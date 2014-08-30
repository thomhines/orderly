orderly
=======

**The world's best, easiest, most flexible grid system.**

For examples and more detailed information about Orderly, check out the [Orderly]() site or load up the demo on [CodePen](http://codepen.io/thomhines/pen/iIKcH) to try it out for yourself.


## Features

- Uses both a grid-unit or fraction-based grid system. This means you can set a column to 1/4th the width of the container **OR** 3 grid-units wide of a 12-column grid, and end up with the same column! Plus, you can mix and match your units as much as you want.

- Built with Sass to automate the heavy lifting - keeping your HTML semantic and your CSS clean and light.

- Simple mixins make it a snap to control grid settings, even accross multiple responsive breakpoints.

- Smart default settings make Orderly great right out of the box, but all settings can be easily adjusted and overwritten from within your .scss file.






## How to Use: The Easy Way

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
		@include column(1/4);
	}
	
	.main {
		@include column(3/4);
		
	}

or

	.main {
		@include column(.75);
	}

or

	.main {
		@include column(9);
	}



If you use whole numbers and default settings, orderly assumes you are setting the width of your column in grid-units. Otherwise, it will assume that the column width you set is a fraction of the total width of the container. 

The default grid is 12 grid-units wide.

