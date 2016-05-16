pug-bunto-plugin (previously jade-bunto-plugin)
=================================================

Converter Plugin that brings Pug support to the [Bunto blog-aware, static site generator](https://bunto.github.io/).

## HOWTO

 1. Install Pug with NPM. e.g. `$ npm install pug -g`
 1. Place the `pug.rb` file into your Bunto installation under `_plugins/` 
 1. All static pages and posts ending in the extension `.pug` are now processed through Pug automatically.
 1. Layouts need special treatment, see below.

## Applying Pug to Layouts

Unfortunately Bunto doesn't yet allow plugins to pre-process layout files before further processing.  To write your layouts in Pug, you therefore have to render them externally.  Fortunately this only needs to be done frequently for a small period of time, during layout development.

During layout development, we recommend:

 1. Create a `_layouts/pug/` folder where you will place your "pre-rendered" Pug source.
 2. Create a `Makefile` or shell script to execute the Pug compile-and-watch command: `pug -w -o ../ *.pug`
 3. In another terminal, simultaneously run your Bunto builds: e.g. `bunto serve -w`

## License

See [LICENSE](https://github.com/bunto/pug-bunto-plugin/blob/master/LICENSE).

