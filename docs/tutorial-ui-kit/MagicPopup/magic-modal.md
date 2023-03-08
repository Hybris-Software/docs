---
sidebar_position: 1
---

# Magic Modal

This is a React component that defines a modal.

:::danger Note

You must wrap the main app with **ThemeProvider** to use this component

:::

<!-- - **style**: Style for the select -->

## Props:

### Style Prop

| **Prop**           | **Type** | **Default** | **Description**          |
| ------------------ | -------- | ----------- | ------------------------ |
| **contentStyle**   | Object   |             | Style for the content    |
| **overlayStyle**   | Object   |             | Style for the overlay    |
| **modalStyle**     | Object   |             | Style for the modal      |
| **closeIconStyle** | Object   |             | Style for the close icon |

---

### Class Props

| **Prop**               | **Type** | **Default** | **Description**               |
| ---------------------- | -------- | ----------- | ----------------------------- |
| **contentClassName**   | string   |             | Class name for the content    |
| **overlayClassName**   | string   |             | Class name for the overlay    |
| **modalClassName**     | string   |             | Class name for the modal      |
| **closeIconClassName** | string   |             | Class name for the close icon |

---

### Basic Props

| **Prop**               | **Type**    | **Default** | **Description**       |
| ---------------------- | ----------- | ----------- | --------------------- |
| **closeIcon**          | JSX.Element |             | Close icon            |
| **showCloseIcon**      | boolean     |             | Show close icon       |
| **destroyBodyOnClose** | boolean     |             | Destroy body on close |

---

### Events

| **Prop**             | **Type** | **Default** | **Description**     |
| -------------------- | -------- | ----------- | ------------------- |
| **onModalOpen**      | function |             | On modal open       |
| **onModalClose**     | function |             | On modal close      |
| **onBodyUpdate**     | function |             | On body update      |
| **onModalDestroy**   | function |             | On modal destroy    |
| **onCloseIconClick** | function |             | On close icon click |

## Examples

### Create your first Modal Component

```jsx
import React, { useRef } from "react";
import { MagicModal } from "@hybris-software/ui-kit";

const ExampleModal = () => {
  // Refs
  const modalRef = useRef(null);

  // Handlers
  const handleOpenModal = () => {
    modalRef.current.open();
  };

  const handleCloseIconClick = () => {
    console.log("Close icon clicked!");
  };

  // JSX
  return (
    <div>
      <button onClick={handleOpenModal}>Open Modal</button>
      <MagicModal
        ref={modalRef}
        body={<p>Default body content</p>}
        onModalOpen={() => console.log("Modal opened!")}
        onModalClose={() => console.log("Modal closed!")}
        onBodyUpdate={() => console.log("Body updated!")}
        onModalDestroy={() => console.log("Modal destroyed!")}
        onCloseIconClick={handleCloseIconClick}
        destroyBodyOnClose={false}
      />
    </div>
  );
};

export default MagicModal;
```

### Second example

```jsx
import React, { useRef, useState } from "react";
import { MagicModal } from "@hybris-software/ui-kit";
import SeletMe from "./Components/SelectMe";

function App() {
  const modalRef = useRef(null);
  const [bodyContent, setBodyContent] = useState(<SeletMe />);
  // Handlers
  const handleOpenModal = () => {
    modalRef.current.open();
  };

  const handleUpdateBody = () => {
    const newBodyContent = <p>New body content</p>;
    setBodyContent(newBodyContent);
    modalRef.current.updateBody(newBodyContent);
  };

  const handleDestroyModal = () => {
    modalRef.current.destroy();
  };

  const handleCloseIconClick = () => {
    console.log("Close icon clicked!");
  };

  const onBodyUpdate = () => {
    setBodyContent(<p>Body updated!</p>);
  };

  // JSX
  return (
    <div>
      <button onClick={handleOpenModal}>Open Modal</button>
      <button onClick={handleUpdateBody}>Update Body</button>
      <button onClick={handleDestroyModal}>Destroy Modal</button>
      <MagicModal
        ref={modalRef}
        body={bodyContent}
        onModalOpen={() => console.log("Modal opened!")}
        onModalClose={() => console.log("Modal closed!")}
        onBodyUpdate={onBodyUpdate}
        onModalDestroy={() => console.log("Modal destroyed!")}
        onCloseIconClick={handleCloseIconClick}
        destroyBodyOnClose={false}
      />
    </div>
  );
}

export default MagicModal;
```
