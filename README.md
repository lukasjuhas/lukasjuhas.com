# itsluk.as
My little pice of internet build on my [web-starter](https://github.com/lukasjuhas/web-starter) using my [api](https://github.com/lukasjuhas/api.itsluk.as) among others.

## Server Configuration
As I'm using vue-router with HTML5 history mode, site requires some server Configuration
to avoid 404s.

#### Apache

```apache
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteBase /
  RewriteRule ^index\.html$ - [L]
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule . /index.html [L]
</IfModule>
```

#### nginx

```nginx
location / {
  try_files $uri $uri/ /index.html;
}
```

#### Node.js (Express)

For Node.js/Express, consider using [connect-history-api-fallback middleware](https://github.com/bripkens/connect-history-api-fallback).


## Tasks
#### Default / Development
```js
gulp
```

#### Watch (Dev)
Runs Default / Development task along with watch & browserSync.

```js
gulp watch
```

#### Build
By default build task will bump **patch** version in package.json
```js
gulp build
```

In order to bump **major** or **minor** version use following flags:
```js
gulp build --major
```
or
```js
gulp build --minor
```

#### Screenshots
Some screenshots of the "hidden" areas and features that are hidden behind the admin area.

TBC.
