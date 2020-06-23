To view the wiki as it was from archive.org:

https://web.archive.org/web/20160324082102/http://calculus.seas.upenn.edu/?n=Main.HomePage

Formatting Notes:

To find/replace dollar signs for kramdown, use:

Replace \(\$|\$\) with $$$$
Also, replace \(:latex:\)( ?\\\[)? with $$$$\n
Finally, replace ( ?\\\[)?\(:latexend:\)

This may miss some standalone \] markers,
Clean them up with \\\]\s*

The goal of this is to try to make standalone blocks of $$stuff$$ with the $$ on their own lines, like

$$
stuff
$$

This will make it easier for simple parsers to change $$ back into \[ stuff \] or \(stuff \) as needed outside of kramdown


## Examples

Examples would probably normally be given a header level of h4, but this does not stand out very much, so instead we simply bold the word Example. This can
be automated by doing a find on ^\s*Example\s*$ and replace with **Example**

To find/replace toggleable answers with buttons, use:

\(:toggle .*(box\w+).*\)

and replace with

<button class="toggle" data-box="#$1">Answer</button>

Then put

{: id="box2" class="answer-hidden"}

After the answer block. If the answer block has multiple block components (like an equation plus a paragraph of explanation, or multiple paragraphs), you can either insert explicit line breaks by ending a line with two spaces, or by using an html <br /> break, or wrap the blocks in a div. In this last case, you can get rid of the {: ...} attributes and just put them directly in the div. Be sure to also include {::options parse_block_html="true" /} if you do this.


For a standalone equation that you want to appear inline as its own paragraph, but kramdown makes into a block, place &#8203; (a zero-width space) after it, like

$$y = f(x)$$&#8203;

For a standalone equation that you want to appear as a block but kramdown makes into inline because it is at the end of a div, just add a blank line before the closing tag, like

<div>
This is a proof:

$$
\begin{align}
...
\end{align}
$$

</div>