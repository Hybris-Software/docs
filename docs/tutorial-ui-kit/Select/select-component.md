---
sidebar_position: 1
---

# Select

This is a React component called **Select** which represents a custom select input. The component receives a number of props to customize its appearance and functionality.

The component renders a button element that toggles the select when clicked. The select is displayed as a dropdown list with options that the user can choose from. When an option is selected, the value of the select is updated and the dropdown list is closed.

<!-- - **style**: Style for the select -->

## Props:

### Style Prop

| **Prop**        | **Type** | **Default** | **Description**                        |
| --------------- | -------- | ----------- | -------------------------------------- |
| **style**       | Object   |             | Style for the select                   |
| **styleOpened** | Object   |             | Style for the select when it is opened |
| **styleClosed** | Object   |             | Style for the select when it is closed |

---

### Class Props

| **Prop**                 | **Type** | **Default** | **Description**                       |
| ------------------------ | -------- | ----------- | ------------------------------------- |
| **className**            | string   |             | Class name for the select             |
| **classNameOpened**      | string   |             | Class name for the select when opened |
| **classNameOption**      | string   |             | Class name for the option             |
| **classNamePlaceholder** | string   |             | Class name for the placeholder        |

---

### Basic Props

| **Prop**        | **Type** | **Default** | **Description**                                                  |
| --------------- | -------- | ----------- | ---------------------------------------------------------------- |
| **placeholder** | string   |             | Placeholder text for the select                                  |
| **value**       | string   |             | The currently selected value                                     |
| **setValue**    | function |             | A function to update the selected value                          |
| **items**       | Array    |             | An array of items to display in the select                       |
| **labelKey**    | string   |             | The key to use for the label of each item (if items are objects) |

---

### Additional Props

| **Prop**                | **Type**    | **Default** | **Description**                                              |
| ----------------------- | ----------- | ----------- | ------------------------------------------------------------ |
| **icon**                | JSX.Element |             | An icon to display in the select                             |
| **iconTransitionSpeed** | number      |             | The speed of the icon transition                             |
| **scrollToTopOnClose**  | boolean     |             | Whether to scroll to the top of the select when it is closed |
| **maxHeightOpened**     | number      |             | The maximum height of the select when it is opened           |

---

### Events

| **Prop**           | **Type** | **Default** | **Description**                                    |
| ------------------ | -------- | ----------- | -------------------------------------------------- |
| **onSelectOpen**   | function |             | A function to call when the select is opened       |
| **onSelectClose**  | function |             | A function to call when the select is closed       |
| **onSelectChange** | function |             | A function to call when the selected value changes |

---

### Advanced Props functions

| **Prop**              | **Type** | **Default** | **Description**                                               |
| --------------------- | -------- | ----------- | ------------------------------------------------------------- |
| **renderOption**      | function |             | A function to customize the rendering of each option          |
| **renderPlaceholder** | function |             | A function to customize the rendering of the placeholder text |

## Examples:

### Create your first Select Component

Some examples that maybe make it easier to understand :

```jsx
import React, { useState } from "react";
import { Select } from "@hybris-software/ui-kit";

const SelectMe = () => {
  const [selectedOption, setSelectedOption] = useState();

  const handleOptionChange = (value) => {
    setSelectedOption(value);
  };
  return (
    <div>
      <Select
        items={[1, 2, 3, 4, 5]}
        placeholder="Select number"
        value={selectedOption}
        setValue={handleOptionChange}
      />
    </div>
  );
};
export default SelectMe;
```
