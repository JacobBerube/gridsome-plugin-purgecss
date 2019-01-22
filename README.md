# gridsome-plugin-purgecss

This plugin will add [Purgecss](https://www.purgecss.com) to your
[Gridsome](http://gridsome.org) project.

To use this plugin, add the following to your `gridsome.config.js`.

```javascript
plugins: [
  {
    use: 'gridsome-plugin-purgecss',
	// default options, the following will be included if you don't provide anything
	options: {
	  content: [
        './src/**/*.vue',
        './src/**/*.js',
        './src/**/*.jsx',
        './src/**/*.md'
      ],
      extractor: TailwindExtractor,
      extensions: ['vue', 'js', 'jsx', 'md']
	}
  }
]

// default extractor
class TailwindExtractor {
  static extract(content) {
    return content.match(/[A-z0-9-:\/]+/g) || []
  }
}
```
