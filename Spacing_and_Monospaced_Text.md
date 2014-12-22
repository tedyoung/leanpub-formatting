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

## Backtick shortcut

You can also use the backtick markup, e.g., this:

{line-numbers=off,lang=text}
~~~~
```console
$ sudo ls -alFh | grep G | sort

total 28
drwxrwxr-x 5 tom tom 4096 Sep 17 18:22 .
drwxr-xr-x 3 tom tom 4096 Aug 19 23:02 ..
drwxrwxr-x 8 tom tom 4096 Sep 17 18:22 .git
-rw-rw-r-- 1 tom tom  142 Aug 20 23:49 LICENSE.md
drwxrwxr-x 4 tom tom 4096 Sep 17 18:22 manuscript
-rw-rw-r-- 1 tom tom  956 Aug 20 23:56 README.md
drwxrwxr-x 2 tom tom 4096 Sep  8 20:00 user-stories
```
~~~~

### Produces:

```console
$ sudo ls -alFh | grep G | sort

total 28
drwxrwxr-x 5 tom tom 4096 Sep 17 18:22 .
drwxr-xr-x 3 tom tom 4096 Aug 19 23:02 ..
drwxrwxr-x 8 tom tom 4096 Sep 17 18:22 .git
-rw-rw-r-- 1 tom tom  142 Aug 20 23:49 LICENSE.md
drwxrwxr-x 4 tom tom 4096 Sep 17 18:22 manuscript
-rw-rw-r-- 1 tom tom  956 Aug 20 23:56 README.md
drwxrwxr-x 2 tom tom 4096 Sep  8 20:00 user-stories
```

{pagebreak}

## Forcing text to start on a new line (line breaks)

Normally multiple lines of text are treated as one long line, but sometimes
you want an explicit line break, without starting a new paragraph (i.e., inserting
a blank line). There are two ways to do this, with the double-backslash method
being preferred over the double-space method as it's easier to see and won't
accidentally get deleted during reformatting as spaces can (hat tip to Jay Fields for that).

### Use case

Formatting an address using blank lines (to create new paragraphs) like this:

```text
First M. Last

123 Some Street

Cityname, ST 00000-1234
```

would look like:


First M. Last

123 Some Street

Cityname, ST 00000-1234


However, with forced line breaks, it would look like:

First M. Last \\
123 Some Street \\
Cityname, ST 00000-1234

Which is nicer.

### Using two backslashes at the end of a line:

```text
This is the first line.\\
This is the second line.
```

#### Produces:

This is the first line.\\
This is the second line.



### Using two spaces at the end of a line:

~~~
This is the first line.∙∙
This is the second line.
~~~

A> Note that the boxes indicate space characters, i.e., you'll need *two* spaces at the end of the line where you want to force a line-break.

#### Produces:

This is the first line.  
This is the second line.

{pagebreak}

### Multi-line code/monospaced text in an aside

#### This content:

{line-numbers=off,lang=text}
```
A>`git fetch origin master`  
A>`git reset –-hard origin/master`  
A>`git pull origin master`  
```

#### Produces

A>`git fetch origin master`  
A>`git reset –-hard origin/master`  
A>`git pull origin master`  
