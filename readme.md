# Modern CSS for Backend Developers

[Flexbox specification](https://www.w3.org/TR/css-flexbox-1/)

## Episode 1: Piece by Piece - Structure, Resets and Flexbox

* Mentally visualize the structure in your head:
    * Oh, it looks like there's a background color.
    * Next, it sounds like there are two sections.
    * Get these two components on the left and right.
    * etc.
* You write it out.
* Then you take it step by step.

## Episode 2: Flex Your Grids

An utility class is a class that:

* is not the most semantic thing in the world
* helps you build up styling for your components
* it has to be as minimal as possible in order to be reused anywhere

The css property `flex: 1, 2, 3, etc.` will allow the component to take twice, 3<br>
times as much space than the others. 

Setting `flex: 1` on a sub-component from a flex block forces that element to take<br>
all available space.

## Episode 3: Workshop - Card Design

Like episode 1 but with more tinkering.

When you set `flex-direction: column` the axis for `align-items: center` reverses.

Naming convention for classes: if a component name is `card`, all its sub-elements<br>
will be named `card-*`.

Use `color: inherit` to avoid setting the color in each subcomponent of a parent<br>
component.

## Episode 4: Refactoring to Utility Classes and Tailwind

See https://tailwindcss.com/docs/what-is-tailwind/

## Episode 5: Easy Flexbox Wins

In order to have blocks to the left and right, always wrap them
inside a div. See second and third examples.

See an example on how to create a sticky footer for a page with
variable content.

## Episode 10: Mobile-First Design

Nowadays, the bulk of the trafic is coming from mobile, so:

* Think Mobile-First
* And then build from there

Use [Zeplin](https://zeplin.io/) for collaboration between developer and designer.

## Episode 11: Mobile-First Layouts

The default classes applied to an element should be mobile-first then use the res-<br>
ponsive breakpoints like `md`, `lg`,(from tailwind) etc.

## Episode 13: Better sizing and spacing with rems

rem = root ems - The rem unit is relative to the root—or the html—element. 

Knowing that the browser sets the font size to 16 px by default for the html ele-<br>
ment, the formula for determining the rem value you should use for a given pixels<br>
value is:

`pixel size / browser pixel size = x rem`

Ex: `40 px / 16 px = 2.5 rem`

To calculate pixel size, use this formula:

`rem size * browser pixel size = y pixels`

Ex: `2.5 rem * 16 px = 40 px`


In order for rem to work, you have to define the html base font size for
each device in your css file:

```css
html {
	font-size: 12px;

	@screen lg {
		font-size: 16 px;
	}
}
```

or directly in the `html` element:

```html
<html class="text-xs lg:text-base">
...
</html>
```

It's useful to take every section of your site and wrap it in some div with class<br>
`section` on which you can apply some padding so that the content looks better<br>
on every device.

Example:

```css
/* you want some margin bottom for paragraphs inside a main container */
.content > * { margin-bottom: 1em; }

.section { padding-left: 20px; padding-right: 20px; }
```

## Episode 14: Reverse the order

Use `flex-direction: column-reverse` or `flex-col-reverse` to revert the order of<br>
elements vertically. It's quite a neat trick for not having to move around the<br>
elements.

## Episode 15: Make it Sticky

To make an element stick until the end of its container with plain CSS, you can use:

```css
.sticky {
	position: sticky;
	top: 0; /* you need to set a top value so that it doesn't behave like 
			a relatively positioned document */
}
```

Using tailwind:

```html
<div class="sticky top-0">...</div>
```

You can check on what browsers a feature is supported by checking [caniuse.com](https://caniuse.com/#search=sticky).
