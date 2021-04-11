# Regex

## C#

### Match method or property declarations

`(public|private).*.+?(?=[\{\(])`

- Assumption is that declarations use either `public` or `private`
- Uses this [SO answer](https://stackoverflow.com/a/7124976/3769526) to not include `{` or `(` in the match.

### Match the whole sentence containing a given word

`word` = lorem

`(?<=\.\s)[^\.]*?lorem.*?\.`

### Match the whole sentence containing given words in the following order
Donec venenatis vestibulum quam, nec blandit urna vulputate eget. <mark>Praesent egestas, metus vitae blandit maximus, justo **lorem** maximus sem, eu dapibus mi dui **quis** ligula.</mark> Cras et turpis posuere, vestibulum dui id, euismod velit.

`(?<=[\s])[^\.]*?lorem[^\.]*quis.*?\.`

### Match the whole sentence containing given words in no order
- This still needs work as it will match even if it just sees two instances of **lorem** or **quis**

`(?<=[\s])[^\.]*?(lorem|quis)[^\.]*(lorem|quis).*?\.`
