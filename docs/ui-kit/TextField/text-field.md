---
sidebar_position: 1
---

# Text Field

## Props

| **Texts Prop**            | **Type** | **Default**    | **Description**                  |
| ------------------------- | -------- | -------------- | -------------------------------- |
| **autoComplete**          | string   | "new-password" | autoComplete                     |
| **className**             | string   |                | Class name for the container     |
| **baseClassName**         | string   |                | Class name for the base          |
| **successClassName**      | string   |                | Class name for the success       |
| **errorMessageClassName** | string   |                | Class name for the error message |
| **errorClassName**        | string   |                | Class name for the error         |
| **labelClassName**        | string   |                | Class name for the error         |
| **isValid**               | boolean  |                | Is valid                         |
| **errorDetails**          | string   |                | Error details                    |
| **label**                 | string   |                | Label                            |
| **onPaste**               | boolean  | true           | On paste                         |
| **onCopy**                | boolean  | true           | On copy                          |
| **placeholder**           | string   |                | Placeholder                      |
| **setValue**              | function | () => {},      | Set value                        |
| **setShowErrors**         | function | () => {},      | Set show errors                  |
| **style**                 | Object   |                | Style                            |
| **value**                 | string   |                | Value                            |
| **showError**             | boolean  | true           | Show error                       |
| **maxLength**             | number   |                | Max length                       |
| **onBlur**                | function | () => {},      | On blur                          |
| **onInput**               | function | () => {},      | On input                         |
| **onChange**              | function | () => {},      | On change                        |
| **readOnly**              | boolean  | false          | Read only                        |
| **inputId**               | string   |                | Input id                         |
| **rows**                  | number   | 4              | Rows                             |
| **cols**                  | number   | 50             | Columns                          |

## Example

```jsx
import { TextField } from "@hybris-software/ui-kit";
<TextField placeholder="Message*" rows={8} />;
```
