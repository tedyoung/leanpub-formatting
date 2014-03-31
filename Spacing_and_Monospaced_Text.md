# Spacing and Monospaced Text

## Embedded spaces

Using:

{line-numbers=off,lang=text}
~~~
Embedded ` spaces ` with regular spaces. 
~~~

Produces:

Embedded ` spaces ` with regular spaces. 

### Notes:

The above won't work as kramdown (the Markdown processor used by Leanpub) considers backticks with spaces on both sides as a "literal" backtick, i.e., it just shows up as a backtick and does not format the text.

----

Using:

{line-numbers=off,lang=text}
~~~
Embedded non-breaking ` spaces ` using the Unicode character `U+00A0`.
~~~

Produces:

Embedded non-breaking ` spaces ` using the Unicode character `U+00A0`.

### Notes:

If the above isn't working (the word "spaces" should be in the monospace font, surrounded by amonospaced non-breaking spaces), then there's a bug in Leanpub, because this used to work.

----

Using:

{line-numbers=off,lang=text}
~~~
Embedded non-breaking `&nsbp;spaces&nsbp;` using the HTML entity.
~~~

Produces:

Embedded non-breaking `&nsbp;spaces&nsbp;` using the HTML entity.

### Notes:

The above doesn't work as the nbsp remains uninterpreted. Strangely enough the back-tick disappears in the output as well.

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



