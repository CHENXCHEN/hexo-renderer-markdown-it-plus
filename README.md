# hexo-renderer-markdown-it-plus

This renderer plugin uses Markdown-it as a render engine on Hexo.

This renderer plugin is forked from [hexo-renderer-markdown-it](https://github.com/hexojs/hexo-renderer-markdown-it/blob/master/lib/renderer.js).
Add some plugin and support thirid-part `markdown-it` plugin.

## Main Features
+ Support for Markdown
+ Extensive configuration
+ Faster than the default renderer | hexo-renderer-marked
+ [sub](https://www.npmjs.com/package/markdown-it-sub), `H~2~0` H<sub>2</sub>0
+ [sup](https://www.npmjs.com/package/markdown-it-sup), `x^2^` x<sup>2</sup>
+ [ins](https://www.npmjs.com/package/markdown-it-ins), `++Inserted++` <ins>Inserted</ins>, `~~Del~~` <s>Del</s>
+ [Katex](https://www.npmjs.com/package/markdown-it-katex), [referer](https://github.com/Khan/KaTeX)
+ [emoji](https://www.npmjs.com/package/markdown-it-emoji), [referer](https://www.webpagefx.com/tools/emoji-cheat-sheet/)
+ [toc&anchor](https://www.npmjs.com/package/markdown-it-toc-and-anchor)
+ [deflist](http://pandoc.org/MANUAL.html#definition-lists)
+ [abbr](https://www.npmjs.com/package/markdown-it-abbr)
+ [footnote](https://www.npmjs.com/package/markdown-it-footnote)
+ [mark](https://www.npmjs.com/package/markdown-it-mark)

## Install
```shell
npm un hexo-renderer-marked --save
npm i hexo-renderer-markdown-it-plus --save
```

## Options
Configuring the renderer is a fairly simple task because all the settings are in the main hexo `_config.yml` file. You just need to open it in your favourite text editor and write down your configuration.

```yml
markdown_it_plus:
    highlight: true
    html: true
    xhtmlOut: true
    breaks: true
    langPrefix:
    linkify: true
    typographer:
    quotes: “”‘’
```

## Katex

Katex plugin is enable default, if you want to disable it, skiped this paragraph.
if you want to use katex, you must add this css style into your website:
`https://cdn.bootcss.com/KaTeX/0.7.1/katex.min.css`

## Advanced Options
The plugins of markdown-it above is enable default, if you want to disable it, see below configuration:
```yml
markdown_it_plus:
    highlight: true
    html: true
    xhtmlOut: true
    breaks: true
    langPrefix:
    linkify: true
    typographer:
    quotes: “”‘’
    plugins:
        - plugin:
            name: markdown-it-mark
            enable: false
```
Default enable plugins:
`markdown-it-emoji`
`markdown-it-sub`
`markdown-it-sup`
`markdown-it-deflist`
`markdown-it-abbr`
`markdown-it-footnote`
`markdown-it-ins`
`markdown-it-mark`
`markdown-it-katex`
`markdown-it-toc-and-anchor`

## Add other `markdown-it` Plugins
If you want to add a plugin name `markdown-it-something`:  

1.Install this plugin
```javascript
npm install markdown-it-something --save
```

2.config main hexo `_config.yml`
```yml
markdown_it_plus:
    # ...
    plugins:
        - plugin:
            name: markdown-it-something
            enable: true
            options:
                # this is plugin option
```
