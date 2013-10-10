# jQuery.CSS3animate

jQuery.CSS3Animate is jQuery plug that is intended for use as `jQuery.animate()`.

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

## Callback call after animation end

```javascript
$('.myanimate').CSS3Animate({
  'left': 400,
  'background-color': '#49A0A0'
}, 1000, 'easeInOutExpo', function() {
  ... // do something
});
```

## Animate continuously

Animation queue is added to the stack, animation during playback is not stopped.

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

## Stop the animation playing, overwrite animation

Animation queue is cleared, animation during playback will be interrupted.

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

`CSS3Animate([props], [duration], [easing], [callback])`

`CSS3Animate('config', [options])`

`CSS3Animate('stop')`

`CSS3Animate('delay', [duration])`

`CSS3Animate('fadeIn', [duration], [easing], [callback])`

`CSS3Animate('fadeOut', [duration], [easing], [callback])`

`CSS3Animate('fadeToggle', [duration], [easing], [callback])`

`CSS3Animate('hide', [duration], [easing], [callback])`

`CSS3Animate('show', [duration], [easing], [callback])`

`CSS3Animate('toggle', [duration], [easing], [callback])`

`CSS3Animate('slideDown', [duration], [easing], [callback])`

`CSS3Animate('slideUp', [duration], [easing], [callback])`

`CSS3Animate('slideToggle', [duration], [easing], [callback])`

## Supporting easing

I support following types of easing:

`linear`, `swing`, `jswing`, `easeInSine`, `easeOutSine`, `easeInOutSine`, `easeInQuad`, `easeOutQuad`, `easeInOutQuad`, `easeInCubic`, `easeOutCubic`, `easeInOutCubic`, `easeInQuart`, `easeOutQuart`, `easeInOutQuart`, `easeInQuint`, `easeOutQuint`, `easeInOutQuint`, `easeInExpo`, `easeOutExpo`, `easeInOutExpo`, `easeInCirc`, `easeOutCirc`, `easeInOutCirc`, `easeInBack`, `easeOutBack`, `easeInOutBack`

