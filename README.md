# Toddy
##### a fork of [Neat](http://neat.bourbon.io/) (from ThoughtBot) put together by [Extended Play](http://www.ep-ny.com)
---
###### Dependencies
As this is a fork of Bourbon Neat, it is dependent on [Bourbon](http://www.bourbon.io). Include it in your main stylesheet before including Toddy.

---
###### Breakpoints
Toddy comes packaged with a series of breakpoints:
|Name|Width Range|
|----|-----|
|small|0-767px|
|medium-only|768px-1023px|
|medium-up|768px-|
|large-only|1024px-1279px|
|large-up|1024px-|
|xlarge-only|1280px-1799px|
|xlarge-up|1280px-|
|xxlarge|1800px-|

---
###### Classes
A la Foundation, Toddy comes packaged with classes for you to use when constructing your templates so that not all of your layout has to be written in CSS. Grid size declarations are prefixed with the breakpoint at which they should begin, followed by the number of columns the item should fill. A `div` element that should be full size on the `small` breakpoint but half-size on the `large` breakpoint is written as `<div class="small-12 large-6 columns"></div>`. Rows of grid items should be nested within `.row` elements, and grid items should be given the class of `.columns` after grid size declarations. An example is as follows:
```
<div class="row">
  <div class="small-12 columns"></div>
  <div class="small-12 medium-6 large-3 xlarge-2 xxlarge-1 columns"></div>
</div>
```

Neat's contextual `span-columns` function works, as well. When in the context of an existing grid column, sub-columns can be created as follows:
```
<div class="row">
  <div class="small-12 medium-6 columns">
    <div class="row">
      <div class="small-12of12 medium-4of6 columns"></div>
      <div class="small-12of12 medium-2of6 columns"></div>
    </div>
  </div>
</div>
```

You can use Neat's `@include shift()` function using classes.
```
<div class="row">
  <div class="small-12 medium-6 medium-offset-6 columns">
    <div class="row">
      <div class="small-12of12 medium-2of6 columns"></div>
      <div class="small-12of12 medium-2of6 medium-offset-2of6 columns"></div>
    </div>
  </div>
</div>
```


---
###### Fixed Gutters
Fixed gutters are enabled by default. To go back to Neat's normal functionality, go to `grid.scss` on line 19, change `$fixed-gutter: true;` to `$fixed-gutter: false;`.

By default, only `$fixed-gutter-small` is defined. If you wish to change gutter sizes for larger breakpoints, do so in `grid.scss`, lines 25-30.

---
###### Flexbox
Flexbox grids work just like the aforementioned grid classes. However, instead of wrapping grid items in a `div` with a class of `.row`, just give it a class of `.flex-row`. Replace `.columns` with `.flex-columns`. Boom. It works.

```
<div class="flex-row">
  <div class="small-12 medium-9 large-6 flex-columns"></div>
  <div class="small-12 medium-3 large-6 flex-columns"></div>
</div>
```
