# Section-level attributes

Turned line-numbering off with {line-numbers=off}...

{line-numbers=off}

{lang=bash}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

{lang=java}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~

No lang...

~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~

With lang=js:

{lang=js}
~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~

With lang=text:

{lang=text}
~~~
[
  {
    "caption": "Show Me",
    "command": "show"
  }
]
~~~


Turned line-numbering on with {line-numbers=on}...

{line-numbers=on}

{lang=bash}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

{lang=java}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~

Using line-numbers attribute per code block...

{lang=bash,line-numbers=off}
    $ sudo wget -qO- https://example.com/gpg | apt-key add -

{lang=java,line-numbers=off}
~~~
  public class MyTests {
    @Test
	public void someTestMethod() {
	  // test code here
	}
  }
~~~


# Ordered & unordered lists with code

See [my blog](http://jitterted.com/blog) for more information about this. 

1. First some code with **no line numbers**:

   {line-numbers=off,lang=text}
   ~~~
   code, code, "code" and { code }
   Some other stuff that's code
   ~~~
   Stuff that belongs to list item #1, but is not code. Note the lack of syntax highlighting for the above code (lang=text).

2. Ice makers have had the show, but not on the truck. Furthermore, the memorial home has been parked for days.

   Note that to properly be another paragraph for point #2, this line has to be indented 3 spaces.

   This is the third paragraph for point #2. I've clearly gone on for too long on this one.

3. That's all folks.

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

