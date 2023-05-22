# React components transition [live example!](https://react-components-transition.netlify.app/)

## Use case

A very small but useful React component, which allows to smart transition between components without adding unnecessary state's hooks to render conditionally

Something like React router but simplified and without rendering based on URL. Just more static

## Instaling

```npm
  npm i react-components-transition
```

## Usage

### Initializing

```JavaScript
  import { ComponentsTransition } from "react-components-transition";

  const Component () => {


    return (
      <>
        <ComponentsTransition>

          {/* Atleast 2 components and first given is visible on first render */}

          <Exmaple1 key="example1"></Example>
          <Exmaple2 key="example2"></Example>
        </ComponentsTransition>
      </>
    );
  }
```

### Switching component

```JavaScript
  import { TransitionButton } from "react-components-transitionn";

  const componentKey = "example2"

  const Example1 = () => {
    return <TransitionButton show={componentKey}>Show example 2 component</TransitionButton>
  }
```

### Or with animations

```JavaScript
  import { TransitionButton } from "react-components-transitionn";

  const componentKey = "example2"

  const Example1 = () => {
    return (
      <TransitionButton show={componentKey} animation={{ className: "animation", duration: 500 }}> // ClassName of animation in component which shows (Exmaple2 component)
        Show example 2 component
      </TransitionButton>
    );
  };
```

In css

```css
/* CSS file of Exmaple2 component */

/* Remember to give unique animation name!!! */

@keyframes animation1 {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}

.animation {
  transform: scale(0);
  animation: animation1 500ms forwards;
}
```

## Last update 2.0.1

- Changed render method:
  - New showed child always display before (on html page) current hiding child. (There was bug with correct positioning elements)
  - Current showing child always is visible on the top of others (has the highest z-index)

## update 2.0.0

- Added smooth transitions between rerenders based on CSS class

## What's next?

Probably maybe any async/await rendering?

Any suggestions? Write to: **s.stepniak01@gmail.com**
