# Regex

## C#

### Match method or property declarations

`(public|private).*.+?(?=[\{\(])`

- Assumption is that declarations use either `public` or `private`
- Uses this [SO answer](https://stackoverflow.com/a/7124976/3769526) to not include `{` or `(` in the match.