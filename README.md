orderly
=======

**The world's best, easiest, most flexible grid system.**

Orderly is a simple, responsive grid system built for Sass. Orderly lets you create you grid how you want: fluid or fixed, fractional column or sub-column parts. And you're not limited to a set of predefined column widths—you can choose whatever column widths you'd like on the fly.

Plus, Orderly uses Sass to keep your CSS simple, your HTML semantic, and give you an unbelievable amount of control over the layout of your site. Just add a line or two to your stylesheet and Orderly will do the rest.


- [Official Site](http://projects.thomhines.com/orderly/)
- [Interactive Demo](http://codepen.io/thomhines/pen/iIKcH) on [CodePen](http://codepen.io/)






## How to Use

Check out the example below to see how simple it is to get your grid started with Orderly. And head over to [Orderly](http://projects.thomhines.com/orderly/) site to see tons more settings and options.

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



If you use whole numbers and default settings, orderly assumes you are setting the width of your column in sub-columns. Otherwise, it will assume that the column width you set is a fraction of the total width of the container. The default sub-column grid is 12 sub-columns wide.

Not sure how to use Sass in your project? Check out [cinch](projects.thomhines.com/cinch/).
