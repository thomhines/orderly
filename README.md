orderly
=======

**The world's best, easiest, most flexible grid system.**

Orderly is a simple, responsive grid system built for Sass. Orderly lets you create you grid how you want: fluid or fixed, fractional column or sub-column parts. And you're not limited to a set of predefined column widths—you can choose whatever column widths you'd like on the fly.

Plus, Orderly uses Sass to keep your CSS simple, your HTML semantic, and to give you an unbelievable amount of control over the layout of your site. Just add a line or two to your stylesheet and Orderly will do the rest.


- [Official Site](http://projects.thomhines.com/orderly/)
- [Interactive Demo](http://codepen.io/thomhines/pen/jIiaz) on [CodePen](http://codepen.io/)






## How to Use

Check out the example below to see how simple it is to get your grid started with Orderly. And head over to the official [Orderly](http://projects.thomhines.com/orderly/) site to see tons more settings and options.

HTML:

	<body>
		<div class="sidebar">
			<h1>Sidebar Content</h1>
		</div>
		<div class="main">
			<h1>Main Content</h1>
		</div>
	</body>


SCSS:

	@import 'orderly';

	body {
		@include container();
	}

	.sidebar {
		@include column(25%);
	}
	
	.main {
		@include column(75%);
		
	}

or

	.main {
		@include column(3/4);
	}

or

	.main {
		@include column(.75);
	}

or even

	.main {
		@include column(9);
	}



If you use whole numbers and default settings, orderly assumes you are setting the width of your column in sub-columns. Otherwise, it will assume that the column width you set is a fraction of the total width of its container. Orderly uses a 12 sub-column grid by default.

Not sure how to use Sass in your project or you don't have node.js installed?? Check out [cinch](projects.thomhines.com/cinch/).



## Changes

#### v.1.1

- Added "Width Indicator" option to make figuring out breakpoints a teeny bit easier
- Changed format of mixin breakpoint arguments to use min and max values instead of just one breakpoint, and for range to be inclusive when using named breakpoints