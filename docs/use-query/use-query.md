---
sidebar_position: 2
---

# useQuery

## Installation

```jsx
npm install @hybris-software/use-query
```

## generateApiClient

### Parameters

| Parameter           | Type   | Default         | Description                                                                                             |
| ------------------- | ------ | --------------- | ------------------------------------------------------------------------------------------------------- |
| baseUrl             | string |                 | Axios base url                                                                                          |
| timeout             | number | 5000            | Default timeout (milliseconds)                                                                          |
| authorizationHeader | string | "Authorization" | Authorization header name                                                                               |
| authorizationPrefix | string | "Bearer "       | The authorization header prefix, for example <br/> `Authorization: Bearer your_token_from_localstorage` |
| localStorageKey     | string | "token"         | Local storage key that contains the authentication token                                                |

## generateJwtApiClient

### Parameters

| Parameter                   | Type     | Default         | Description                                                                                                                |
| --------------------------- | -------- | --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| baseUrl                     | string   |                 | Axios base url                                                                                                             |
| timeout                     | number   | 5000            | Default timeout (milliseconds)                                                                                             |
| authorizationHeader         | string   | "Authorization" | Authorization header name                                                                                                  |
| authorizationPrefix         | string   | "Bearer "       | The authorization header prefix, for example <br/>`Authorization: Bearer your_token_from_localstorage`                     |
| accessTokenLocalStorageKey  | string   | "accessToken"   | Local storage key that contains the access token                                                                           |
| refreshTokenLocalStorageKey | string   | "refreshToken"  | Local storage key that contains the refresh token                                                                          |
| refreshTokenFunction        | function |                 | An asyncronous function that receives the old access token and refresh token and returns [newAccessToken, newRefreshToken] |

## useQuery

### Parameters

| Parameter          | Type                 | Default     | Description                                                                                                                                                                                                                                                                                |
| ------------------ | -------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| url                | string               |             | Endpoint url                                                                                                                                                                                                                                                                               |
| method             | string               | 'GET'       | Request method (GET, POST...)                                                                                                                                                                                                                                                              |
| executeImmediately | boolean              | false       | Sets whether the call should be executed when the component is created or wait for the call to `executeQuery()`                                                                                                                                                                            |
| onSuccess          | `(response) => void` | `() => { }` | Function executed after a successful query                                                                                                                                                                                                                                                 |
| onUnauthorized     | `(error) => void`    | undefined   | Function executed after an unsuccessful query if the response code is 401 (optional, see `onError`). The default function is the one defined in the `ApiProvider` if it is not specified in useQuery. To disable the default one and not use an `onUnauthorized` set `onUnauthorized=null` |
| onError            | `(error) => void`    | `() => { }` | Function executed after an unsuccessful query. If `onUnauthorized` is not defined, it also handles 401 status code                                                                                                                                                                         |
| clientOptions      | object               | `{}`        | Extra Axios options, ex. `{timeout: 1000}`                                                                                                                                                                                                                                                 |

### Returned parameters

| Parameter    | Type                  | Description                                                                                                                                    |
| ------------ | --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| isLoading    | boolean               | `true` while the query is being executed, `false` otherwise, even if it has not yet started                                                    |
| isError      | boolean               | `true` while the query finished unsuccessfully, `false` otherwise                                                                              |
| isSuccess    | boolean               | `true` while the query finished successfully, `false` otherwise                                                                                |
| response     | any                   | The query response if it finished successfully, `undefined` otherwise                                                                          |
| error        | any                   | The generated error if the query finished unsuccessfully, `undefined` otherwise. If it got a response, it can be accessed via `error.response` |
| executeQuery | `(data?: {}) => void` | Trigger the query with optional body as parameter                                                                                              |

## useMultipleQueries

### Parameters

| Parameter          | Type                 | Default     | Description                                                                                                                                                                                                                                                                                          |
| ------------------ | -------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| queries            | object               |             | Object where the key is the name of the query. The content variables are described below.                                                                                                                                                                                                            |
| -- url             | string               |             | Endpoint url                                                                                                                                                                                                                                                                                         |
| -- method          | string               | 'GET'       | Request method (GET, POST...)                                                                                                                                                                                                                                                                        |
| -- data            | object               | { }         | Request body                                                                                                                                                                                                                                                                                         |
| -- onSuccess       | `(response) => void` |             | Function executed after a successful query                                                                                                                                                                                                                                                           |
| -- onUnauthorized  | `(error) => void`    |             | Function executed after an unsuccessful query if the response code is 401 (optional, see `onError`). The default function is the one defined in the `ApiProvider` if it is not specified in useMultipleQueries. To disable the default one and not use an `onUnauthorized` set `onUnauthorized=null` |
| -- onError         | `(error) => void`    |             | Function executed after an unsuccessful query. If `onUnauthorized` is not defined, it also handles 401 status code                                                                                                                                                                                   |
| executeImmediately | boolean              | false       | Sets whether the call should be executed when the component is created or wait for the call to `executeQueries()`                                                                                                                                                                                    |
| onEnd              | `(response) => void` | `() => { }` | Function executed after after all the queries finished                                                                                                                                                                                                                                               |
| clientOptions      | object               | `{}`        | Extra Axios options, ex. `{timeout: 1000}`                                                                                                                                                                                                                                                           |

### Returned parameters

| Parameter      | Type                  | Description                                                                                                                                                 |
| -------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| executeQueries | `(data?: {}) => void` | Start the queries with optional body as parameter. `data` should be an object where the key is the name of the query and the value is the actual query data |
| errors         | object                | Object containing all the received errors. The key is the name of the query, the value is the error                                                         |
| responses      | object                | Object containing all the received successful responses. The key is the name of the query, the value is the response                                        |
| statuses       | object                | Object containing the status of each query. The key is the name of the query, the value is the status                                                       |
| isLoading      | boolean               | `true` if any calls are in progress, `false` otherwise, even if it has not yet started                                                                      |
| queries        | object                | Contains all the information of each query. The key is the name of the query, the value is an object with the following queries: `status, error, response`  |

## Examples

### Example 1

```javascript
const { isLoading, executeQuery } = useQuery({
  url: "accounts/login/", // If baseUrl has been set, you can use a relative url. It also accepts absolute urls.
  method: "POST",
  executeImmediately: false,
  onSuccess: (response) => {
    console.log(response);
  },
  onUnauthorized: (response) => {
    console.log(response);
  },
});

const submitForm(value) => {
  executeQuery(value);
}

if(isLoading)
  return <Loader />
else
  return <Form submitForm={submitForm} />
```

### Example 2

```javascript
const { isLoading, isSuccess, data, error } = useQuery({
  url: "api/v1/userinfo/",
  method: "GET",
  executeImmediately: true,
});

if (isLoading) return <Loader />;
else if (isSuccess) return <UserInfo data={data} />;
else return <Error error={error} />;
```

### Example with useMultipleQueries

```javascript
const { queries } = useMultipleQueries({
  queries: {
    query1: {
      url: "https://jsonplaceholder.typicode.com/todos/1",
      onSuccess: (response) => {
        console.log("query1", response);
      },
    },
    query2: {
      url: "https://jsonplaceholder.typicode.com/todos/2",
      onError: (error) => {
        console.log("query2 error", error);
      },
      onSuccess: (response) => {
        console.log("query2 success", response);
      },
    },
    query3: {
      url: "https://wrongdomain/todos/3",
      onError: (error) => {
        console.log("query3", error);
      },
    },
  },
  executeImmediately: true,
  onEnd: () => {
    console.log("All done");
  },
});
```

### Example with JWT

```javascript
import axios from "axios";
import { generateJwtApiClient, ApiProvider } from "@hybris-software/use-query";
...
const apiClient = generateJwtApiClient({
  baseUrl: "https://my.api.com/api/v1",
  authorizationHeader: "Authorization",
  authorizationPrefix: "Bearer ",
  refreshTokenFunction: async ({accessToken, refreshToken}) => {
    const response = await axios.post("https://example.com/refresh", {accessToken, refreshToken})
    const updatedAccessToken = response.data.accessToken;
    const updatedRefreshToken = response.data.refreshToken;
    return [updatedAccessToken, updatedRefreshToken];
  }
})
...
root.render(
  <React.StrictMode>
    <ApiProvider apiClient={apiClient} onUnauthorized={(response) => {console.log(response)}}>
      <App />
    </ApiProvider>
  </React.StrictMode >
);
```
