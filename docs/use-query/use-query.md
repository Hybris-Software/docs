---
sidebar_position: 1
---

# useQuery

## Introduction:

This hook can be used to perform queries to an endpoint. Allows easy management of operations and query status.
It requires an `Axios` client. This library already provides the `generateApiClient` function which returns a client with a variable base url and an interceptor to send an authentication header. You may also create an axios client by your own.

## Installation:

Install the library with :

```bash
    npm install @hybris-software/use-query.
```

At the upper level of the application you should also insert the `ApiProvider` component which requires an `apiClient` prop. It should be an Axios client which you can create by your own or use `generateApiClient` to generate one.

## Props:

| **Prop**              | **Type**    | **Default**                   | **Description**                                 |
| --------------------- | ----------- | ----------------------------- | ----------------------------------------------- |
| **buttonClassName**   | string      | UI-KIT default Style          | Class name for the button                       |
| **disabledClassName** | string      | UI-KIT default disabled Style | Class name for the disabled button              |
| **className**         | string      | UI-KIT default disabled Style | Class name for the button                       |
| **disabled**          | boolean     | false                         | Disables the Button and preventing mouse events |
| **isLoading**         | boolean     | false                         | The loading behaviors of the button             |
| **loader**            | JSX.Element | UI-KIT basic loader           | A loader that we can pass to the button         |
| **onClick**           | function    |                               | On click function                               |
| **style**             | Object      | UI-KIT style                  | Style                                           |
| **children**          | JSX.Element |                               | Children of the button                          |

## Examples:

### Example 1

```jsx
import { Button } from "@hybris-software/ui-kit";

<Button
  disabled={Api.isLoading} //Api.isLoading retruns ture or false
  isLoading={Api.isLoading}
  loader={<spin />}
  onClick={() => {
    Api.execute();
  }}
>
  Check status
</Button>;
```
