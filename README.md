# webp-url-loader

[WebP](https://developers.google.com/speed/webp/) image loader & converter loader for Webpack.
功能：可以保留源文件，并且使用源文件的hash命名

## Install

```sh
npm install webp-url-loader --save-dev
```

## Usage

Here is the example of using `toWebp-loader` along with common [mime](https://github.com/broofa/node-mime):

```javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/,
        use: [
          {
            loader: 'webp-url-loader',
            options: {}  
          }
        ]
      }
    ]
  }
}
```
Unfortunately, if you wish to pass an options for internal [imagemin-webp](https://github.com/imagemin/imagemin-webp) you should pass a options in JSON form:


```javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/,
        use: [
          {
            loader: 'webp-url-loader',
            options: {
              quality: 13
            }  
          }
        ]
      }
    ]
  }
}
```
if you wish to configure a custom public path for your file, you can pass a options in JSON form :

```javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/,
        use: [
          {
            loader: 'webp-url-loader',
            options: {
              quality: 13,
              publicPath: 'assets/ or cdn url'
            }  
          }
        ]
      }
    ]
  }
}
```

Normally you don't want to convert all of your images to WebP format, you just want to make alternate versions. You can use [multi-loader](https://github.com/webpack/multi-loader) to achieve it:

```javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/,
        use: [
          {
            loader: 'webp-url-loader',
            options: {
              quality: 95
            }  
          }
        ]
      }
    ]
  }
}
```

## License

[MIT](http://opensource.org/licenses/MIT)
