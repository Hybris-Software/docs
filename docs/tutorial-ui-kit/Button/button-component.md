---
sidebar_position: 1
---

# Button

The "Button" component is returns a div element with a button-like appearance.

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

### Example 2

```jsx
import { Button } from "@hybris-software/ui-kit";

<Button
  buttonClassName={Style.button}
  disabledClassName={Style.buttonDisabled}
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
