---
sidebar_position: 1
---

# Button

The "Button" component is returns a div element with a button-like appearance.

## Props:

| **Prop**              | **Type**    | **Default**                   | **Description**                    |
| --------------------- | ----------- | ----------------------------- | ---------------------------------- |
| **buttonClassName**   | string      | UI-KIT default Style          | Class name for the button          |
| **disabledClassName** | string      | UI-KIT default disabled Style | Class name for the disabled button |
| **className**         | string      | UI-KIT default disabled Style | Class name for the button          |
| **disabled**          | boolean     | false                         | Disables the Button                |
| **isLoading**         | boolean     | false                         | Is the button loading              |
| **loader**            | JSX.Element | UI-KIT basic loader           | Loader                             |
| **onClick**           | function    |                               | On click function                  |
| **style**             | Object      | UI-KIT style                  | Style                              |
| **children**          | JSX.Element |                               | Children of the button             |

## Examples:

### Example

```jsx
import { Button } from "@hybris-software/ui-kit";

<Button buttonClassName={Style.button} onClick={() => setState(State)}>
  Click me
</Button>;
```
