# Chapter 5: Special Characters

Sometimes you'll want to use characters, such as the hash symbol `#` that have other meanings in Markdown. In most circumstances, putting a backslash before the special character works just fine. Putting the special character inside of a monospaced span, i.e., surrounded by backticks, also generally works. What follows are some special cases where a backslash doesn't work.


## Using the hash (#) as the last character in a heading

If you want a hash character in a heading, normally that works fine, e.g.:

{lang=text,linenos=off}
~~~
## We're #1
~~~

which produces:

>## We're #1

However, if you need the hash to be the last character, such as:

{lang=text,linenos=off}
~~~
## C#
~~~

this won't work and you'll only see:

>## C#

Trying the backslash escape works in when it's embedded inside of other text, e.g.:

{lang=text,linenos=off}
~~~
#\#1 of 3
~~~

produces:

>#\#1 of 3

{pagebreak}

but in a header like this:

{lang=text,linenos=off}
~~~
## C\#
~~~

it does not work and produces:

>## C\#

because the trailing hash is stripped before the backslash can take effect (the Markdown parser considers it to be part of the header markup). Adding whitespace at the end might help, e.g. (where the box indicates a normal space):

{lang=text,linenos=off}
~~~
## C#∙
~~~

produces:

>## C# 

but that doesn't work because the space also gets trimmed. How about two spaces at the end, since that works in other situations (the boxes indicate spaces):

{lang=text,linenos=off}
~~~
## C#∙∙
~~~

Produces:

>## C#  

Which doesn't work either.

### Solutions

### #1: Force a space at the end

Since a regular whitespace didn't work, how about the "no break" space, i.e.:

{lang=text,linenos=off}
~~~
## C#&nbsp;
~~~

Produces:

>## C#&nbsp;

***Success!***

### #2: Close ATX style

Are there other ways to solve this problem? Yes. Let's "close" the ATX style (ATX style is the use of the hashes to indicate section levels):

{lang=text,linenos=off}
~~~
## C\# ##
~~~

Produces:

>## C\# ##

Another success.

### #3: Alternate heading syntax

Instead of suing the ATX style (double-hash) to indicate a section, use the alternate syntax of underlining the text:

{lang=text,linenos=off}
~~~
C#
--
~~~

Which produces:

>C#
>--

### #4: Monospaced hash

You can also surround the hash with the backtick that marks the text as monospace. Though this has a different look for the hash that you may or may not like. Do this:

{lang=text,linenos=off}
~~~
## C`#`
~~~

Which produces:

>## C`#`

### Conclusion

So there you have it, four solutions to the problem. It's unfortunate that it takes a deeper understanding of how the Markdown syntax is parsed to workaround these issues, but there's usually a solution if you try enough different things.

{pagebreak}

## Dashes: en and em

To produce an "en-dash" (i.e., a dash that's as wide as the letter "N"), you put two dashes in a row. For a wider "em-dash" ("M" is wider than "N"), you put three dashes in a row. For example:

{lang=text,linenos=off}
~~~
This text has two dashes -- separating this phrase -- in it to produce an
"en-dash", but has three --- three! --- dashes here to create an "em-dash".
~~~

### Produces:

This text has two dashes -- separating this phrase -- in it to produce an
"en-dash", but has three --- three! --- dashes here to create an "em-dash".
