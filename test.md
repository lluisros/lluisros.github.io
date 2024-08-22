
# README #

In this file I test various markup options of the markdown language. Emphasis is on the markdown version of Bitbucket, which is limited.

To produce separate lines, end the preceding line with two spaces:

Coordinator: Caius Iulius Caesar  
Instructor: Caius Ludovicus

## Lists ##

Here's a bulleted list:

* Theory lecture notes
* Exercises (mixed with the theory)
* Lab miniprojects
* Exams

A numerated list:

1. Theory lecture notes
2. Exercises (mixed with the theory)

## Links ##

* [Learn Markdown](https://bitbucket.org/tutorials/markdowndemo)

## Blocks ##

A blockquote:

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.


A code block delimited with 4 spaces:

    Hello, I'm a code block. I must start with 4 spaces, or start and end with ```

A code block delimited with with ```

```
def wiki_rocks(text): formatter = lambda t: "funky"+t return formatter(text) 		
```

## Tables ##

Common mardown interpreters will understand the HTML syntax:

<table>
<thead>
<tr>
  <th>First Header</th>
  <th>Second Header</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Content Cell</td>
  <td>Content Cell</td>
</tr>
<tr>
  <td>Content Cell</td>
  <td>Content Cell</td>
</tr>
</tbody>
</table>

Bitbucket only understands the simple markdown syntax:

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

which only allows producing simple tables like the one shown.