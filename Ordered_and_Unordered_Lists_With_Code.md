# Chapter 3: Section-level attributes

Turned line-numbering off for an entire section using the "Attributes" feature, this is using: `{line-numbers=off}`...

{line-numbers=off}

Now some code blocks that should *not* have any line-numbering.

E>## Note
E>
E>As of August 27, 2014, this is not working, despite it being documented in the [Leanpub Manual](https://leanpub.com/help/manual#leanpub-auto-attributes).

{lang=bash}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

and

{lang=java}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~

Now some code blocks without the `{lang=xyz}` tag:

~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~

{pagebreak}

This block has `{lang=js}`:

{lang=js}
~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~

With `{lang=text}` (turns off all coloring/formatting):

{lang=text}
~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~

With line-numbering turned back on with `{line-numbers=on}` as a stand-alone attribute...

{line-numbers=on}

Here are some code blocks that should have line numbers.

{lang=bash}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

and

{lang=java}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~

Using `line-numbers=off` attribute per code block...

{lang=bash,line-numbers=off}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

and

{lang=java,line-numbers=off}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~


# Chapter 4: Ordered & unordered lists with code

See [my blog](http://jitterted.com/blog) for more information about this. 

1. First some code with **no line numbers**:

   {line-numbers=off,lang=text}
   ~~~
   code, code, "code" and { code }
   Some other stuff that's code
   ~~~
   Text that belongs to list item #1, but is not code. Note the lack of syntax highlighting for the above code (lang=text).

2. Ice makers have had the show, but not on the truck. Furthermore, the memorial home has been parked for days.

   Note that to properly be another paragraph for point #2, this line has to be indented 3 spaces.

   This is the third paragraph for point #2. I've clearly gone on for too long on this one.

3. Penultimate list item.

3. Oh and remember, the numbers used in ordered lists doesn't matter. I could have used `1.` for each item.


A typically indented unordered list:

* This line has typical spacing, and here I've turned the line-numbers on.

  {line-numbers=on,lang=text}
  ~~~
  for all code do
  if {
    indented code
  } else {
    other code
  }
  ~~~

  * A second-level indentation of above list. This could describe the code listing referencing numbers.

* Second major bullet of the list.

An oddly spaced, unordered list:

*  Here's a list with an extra space after the asterisk. Lines that are not new bullets, but are related to this bullet need to have the same level of indentation.

  Two spaces of indenting for this line won't work, it has to match the indentation of the first list item.
  ~~~
  Even for fenced code blocks, this doesn't work as the indentation doesn't match.
  ~~~

*  Next bullet, please, but really this is considered a new list.

Correct way to do indents with oddly spaced lists:

*    This line is indented pretty far and has four spaces in between the * and the first non-space character.

     To have this paragraph be connected to the first bullet, you need to line up this new paragraph line with the above, two spaces here won't work, you'll need five. And it MUST have a blank line above it (though a blank line below is optional, because the asterisk at the beginning of the next line will tell the parser that it's another item).
*    This second bullet also has the same number of additional spaces before the first non-space character.

### Putting it all aside

Let's put some of the above in an aside:

G> ### A 'G' Aside
G>
G> 1. First numbered item (1)
G> 1. Second numbered item (2)
G>
G>    <<[Code inside the aside for item #2](code/aside-code-item.js)
G>  
G>    Text that explains the code above (indented 3 spaces to line up with the `S` in the word Second in the second item above).
G>
G> 1. Continuation of numbered items (3)

Again, the key here is to ensure that everything is indented appropriately: text that lines up with an item are considered part of that item.

{pagebreak}

## Formatting included code

The section format instructions (e.g., `{line-numbers=off,lang=text}`) can also 
be applied to included sections of code, i.e., external files that are included
using the `<<(filename)` syntax. For example, this:

{line-numbers=off,lang=text}
~~~
{line-numbers=off,lang=text}
<<(javascript/Gruntfile.js)
~~~

### Produces:

{line-numbers=off,lang=text}
<<(Gruntfile.js)

