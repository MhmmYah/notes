# This is a rundown of simple github flavoured markdown

# H1 header
## H2 header
### H3 header

\ <= placed before markdown syntax to ignore
newline\
**bold text**\
*italicized text*\
~~Strike through~~\
This<sub>subscripts</sub>Words\
This<sup>superscripts</sup>Words\
Adding emojis :joy:


> block quote:\
> This is the Loreum Ipsum stuff that noone reads

1. List
2. with
3. Order

- List
- without
- order

`System.out.println("Code");`\
`returns inline code`

Horizontal Rule (Interesting, it makes it a H2)
---

[link](https://www.google.com)\
[link again](https://github.com)

![Image info](./MDImages/GrandRapids.png)

|Table | And stuff|
|-|:-:|-:|
|Item 1 | asdf | whee |
|Item 2 | asdf2 | whoo |
|Lines necessary| \|\-\|\-\| | yah |  

```
FencedCode = 
{
    "this" : "is a JSON",
    "this2" : "is more JSON"
}
```

Adding footnotes are easy too. [^1]
[^1]: Match it with the right number.

### Heading ID {#this-id-will-show-in-url-bar-instead-of-Heading-ID}

Lets define
: This is the definition

- [x] Add some tasks
- [ ] must contain either space
- [ ] or contain an 'x'