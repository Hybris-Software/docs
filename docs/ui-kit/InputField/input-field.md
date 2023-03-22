---
sidebar_position: 1
---

# Input Field

## Props:

### Classes:

| **Prop**                  | **Type** | **Default**                        | **Description**                              |
| ------------------------- | -------- | ---------------------------------- | -------------------------------------------- |
| **className**             | string   | UI-KIT default Style               | Class name for the input field               |
| **baseClassName**         | string   | UI-KIT basic Style                 | Base class name for the input field          |
| **successClassName**      | string   | UI-KIT default Success Style       | Success class name for the input field       |
| **errorMessageClassName** | string   | UI-KIT default Error Message Style | Error message class name for the input field |
| **errorClassName**        | string   | UI-KIT default Error Style         | Error class name for the input field         |
| **labelClassName**        | string   | UI-KIT default label Style         | Label class name for the input field         |

### Icons:

| **Prop**                       | **Type** | **Default**             | **Description**              |
| ------------------------------ | -------- | ----------------------- | ---------------------------- |
| **icon**                       | svg      | UI-KIT default icon     | Icon                         |
| **errorIcon**                  | svg      | null                    | Icon on error                |
| **successIconVisibility**      | boolean  | true                    | Show or not the success icon |
| **successIcon**                | svg      | UI-KIT default icon     | Icon that shows on Success   |
| **showPasswordIconVisibility** | boolean  | true                    | Show or not the error icon   |
| **showPasswordIcon**           | svg      | UI-KIT default icon     | Password icon is On          |
| **showPasswordIconOff**        | svg      | UI-KIT default icon off | Password icon is Off         |

### Basic:

| **Prop**        | **Type** | **Default** | **Description**                 |
| --------------- | -------- | ----------- | ------------------------------- |
| **label**       | string   | null        | Label                           |
| **placeholder** | string   | null        | placeholder                     |
| **type**        | string   | text        | type of the input field         |
| **value**       | string   | undefined   | The value of the input.         |
| **setValue**    | function | () => {},   | changing the value of the input |
| **style**       | Object   | null        | Style                           |

### More Props

| **Prop**          | **Type** | **Default**    | **Description**                                                                                                    |
| ----------------- | -------- | -------------- | ------------------------------------------------------------------------------------------------------------------ |
| **isValid**       | boolean  | undefined      | Check if the input is valid or not                                                                                 |
| **errorDetails**  | string   | null           | Error details                                                                                                      |
| **onPaste**       | boolean  | true           | Allow or prevent the user to paste over the input                                                                  |
| **onCopy**        | boolean  | true           | Allow or prevent the user to copy the content of the input                                                         |
| **setShowErrors** | function | () => {},      | Set show errors                                                                                                    |
| **showArrows**    | boolean  | false          | Show arrows on the input                                                                                           |
| **showError**     | boolean  | true           | Show the error under the input , if false hide                                                                     |
| **readOnly**      | boolean  | false          | Prevent the user of editing the input                                                                              |
| **inputId**       | string   | random         | give an id for the input                                                                                           |
| **onBlur**        | function | () => {},      | The onBlur event handler is called when focus has left the element                                                 |
| **onInput**       | function | () => {},      | The onInput gets triggered on every keystroke on the keyboard                                                      |
| **onChange**      | function | () => {},      | The onChange gets triggered on every keystroke on the keyboard.                                                    |
| **autoComplete**  | string   | "new-password" | specify what if any permission the user agent has to provide automated assistance in filling out form field values |
| **maxLength**     | number   | null           | give a max length for the input                                                                                    |
| **inputRef**      | Object   | null           | input reference                                                                                                    |

## Example 1

```jsx
import { InputField } from "@hybris-software/ui-kit";

<div className={Style.doubleForm}>
  <InputField placeholder="First Name" className={Style.firstField} />

  <InputField
    style={{ background: " rgba(217, 217, 217, 0.4)" }}
    placeholder="Last Name"
  />
</div>;
```
