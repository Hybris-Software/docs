---
sidebar_position: 1
---

# Simple Slider

## **Props**

| **Texts Prop**              | **Type** | **Default**          | **Description**                                        |
| --------------------------- | -------- | -------------------- | ------------------------------------------------------ |
| **animation**               | string   | ease                 | anitmation style                                       |
| **animationDuration**       | number   | Apply                | The time that an animation takes to complete one cycle |
| **disableDrag**             | boolean  | false                | The user can't drag the elements inside if it's true   |
| **autoPlay**                | boolean  | false                | Move the elements continuously                         |
| **autoPlayTransitionSpeed** | number   | 1000                 | Speed of autoplay transition                           |
| **breakPoints**             | object   | null                 |                                                        |
| **buttonClass**             | string   | UI-KIT default Style | Class name of the pagination buttons                   |
| **dragSlideRatio**          | number   | 0.02                 | Drag slide ratio                                       |
| **gap**                     | number   | 40                   | The gap between the elements                           |
| **nextChild**               | string   | Next                 | Childerns of the next button                           |
| **prevChild**               | string   | Prev                 | Childerns of the Prev button                           |
| **errorIcon**               | svg      | null                 | Icon that shows on error                               |
| **paginationButtons**       | boolean  | true                 | Hide the pagination buttons if it's false              |
| **paginationClass**         | string   | UI-KIT default Style | The class name of the pagiantion Buttons               |
| **slidePerView**            | number   | 3                    | Number of how many slider per view                     |

## Examples

```jsx
//Librires
import { Container,Button, SimpleSlider } from "@hybris-software/ui-kit";

<Container>
    <SimpleSlider
      gap={37}
      slidePerView={4}
      paginationButtons={false}
      autoPlay={false}
      autoPlaySpeed={3000}
      nextChild={
            <Button >
              <img src={rightArrow} alt="" />
              Go right
            </Button>
          }
      prevChild={
            <Button >
              <img src={leftArrow} alt="" />
               Go Left
            </Button>
          }
        >
      breakPoints={{
        576: {
          slidesPerView: 1,
        },
        768: {
          slidesPerView: 2,
        },
        992: {
          slidesPerView: 3,
        },
        1200: {
          slidesPerView: 4,
        },
        1440: {
          slidesPerView: 5,
        },
      }}
    >
      {Childern} // your elements
    </SimpleSlider>
  </div>
</Container>;

```
