# Homepage

## Admonition Examples

### Collapsible admonition

??? abstract

    This is a collapsible abstract admonition block

### Collapsible admonition with nested note

??? abstract "Expand Me!"

    This is a collapsible abstract admonition block

    !!! note
        This is a test nested note admonition

    Test text after the nested note.

### Custom Collapsible admonition

??? cmd

    This is a collapsible custom admonition block


## Code Annotation Examples

### Codeblocks

Some `code` goes here.

### Plain codeblock

A plain codeblock:

```
some code here
def myfunction()
// some comment
```

#### Code for a specific language

Some more code with the `json` at the start:

``` json
{
  "name": "apple",
  "color": "red"
}
```

#### With a title

``` json title="fruit.json"
{
  "name": "apple",
  "color": "red"
}
```

#### With line numbers

``` json linenums="1"
{
  "name": "apple",
  "color": "red"
}
```

#### Highlighting lines

``` json hl_lines="2 3"
{
  "name": "apple",
  "color": "red"
}
```

## Icons and Emojis

:smile:

:fontawesome-regular-face-laugh-wink:

:fontawesome-brands-twitter:{ .twitter }

:octicons-heart-fill-24:{ .heart }