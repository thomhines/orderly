orderly
=======

**The world's best, easiest, most flexible grid system.**

Check out this editable [demo](http://codepen.io/thomhines/pen/iIKcH) on CodePen to try it out.


## Features

- Uses both a grid-unit or fraction-based grid system. This means you can set a column to 1/4th the width of the container **OR** 3 grid-units wide of a 12-column grid, and end up with the same column! Plus, you can mix and match your units as much as you want.

- Built with Sass to automate the heavy lifting and to keep your CSS clean and light.

- Simple mixins make it a snap to control grid settings, even accross multiple responsive breakpoints.

- Smart default settings make Orderly great right out of the box, but all settings can be easily adjusted and overwritten from within your .scss file.






## How to Use: The Easy Way

	.container {
		@include container();
	}

	.column {
		@include column(1/3);
	}

or

	.column {
		@include column(.333);
	}

or

	.column {
		@include column(4);
	}



If you use whole numbers and default settings, orderly assumes you are setting the width of your column in grid-units. Otherwise, it will assume that the column should is a fraction of the total width of the container. 

The default grid is 12 grid-units wide.


## More Powerful Stuff

### Settings


To adjust any of the default settings, just add the setting name and set it to the value you would like *before* you include orderly in your SCSS file.

For example:
	
	// top of your .scss file
	$total_width: 800px;
	$gutter: 15px;
	@import 'orderly';



#### $total_width
*Sets the maximum width of the container*

default: 960px



#### $total_columns
*Sets the number of columns in the grid*

default: 12



#### $gutter
*Sets the space between columns in the grid*

default: 30px;



#### $auto_responsive
*Use default breakpoint markers to control container and column width*

**Nutshell**: container becomes fluid below `$lg` screen size and columns are full width below `$sm` screen size

default: true



#### $go_to_fluid:
*The size/breakpoint at which the layout should become fluid*

**NOTE**: This value only works when $auto_responsive is set to true.

default: $lg



#### $go_to_single_column
*The size/breakpoint at which columns should stack on top of one another*

**NOTE**: This value only works when $auto_responsive is set to true.

default: $sm



#### $enable_helper_classes
*Adds helper classes to your CSS file*

**Nutshell**: If you prefer to control your grid from within your HTML instead of your SCSS, enabling this will add a large assortment of common class names to your CSS file. Keeping this disabled this will make your output CSS much smaller.

default: false




#### Responsive Breakpoints

##### $xs
default: 420px

##### $sm
default: 568px

##### $md
default: 768px

##### $lg
default: 1024px

##### $xl
default: 1280px










## API -or- REAL POWER



#### container
*Sets properties on container elements*

$width: width of the container (default: full container width)

$breakpoint: applies width only when browser width is less than this value 

**NOTE**: Multiple container() functions can be used to change widths at various browser sizes. For instance:

	.container {
		@include container(960px);
		@include container(700px, 'lg');
		@include container(100%, 'sm');
	}


#### column
*Sets properties on column elements*

$width: number of columns to fill (default: 100% of the container width)

$breakpoint: applies width only when browser width is less than this value

**NOTE**: Multiple column() functions can be used to change widths at various browser sizes. For instance:

	div {
		@include column(3);
		@include column(6, 'lg');
		@include column(12, 'md');
	}




#### push-left

*Adds margin to the left of a column*

$width: number of columns to fill

$breakpoint: sets number of columns when stated breakpoint is reached

**NOTE**: Similar to column(), push-left() can be used multiple times with different breakpoints

	div {
		@include push-left(3);
		@include push-left(6, 'lg');
		@include push-left(12, 'md');
	}


#### push-right

*Adds margin to the right of a column*

$width: number of columns to fill

$breakpoint: sets number of columns when stated breakpoint is reached

**NOTE**: Similar to column(), push-right() can be used multiple times with different breakpoints

	div {
		@include push-right(3);
		@include push-right(6, 'lg');
		@include push-right(12, 'md');
	}


#### swap

*Swaps the position of this column with the column that comes after it in your HTML*

	div {
		@include swap;
	}


#### row
*Encloses columns in a wrapper prevent other columns from sitting on the same line*


#### hide
*Hides an element at a certain breakpoint*

	div {
		@include hide('sm');
	}


#### show
*Displays an element at a certain breakpoint*

	div {
		@include show('sm');
	}


### Other Notes


- Orderly uses `box-sizing: border-box` to keep grid elements properly aligned. This could potentially affect (mess up) some layouts if Orderly is being added to an already styled page.



