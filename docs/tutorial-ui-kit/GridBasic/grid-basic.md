---
sidebar_position: 1
---

# Grid Basic

## Props:

### 1.Container

| **Prop**      | **Type**    | **Default**                   | **Description**                            |
| ------------- | ----------- | ----------------------------- | ------------------------------------------ |
| **className** | string      | UI-KIT default Style          | Add one or more class names to the element |
| **children**  | JSX.Element | UI-KIT default disabled Style | Rendered children                          |
| **style**     | Object      | UI-KIT default disabled Style | Add inline styles to the element           |

### 2.Col (Column)

| **Prop**         | **Type**    | **Default**                   | **Description**                                           |
| ---------------- | ----------- | ----------------------------- | --------------------------------------------------------- |
| **orderSm**      | number      | (1 to 12)                     | Set the order of the column for small screens             |
| **orderMd**      | number      | (1 to 12)                     | Set the order of the column for medium screens            |
| **orderLg**      | number      | (1 to 12)                     | Set the order of the column for large screens             |
| **orderXl**      | number      | (1 to 12)                     | Set the order of the column for extra large screens       |
| **orderXxl**     | number      | (1 to 12)                     | Set the order of the column for extra extra large screens |
| **colsize**      | number      | defualt percentage            | Change the width of the column                            |
| **marginbottom** | number      | UI-KIT default Style          | Change the margin bottom of the column                    |
| **children**     | JSX.Element | UI-KIT default disabled Style | Rendered children                                         |
| **style**        | Object      | UI-KIT default disabled Style | Add inline styles to the element                          |
| **className**    | string      | UI-KIT default Style          | Class Name                                                |

### 3.Row

| **Prop**      | **Type**    | **Default**                   | **Description**                            |
| ------------- | ----------- | ----------------------------- | ------------------------------------------ |
| **className** | string      | UI-KIT default Style          | Add one or more class names to the element |
| **children**  | JSX.Element | UI-KIT default disabled Style | Rendered children                          |
| **columnGap** | Object      | UI-KIT default                | Add gap between the Column                 |
| **useGap**    | boolean     | true                          | If you want to use gap or not              |

## Example

```jsx
mport { Container, Row, Col } from "@hybris-software/ui-kit";

<Container>
  <Row
    className={Style.customRow}
    columnGap={{
      horizontal: {
        xs: 30,
        sm: 30,
        md: 30,
        lg: 30,
        xl: 30,
        xxl: 30,
      },
      vertical: {
        xs: 50,
        sm: 50,
        md: 50,
        lg: 50,
        xl: 50,
        xxl: 50,
      },
    }}
  >
    <Col xl={4} lg={6} md={8} sm={12}>
      <h3>title</h3>
      <p>description</p>
    </Col>
    <Col xl={4} lg={6} md={8} sm={12}>
      <h3>title</h3>
      <p>description</p>
    </Col>
  </Row>
</Container>;
```
