# Condé Nast react-slick fork

### Purpose:
This project was forked to allow for added features developed by Condé Nast engineering.

### Goal:
Remove the need for this fork and have said features adapted into react-slick core.

### Added Features:

| Property       | Type     | Description                                                                                                                            | Working | Proposed to Core | Accepted into Core | PR link                                         |
|----------------|----------|----------------------------------------------------------------------------------------------------------------------------------------|---------|------------------|--------------------|-------------------------------------------------|
| afterInit      | function | callback function called after inner-slider mounts                                                                                     | Yes     | Yes              | Yes                 | [link](https://github.com/akiran/react-slick/pull/1013) |
| lazyLoadOffset | int      | Lazy loads offset amount of images, forwards and backwards, in the queue. ```lazyLoad``` must be set to ```true``` to use this feature | Yes     | Yes               | No                 |                                                 |

### Bug Fixes:

| Description                                       | Working | Proposed to Core | Accepted into Core | PR link                                        |
|---------------------------------------------------|---------|------------------|--------------------|------------------------------------------------|
| [Issue Link](https://github.com/CondeNast/react-slick/issues/9) | Yes     | Yes              | Yes                | [Link](https://github.com/akiran/react-slick/pull/762) |

---

# react-slick

[![Join the chat at https://gitter.im/akiran/react-slick](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/akiran/react-slick?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


Carousel component built with React. It is a react port of [slick carousel](http://kenwheeler.github.io/slick/)



### Installation

**npm**
```bash
npm install react-slick
```
**yarn**
```bash
yarn add react-slick
```


⚠️ Also install slick-carousel for css and font

```bash
npm install slick-carousel
@import "~slick-carousel/slick/slick.css";
@import "~slick-carousel/slick/slick-theme.css";
```

or add cdn link in your html

```html
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.6.0/slick.min.css" />
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.6.0/slick-theme.min.css" />
```

### [Demos](http://neostack.com/opensource/react-slick)

### [PlayGround](https://jsfiddle.net/kirana/20bumb4g/)
Use [jsfiddle template](https://jsfiddle.net/kirana/20bumb4g/) to try react-slick with different settings.

### Filing issues
Please replicate your issue with [jsfiddle template](https://jsfiddle.net/kirana/20bumb4g/) and post it along with issue to make it easy for me to debug.


### Starter Kit
Checkout [yeoman generator](https://github.com/akiran/generator-react-slick) to quickly
get started with react-slick.

### Example

```js
var React = require('react');
var Slider = require('react-slick');

class SimpleSlider extends React.Component {
  render: function () {
    var settings = {
      dots: true,
      infinite: true,
      speed: 500,
      slidesToShow: 1,
      slidesToScroll: 1
    };
    return (
      <Slider {...settings}>
        <div><h3>1</h3></div>
        <div><h3>2</h3></div>
        <div><h3>3</h3></div>
        <div><h3>4</h3></div>
        <div><h3>5</h3></div>
        <div><h3>6</h3></div>
      </Slider>
    );
  }
}
```

### Props

Props            | Type            | Default Value                   | Description                                                 | Working
---------------- | --------------- | ------------------------------- | -----------                                                 | -------
`accessibility`  | `bool`          | `true`                          | Enable tabbing and arrow key navigation                     | Yes
`className`      | `string`        | `''`                            | CSS class for inner slider div                              | Yes
`adaptiveHeight` | `bool`          | `false`                         | Adjust the slide's height automatically                     | Yes
`arrows`         | `bool`          | `true`                          |                                                             | Yes
`nextArrow`      | React Element   | `null`                          | React element for next arrow. [Example](customArrows)       | Yes
`prevArrow`      | React Element   | `null`                          | React element for prev arrow. [Example](customArrows)       | Yes
`autoplay`       | `bool`          | `false`                         |                                                             | Yes
`autoplaySpeed`  | `int`           | `3000`                          | Delay between each auto scroll (in milliseconds)            | Yes
`centerMode`     | `bool`          | `false`                         | Center current slide                                        | Yes
`centerPadding`  |                 | `'50px'`                        |                                                             |
`cssEase`        |                 | `'ease'`                        |                                                             |
`customPaging`   | `func`          | `i => <button>{i + 1}</button>` | Custom paging templates. [Example](customPaging)            | Yes
`dots`           | `bool`          | `Default`                       |                                                             | Yes
`dotsClass`      | `string`        | `'slick-dots'`                  | CSS class for dots                                          | Yes
`draggable`      | `bool`          | `true`                          | Enable scrollable via dragging on desktop                   | Yes
`easing`         | `string`        | `'linear'`                      |                                                             |
`fade`           | `bool`          | `Default`                       |                                                             | Yes
`focusOnSelect`  | `bool`          | `false`                         | Go to slide on click                                        | Yes
`infinite`       | `bool`          | `true`                          | Infinitely wrap around contents                             | Yes
`initialSlide`   | `int`           | `0`                             | Index of first slide                                        | Yes
`lazyLoad`       | `bool`          | `false`                         | Load images or render components on demand                  | Yes
`pauseOnHover`   | `bool`          | `true`                          | Prevents autoplay while hovering                            | Yes
`responsive`     | `array`         | `null`                          | Customize based on breakpoints (detailed explanation below) | Yes
`rtl`            | `bool`          | `false`                         | Reverses the slide order                                    | Yes
`slide`          | `string`        | `'div'`                         |                                                             |
`slidesToShow`   | `int`           | `1`                             | Yes                                                         | Yes
`slidesToScroll` | `int`           | `1`                             |                                                             |
`speed`          | `int`           | `500`                           |                                                             |
`swipe`          | `bool`          | `true`                          |                                                             |
`swipeToSlide`   | `bool`          | `false`                         | Enable drag/swpie irrespective of `slidesToScroll`          | Yes
`touchMove`      | `bool`          | `true`                          |                                                             |
`touchThreshold` | `int`           | `5`                             |                                                             |
`variableWidth`  | `bool`          | `false`                         |                                                             |
`useCSS`         | `bool`          | `true`                          | Enable/Disable CSS Transitions                              | Yes
`vertical`       | `bool`          | `false`                         |                                                             | Yes
`afterChange`    | `func`          | `Default`                       | Index change callback. `index => ...`                       | Yes
`beforeChange`   | `func`          | `null`                          | Index change callback. `(oldIndex, newIndex) => ...`        | Yes
`slickGoTo`      | `int`           | `Default`                       | Go to the specified slide number                            |

#### `responsive` property

Array of objects in the form of `{ breakpoint: int, settings: { ... } }` The breakpoint _int_ is the `maxWidth` so the settings will be applied when resolution is below this value. Breakpoints in the array should be ordered from smallest to greatest. Use 'unslick' in place of the settings object to disable rendering the carousel at that breakpoint. Example: `[ { breakpoint: 768, settings: { slidesToShow: 3 } }, { breakpoint: 1024, settings: { slidesToShow: 5 } }, { breakpoint: 100000, settings: 'unslick' } ]`

[customArrows]: https://github.com/akiran/react-slick/blob/master/examples/CustomArrows.js
[customPaging]: https://github.com/akiran/react-slick/blob/master/examples/CustomPaging.js


### Methods
* `slickNext()`   - function called to change current slide on next slide ([Example](https://github.com/akiran/react-slick/blob/master/examples/PreviousNextMethods.js))
* `slickPrev()`   - function called to change current slide on previous slide ([Example](https://github.com/akiran/react-slick/blob/master/examples/PreviousNextMethods.js))
* `slickGoTo(slideNumber)` - function called to change current slide to given slide number ([Example](https://github.com/akiran/react-slick/blob/master/examples/SlickGoTo.js))

### Custom next/prev arrows

To customize the next/prev arrow elements, simply create new React components and set them
as the values of nextArrow and prevArrow.

```js
class LeftNavButton extends React.Component {
  render() {
    return <button {...this.props}>Next</button>
  }
}
```

Important: be sure that you pass your component's props to your clickable element
like the example above. If you don't, your custom component won't trigger the click handler.

You can also set `onClick={this.props.onClick}` if you only want to set the click handler.

### Flexbox support
If you have flex property on container div of slider, add below css
```css
* {
  min-height: 0;
  min-width: 0;
}
```

### Test Setup
If you try to run tests with jest in a project that uses react-slick, you may run into this error
```
matchMedia not present, legacy browsers require a polyfill
```

To fix this issue add below snippet in test-setup.js
```js
window.matchMedia = window.matchMedia || function() {
    return {
        matches : false,
        addListener : function() {},
        removeListener: function() {}
    };
};

```
and add below jest config in package.json
```json
"jest": {
    "setupFiles": ["test-setup.js"]
}
```


### Development
Want to run demos locally

```bash
git clone https://github.com/akiran/react-slick
npm install
npm start
open http://localhost:8080
```

### Polyfills for old IE support
`matchMedia` support from [media-match](https://github.com/weblinc/media-match)
