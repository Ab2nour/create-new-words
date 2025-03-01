# Create New Words

Create new words sounding statistically French.

Partially inspired by [Paralogical's Glish language](https://github.com/paralogical/glish) _(make a version of English where every word is only one syllable)_, I highly recommend watching [his YouTube video](https://www.youtube.com/watch?v=sRbcw2sGkJw).

# Concept

Using a list of all most used 20k French words, I built a weighted directed graph $g$ in which every directed edge $(a, b)$ indicates the frequence the letter $b$ appears after the letter $a$.

## Example

The `create_word` function _randomly_ creates a new word.

```py
>>> create_word(g, start_letter="c", length=7)  # g is the graph above-mentioned
"choûter"  # looks French enough
```

## Results

Some words really sound French, like _"choûter"_.

But there are terrible results as well, coming from the method used. Some words have a "ttt" inside them, however there is no such triple "t" in the French language. This comes from the fact that the algorithm does not take into account more than the previous letter. As  a "t" is very frequent after another "t", words with "ttt" arise.
