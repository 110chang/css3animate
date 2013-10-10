# jQuery.CSS3animate

jQuery.CSS3Animate is jQuery plugin that is intended for use as `jQuery.animate()`.

[Sample page](http://110chang.com/css3animate/)(in Japanese)

## Basic usage

```javascript
$('.myanimate').CSS3Animate({
  'left': 400,
  'background-color': '#FFCE73'
}, 1000, 'easeInOutExpo');
```
## Change default values before animation

```javascript
$('.myanimate').CSS3Animate('config', {
  duration: 1000,
  easing: 'easeOutBack'
}).CSS3Animate({
  'left': 400,
  'background-color': '#49A0A0'
});
```

## Callback calls after animation end

```javascript
$('.myanimate').CSS3Animate({
  'left': 400,
  'background-color': '#49A0A0'
}, 1000, 'easeInOutExpo', function() {
  ... // do something
});
```

## Animate continuously

Animation queue is added to a stack, animations during playback are not stopped.

```javascript
$('#btn-myanimate').toggle(function() {
  $('.myanimate').CSS3Animate({
    'left': 400,
    'background-color': '#FFCE73'
  });
}, function() {
  $('.myanimate').CSS3Animate({
    'left': 0,
    'background-color': '#49A0A0'
  });
});
```

## Stop animations during playback, overwrite animations

Animation queue is cleared, animations during playback will be interrupted.

```javascript
$('#btn-myanimate').toggle(function() {
  $('.myanimate')
    .CSS3Animate('stop')
    .CSS3Animate({
      'left': 400,
      'background-color': '#FF7E73'
    });
}, function() {
  $('.myanimate')
    .CSS3Animate('stop')
    .CSS3Animate({
      'left': 0,
      'background-color': '#49A0A0'
    });
});
```

## Use 2D transform

```javascript
$('.myanimate').CSS3Animate({
  'transform': {
    'translate': [400, 0],
    'scale': 1.2,
    'rotate': 10,
    'skew': [5, 10]
  }
});
```

## Methods

### `CSS3Animate`
```javascript
CSS3Animate([props], [duration], [easing], [callback])
```
Main function of this plugin.

### `'config'`
```javascript
CSS3Animate('config', [options])
```
Change default values. Currently, `easing` and `duration` can be set.

### `'stop'`
```javascript
CSS3Animate('stop')
```
Stop animations during playback, clear a queue stacked.

### `'delay'`
```javascript
CSS3Animate('delay', [duration])
```
Delay start of animations. It should not be used in conjunction with `stop`.

### `'fadeIn'`
```javascript
CSS3Animate('fadeIn', [duration], [easing], [callback])
```
Alternative of `jQuery.fadeIn()` in CSS3.

### `'fadeOut'`
```javascript
CSS3Animate('fadeOut', [duration], [easing], [callback])
```
Alternative of `jQuery.fadeOut()` in CSS3.

### `'fadeToggle'`
```javascript
CSS3Animate('fadeToggle', [duration], [easing], [callback])
```
Alternative of `jQuery.fadeToggle()` in CSS3.

### `'hide'`
```javascript
CSS3Animate('hide', [duration], [easing], [callback])
```
Alternative of `jQuery.hide()` in CSS3.

### `'show'`
```javascript
CSS3Animate('show', [duration], [easing], [callback])
```
Alternative of `jQuery.show()` in CSS3.

### `'toggle'`
```javascript
CSS3Animate('toggle', [duration], [easing], [callback])
```
Alternative of `jQuery.toggle()` in CSS3.

### `'slideDown'`
```javascript
CSS3Animate('slideDown', [duration], [easing], [callback])
```
Alternative of `jQuery.slideDown()` in CSS3.

### `'slideUp'`
```javascript
CSS3Animate('slideUp', [duration], [easing], [callback])
```
Alternative of `jQuery.slideUp()` in CSS3.

### `'slideToggle'`
```javascript
CSS3Animate('slideToggle', [duration], [easing], [callback])
```
Alternative of `jQuery.slideToggle()` in CSS3.

## Browser

Chrome, Firefox, Safari(Mac, iOS), Android(Webkit), IE10+.

## Supporting easing

This plugin supports following types of easing:

`linear`, `swing`, `jswing`, `easeInSine`, `easeOutSine`, `easeInOutSine`, `easeInQuad`, `easeOutQuad`, `easeInOutQuad`, `easeInCubic`, `easeOutCubic`, `easeInOutCubic`, `easeInQuart`, `easeOutQuart`, `easeInOutQuart`, `easeInQuint`, `easeOutQuint`, `easeInOutQuint`, `easeInExpo`, `easeOutExpo`, `easeInOutExpo`, `easeInCirc`, `easeOutCirc`, `easeInOutCirc`, `easeInBack`, `easeOutBack`, `easeInOutBack`

