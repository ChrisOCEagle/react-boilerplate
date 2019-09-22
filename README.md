## Creating the React Front-End without using the create-react-app

1.  Create a new directory called 'client' and change the directory into that new directory
    > mkdir client && cd client
1.  Initialize an npm project by creating a package.json
    > npm init -y
1.  Install react
    > npm i react react-dom
1.  Install webpack
    > npm i --save-dev webpack webpack-dev-server webpack-cli > npm i -D webpack webpack-dev-server webpack-cli
    1. This installs the
       -- webpack module: includes all core webpack functionality
       -- webpack-dev-server: development server that automatically reruns webpack when our file is changed
       -- webpack-cli: enables running webpack from the command line
1.  Create an 'index.html' at the root and fill it with general html
1.  Create a new directory called 'src' and change the directory in that new directory and then create a new file called 'index.js'
    > mkdir src && cd src && touch index.js
1.  Then write a React component into that file
1.  Install Babel
    > npm i --save-dev @babel/core @babel/preset-env \@babel/preset-react babel-loader > npm i -D @babel/core @babel/preset-env \@babel/preset-react babel-loader
    1. This installs the
       -- @babel/core: the main dependency that includes babel transform script
       -- @babel/preset-env: the default Babel preset used to transform ES6+ into valid ES5 code. Optionally configures browser polyfills automatically.
       -- @babel/preset-react: transforms JSX and React class syntax into valid JavaScript code
       -- babel-loader: webpack loader that hooks Babel into webpack. We will run Babel from webpack with this package.
1.  Create a webpack config file at the root directory to hook babel into webpack
    > touch webpack.config.js
1.  Create a new .babelrc file to use babel presets
    > touch .babelrc
1.  Make the code formatter use Prettier to speed up development
    -- Install the development dependency locally
    -- Save the exact argument, since Prettier introduces stylistic changes in patch releases
    > npm i --save-dev --save-exact prettier
    > npm i -D --save-exact prettier
1.  Now to write the prettierrc config file which will also be in the root directory
1.  Now to setup ESlint to check my code for any error or warning that can cause bugs
    > npm --save-dev i eslint eslint-loader babel-eslint eslint-config-react eslint-plugin-react
    1. This installs
       -- eslint: the core dependency for all functionalities
       -- eslint-loader: enables hooking eslint into webpack
       -- babel-eslint: a parser that enables eslint to lint all valid ES6+ codes, useful since React uses ES6+ syntax
       -- eslint-config-react and eslint-plugin-react: enables eslint to use premade rules
1.  Create an eslint config file in the root directory
    > touch .eslintrc
1.  Add the CSS SASS Processor
    > npm i --save-dev sass sass-loader css-loader style-loader
    > npm i -D sass sass-loader css-loader style-loader
    1. This installs
       -- sass: this installs sass so that I can use sass styling instead of direct css styling
       -- sass-loader: compiles my sass file into css
       -- css-loader: resolves css syntax like import or url()
       -- style-loader: retrieves the compiled css and loads it into a <style></style> in my bundle
1.  Now create some css files in a new styles directory within the src directory
    > cd src && mkdir styles && cd styles && touch header.sass main.sass
1.  The React Application is now ready to deploy!
    1. Change the build output and developer content base from dist to build
    1. Install a new webpack plugin HtmlWebpackPlugin, this plugin generates an index.html file in the same directory as where webpack creates bundle.js (build directory)
       > npm i -D html-webpack-plugin
    1. Remove <script></script> from index.html
