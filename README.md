# Verovio Task

This task will help you understand how to use the Verovio toolkit.
The goals are as follows:

1. Gain familiarity with basic commands of the Verovio toolkit;
2. Use Verovio as a renderer to generate an SVG from an MEI document;
3. See how the representation of the document in the DOM reflects the structure
of the MEI document itself; and
4. Manipulate the SVG rendering of the MEI document.

This will involve working with some HTML, some Javascript, and some Git.

## Getting Started

First, clone this repository using `git clone https://github.com/JRegimbal/Verovio-Task.git` from the command line.
This will create a copy of the repository in a directory called `Verovio-Task` in your current working directory (i.e. wherever you called the command from).

***
*If you're unfamiliar with Git, you may want to keep [this cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf) handy and take a look at [the guide](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) when you have a chance.*

*If you're unfamiliar with JavaScript, you might find [these guides helpful](https://developer.mozilla.org/en-US/docs/Web/javascript)*.
***

Open the file `index.html` in an editor and in your browser of choice.
Notice that the file contains a script stub. You will fill this in during this
task.

## Part 1: Using the Engraver

In `index.html`, look at the stub. It should look like this:
```javascript
var vrvToolkit = new verovio.toolkit();
vrvToolkit.setOptions({font: 'Bravura'});
$.get('https://ddmal.github.io/Neon2/mei/CF-018.mei', (data) => {
/* ENTER USER CODE HERE */

/* END OF USER CODE */
}, 'text');
```
If you're unfamiliar with JavaScript, this is what happens: an instance of the
Verovio Toolkit is created on the first line. We then set the font to be Bravura
on the second.
Finally we use JQuery to get the contents of an MEI file.

In that line, the contents are manipulated using a *callback* function. The
function takes `data` as an argument, which is actually the contents of the
MEI file being fetched. A callback function only runs when an action &mdash; in
this case getting the contents of an external file &mdash; completes.

In this stub, fill in the contents of the callback function in order to render
an SVG with the Verovio toolkit (`vrvToolkit`) and display it on the page.

Here's a hint: you'll need to use the `renderData` function of the toolkit!

***
**Resources:**

* For information on the Verovio toolkit, look [here](https://www.verovio.org/javascript.xhtml).
* For information about SVGs in HTML and Javascript, [the MDN docs might be useful](https://developer.mozilla.org/en-US/docs/Web/SVG).
***

## Part 2: An SVG is just part of the DOM!

A black and white rendering is just so boring!
We can use <span style="color:red">c</span><span style="color:orange">o</span><span style="color:yellow">l</span><span style="color:green">o</span><span style="color:blue">u</span><span style="color:purple">r</span>
to easily point out different musical elements.
This can be very useful in visualizing different structures in, say, an editor.
This is also fairly easy to do since SVG is an XML-based standard. If you've
ever set the color of text in HTML, changing the color of an SVG element will
be familiar.

This time, try and make every custos <span style="color:blue">blue</span> and
every clef <span style="color:red">red</span>.

Hint: use the browser to inspect the SVG. See if there's anything all custos and
clefs have in common...

Also, this is a custos: ![Custos](res/custos.png)

## Part 3: Getting Information

In the first staff, print the pitch of every part of a neume to the command line.
Thankfully, Verovio makes it pretty easy to get information on the loaded
file. Unique IDs are assigned to all elements internally in Verovio.
Conveniently these same IDs are assigned to the corresponding SVG tags as the
attribute `id`.

Hint: use `vrvToolkit.getElementAttr`.

## Checking your work

Later on, I'll add a solution key to the repository so you can see how I completed
each part. You can also [fork the repository](https://help.github.com/en/articles/fork-a-repo)
and [create a pull request](https://help.github.com/en/articles/about-pull-requests)
so I can see what you did, but that part is optional.
