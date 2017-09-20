# how-to-d3

## Before you write a line of D3 code, read this...

### The Mental Model for D3

These five concepts are the most important part of learning D3:

1. D3 is like JQuery
2. D3 elements are SVGs. SVGs are like divs that have funny shapes. You can handle this.
3. You are the god/godess of SVGs. Whatever you touch springs into existence.
4. Everything has a relationship to the axes. EVERYTHING.
5. D3's main job is to automate spacing out your data along the axes

#### 1. D3 is like JQuery
Think back to the basics of JQuery. Almost everything you do begins with selecting
an element that's already in the DOM and doing something to it, or constructing
a new element in your JavaScript and then appending
it to the DOM. (If you're not familiar with the DOM or JQuery, read [this]().)

D3 is A *LOT* like JQuery. You select or create elements, then change their
properties to match some part of the data set you want to visualize. Instead of
selecting a div and changing the text font to Comic Sans, you're selecting shapes
and changing their color or position.

`<example jquery>`
`<example d3>`

#### 2. D3 elements are SVGs. SVGs are like divs that have funny shapes. You can handle this.

`<example div>`
`<example svg>`

See the similarities? Some of the attributes have different names, like `fill`
instead of `background-color`, but this is familiar territory.

#### 3. You are the god/godess of SVGs. Whatever you touch springs into existence.

Here's a major difference with D3 compared to JQuery. When you select something
in D3, it will update it if it exists, and create it if it doesn't.

When you first make a chart, it will be empty! So how could you select something
on it? Repeat after me. You the god/goddess of SVGs and whatever you touch
comes into existence within your JavaScript. Then, with just a few more steps,
you can make the invisible visible. You reveal your creation to the user by adding
it to the DOM or changing the attributes of shapes that the user can already see.

You are powerful. You are mighty. You will build things that have never been
done before. Hold onto these sentiments. They will carry you
through the moments when this library makes you feel like an total idiot.

#### 4. Everything has a relationship to the axes. EVERYTHING.

After you wrap your head around what I mean by this statement, you will know
*WHAT* you need to do and *WHY* you need to do it. You won't know *HOW*, but that's
what API docs, Google, and tutorials are for. This is the explanation you
won't find anywhere else.

Get a piece of paper. It's time to draw. We're going to make
a scatter plot, and justify every stroke of the pen.
The purpose of the drawing is to answer the questions, "Where do
the shapes go and how do I know to put them there?" D3 does a LOT of the math
and positioning for you, so don't worry! However, in order to understand what's
going on and which methods to use, you need to have a base level understanding
of the raw elements.

First draw a big rectangle that will hold the graph. This is our SVG canvas,
the space where we will position some shapes. It has a height and width that
is probably tied to the overall page layout.

<pic>

Now draw the Y (or vertical) axis. How tall is it? Probably close to the
height of the SVG itself. How much padding should be between the axis and the
edge of the SVG? You'll need to leave enough space to fit the label in there too.
What is the scale? It probably ought to start at 0 and go to the maximum
y coordinate of a data point, at least.

<pic>

Next draw the X (or horizontal) axis. Similar to the Y axis, it should be about
as wide as the SVG canvas. There needs to be a little padding between the
edge of the SVG and the X axis. What's the scale? It should go from 0 to the
maximum x coordinate of a data point, at least.

<pic>

We need axes labels. Let's label the x and y axes first. A label is just text
that has a specific orientation and location on the chart. The y axis label is
usually rotated and then centered along the height of the y axis. To be "centered"
means that its position is roughly the height of the axis divided by 2. It has some
padding in a horizontal direction. It has a font
size, color, and font family. The x axis label is easier. No rotation, and it's
centered along the width of the x axis (axis width divided by 2).
It has a little bit vertical padding.

<pic>

Time for tic marks. How do you know where to put them? They should be evenly
spaced between the maximum and minimum of each axis. You also have to
choose how many tick marks there are. The number of tick marks can be different
on each axis.

<pic>

Let's label the tick marks. The labels are the overall length of the axis
divided by the spacing you want to have. The x tick marks are positioned evenly
spaced along the x axis, with a little padding in the y direction.
Likewise, the y tick marks are positioned evenly
spaced along the y axis, with a little padding in the x direction.

<pic>

FINALLY let's add a data point. Where does it go? The data has it's own
concept of x and y. What does that map to? Not inches or cm on the paper. Not
pixels on a screen. No, the x and y of a data point maps to the x and y of our axes.

<pic>

And just for fun, let's pretend that when you hover over a data point, some text
should appear that says the xy coordinates. How is it positioned? Well, it's pretty
close to the x and y coordinates of the data point. We just shift it over a
to the left. Subtract a little from the x coordinate of the data point in order to
establish some horizontal padding.

<pic>

You should go through this exercise every time you start a new kind of chart.

#### D3's main job is to automate spacing out your data along the axes



#### Conclusion


## Prerequisites

You will need the following things properly installed on your computer.

* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/) (with NPM)
* [Ember CLI](https://ember-cli.com/)
* [PhantomJS](http://phantomjs.org/)

## Installation

* `git clone <repository-url>` this repository
* `cd how-to-d3`
* `npm install`

## Running / Development

* `ember serve`
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)

### Deploying

Specify what it takes to deploy your app.

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
