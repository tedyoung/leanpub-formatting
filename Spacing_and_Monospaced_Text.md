# Chapter 2: Spacing and Monospaced Text

The examples here are formatted such that the actual text that Leanpub will format is first in monospace and the results are formatted by Leanpub, i.e., if you copied the monospaced text and pasted it into a Leanpub file, you'd see the text under "Produces:".

## Embedded spaces

### Using normal spaces:

{line-numbers=off,lang=text}
~~~
Embedded ` spaces ` with regular spaces. 
~~~

### Produces:

Embedded ` spaces ` with regular spaces. 

### Notes:

The above won't work as kramdown (the Markdown processor used by Leanpub) considers backticks with spaces on both sides as a "literal" backtick, i.e., it just shows up as a backtick and does not format the text.

{pagebreak}

### Using Unicode non-breaking space:

{line-numbers=off,lang=text}
~~~
Embedded non-breaking ` spaces ` using the Unicode character `U+00A0`.
The space here after the first backtick is a non-breaking space: ` -test` so
this should show up where the space and the *-test* is monospaced.
~~~

### Produces:

Embedded non-breaking ` spaces ` using the Unicode character `U+00A0`.
The space here after the first backtick is a non-breaking
space: ` -test` so should show up where the space and the *-test* are monospaced.

### Notes:

If the above isn't working (the word "spaces" should be in the monospace font, surrounded by monospaced non-breaking spaces), then there's a bug in Leanpub, because this used to work.

{pagebreak}

### Using a normal space only on one side of the backtick:

{line-numbers=off,lang=text}
~~~
` -test` normal text `monospaced text` and` more monospaced text `with
extra space on the side.
~~~

### Produces:

` -test` normal text `monospaced text` and` more monospaced text `with
extra space on the side.

### Notes:

This works fine because there's no backticks that are surrounded by spaces.

{pagebreak}

### Using the nbsp entity:

{line-numbers=off,lang=text}
~~~
Embedded non-breaking `&nsbp;spaces&nsbp;` using the HTML entity.
~~~

### Produces:

Embedded non-breaking `&nsbp;spaces&nsbp;` using the HTML entity.

### Notes:

The above doesn't work as the `nbsp` remains uninterpreted. Strangely enough the backticks disappear in the output as well.

{pagebreak}

## Fencing for monospaced plain text:

{line-numbers=off,lang=text}
~~~
a monospace text
  another text
    a third line of text
~~~

## Using 4-space indents for pre-formatted text:

    a monospace text
    another text
    another text

### Notes:

Since fencing isn't used, the book's defaults for line-numbering (in this case "on") applies.

{pagebreak}

## Highlighting Code

Sometimes you want to highlight (emphasize) some lines of code, or whatever your monospaced text is. You can do that using the `leanpub-start-insert` and `leanpub-end-insert` as code comments. For example:

A>`# leanpub-start-insert`  
A>`$ rackup -h`  
A>`# leanpub-end-insert`  
A>&nbsp;&nbsp;`Usage: rackup [ruby options] [rack options] [rackup config]`  

will produce:

{line-numbers=off,lang=text}
~~~~
# leanpub-start-insert
$ rackup -h
# leanpub-end-insert
  Usage: rackup [ruby options] [rack options] [rackup config]
~~~~

{pagebreak}

## Forcing text to start on a new line

### Using two spaces at the end of a line:

~~~
This is the first line.∙∙
This is the second sentence.
~~~

A> Note that the boxes indicate space characters, i.e., you'll need *two* spaces at the end of the line where you want to force a line-break.

### Produces:

This is the first line.  
This is the second sentence.

