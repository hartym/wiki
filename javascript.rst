JavaScript
==========

.. image:: http://turnoff.us/image/en/love-ecmascript6.png
    :width: 600px

Source: http://turnoff.us/image/en/love-ecmascript6.png

Project structure
:::::::::::::::::

* http://jaysoo.ca/2016/02/28/organizing-redux-application/

Universal React / Redux / Webpack Starter
:::::::::::::::::::::::::::::::::::::::::

* http://leanjs.readthedocs.io/
* https://github.com/hartym/LeanJS

Additional tools
::::::::::::::::

* https://github.com/nfl/react-helmet


Testing frameworks
::::::::::::::::::

- Tape - https://github.com/substack/tape

  - https://medium.com/javascript-scene/why-i-use-tape-instead-of-mocha-so-should-you-6aa105d8eaf4

- Mocha - http://mochajs.org/

- Jasmine - http://jasmine.github.io/


React / Flux
::::::::::::

- http://survivejs.com/webpack_react/introduction/
- http://redux.js.org/
- https://egghead.io/series/getting-started-with-redux

Install node in a docker image
::::::::::::::::::::::::::::::

.. code-block:: text

    RUN curl -sL https://deb.nodesource.com/setup_6.x | bash - \
     && apt-get install -y nodejs \
     && curl -o- -L https://yarnpkg.com/install.sh | bash

Webpack with Django
:::::::::::::::::::

Example config for use within a django project, with hot module replacement plugin setup:

.. code-block:: javascript

    var path = require("path")
    var webpack = require('webpack')
    var BundleTracker = require('webpack-bundle-tracker')
    
    module.exports = {
        context: __dirname,
        entry: {
            package1: [
                'webpack-dev-server/client?http://localhost:3000',
                'webpack/hot/only-dev-server',
                './my_assets_path/package1'
            ],
            package2: [
                'webpack-dev-server/client?http://localhost:3000',
                'webpack/hot/only-dev-server',
                './my_assets_path/package2'
            ]
        },
        output: {
            path: path.resolve('./static/'),
            filename: '[name]-[hash].js',
            publicPath: 'http://localhost:3000/'
        },
        plugins: [
            new webpack.HotModuleReplacementPlugin(),
            new webpack.NoErrorsPlugin(),
            new BundleTracker({filename: './webpack-stats.json'})
        ],
        module: {
            loaders: [
                {test: /\.s[ac]ss$/, loaders: ["style", "css", "sass?sourceMap"]},
                {test: /\.jsx?$/, exclude: /node_modules/, loaders: ['react-hot', 'babel']},
            ]
        },
        resolve: {
            modulesDirectories: ['node_modules', 'bower_components'],
            extensions: ['', '.js', '.jsx']
        },
        externals: {
            'jquery': 'jQuery',
        }
    }
    
Example ``server.js`` used instead of ``webpack --watch`` for hot reload:

.. code-block:: javascript

    var webpack = require('webpack')
    var WebpackDevServer = require('webpack-dev-server')
    var config = require('./webpack.config')
    
    new WebpackDevServer(webpack(config), {
      publicPath: config.output.publicPath,
      hot: true,
      inline: true,
      historyApiFallback: true
    }).listen(3000, '0.0.0.0', function (err, result) {
      if (err) {
        console.log(err)
      }
    
      console.log('Listening at 0.0.0.0:3000')
    })

Node dependencies (``package.json``):

.. code-block:: json

    {
      "name": "acme",
      "version": "...",
      "description": "Boilerplate",
      "main": "server.js",
      "repository": {
        "type": "git",
        "url": "git+ssh://git@...acme.git"
      },
      "author": "",
      "license": "GFYL",
      "homepage": "https://.../...#readme",
      "devDependencies": {
        "babel": "^6.3.26",
        "babel-core": "^6.3.26",
        "babel-loader": "^6.2.0",
        "babel-preset-es2015": "^6.3.13",
        "babel-preset-react": "^6.3.13",
        "babel-preset-stage-0": "^6.3.13",
        "babel-preset-stage-1": "^6.3.13",
        "babel-preset-stage-2": "^6.3.13",
        "css-loader": "^0.23.1",
        "node-sass": "^3.4.2",
        "react": "^0.14.3",
        "react-hot-loader": "^1.3.0",
        "sass-loader": "^3.1.2",
        "style-loader": "^0.13.0",
        "webpack": "^1.12.9",
        "webpack-bundle-tracker": "0.0.9",
        "webpack-dev-server": "^1.14.0"
      },
      "dependencies": {
        "bootstrap": "^4.0.0-alpha.2",
      }
    }

Miscellaneous
:::::::::::::

- https://github.com/vasanthk/js-bits
