# vuepress-plugin-sitemap

Sitemap generator plugin for vuepress.

## Install

* Yarn

  ```sh
  yarn add vuepress-plugin-sitemap
  ```

* NPM

  ```sh
  npm install vuepress-plugin-sitemap
  ```

## Usage

### Vuepress v1.x

```js
// .vuepress/config.js
module.exports = {
  plugins: {
    'sitemap': {
      hostname: 'https://pake.web.id'
    },
  }
}
```

### Vuepress v0.x

There's no plugin supported with Vuepress v0.x so we need to run it after the build process manually (or with npm `prebuild` script).

1. Manual

   ```sh
   ./node_modules/.bin/vuepress -d "dist"
   ./node_modules/.bin/vuepress-sitemap -h "https://pake.web.id" -d "dist"
   ```

2. NPM Script

   ```ts
   {
     scripts: {
       build: "vuepress build docs -d dist",
       prebuild: "vuepress-sitemap -h https://pake.web.id -d dist"
     }
   }
   ```

## Options

```yml
hostname:
  type: string
  required: true
  default: null
  description: website root url
  example: https://pake.web.id

outFile:
  type: string
  required: false
  default: sitemap.xml
  description: sitemap file name
  example: sitemap.txt

urls:
  type: array
  required: false
  default: [],
  description: custom urls to append
  example: [
    { url: '/place', changefreq: 'montly'}
  ]
```

*Note: Other options of [sitemap](https://npm.im/sitemap) can be used.*

## Todo

* [ ] Localization

## Related Plugins

* [Server Push Links Generator](https://github.com/ekoeryanto/vuepress-plugin-server-push)
