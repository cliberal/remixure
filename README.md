# remixure

## DO NOT DOWNLOAD. I AM STILL WORK ON IT. SORRY...

remixure is to help to quickly build a webpack based React project.

# Install
Install with npm:
```
npm i --save-dev remixure
```
Install with yarn
```
yarn add remixure --dev
```

# How to use
1. In your project package.json, add the content:
```json
"scripts": {
  "production": "remixure build --env=prod",
  "dev": "remixure build --env=dev"
}
```
2. Create the configuration file in your config folder.
- config.default.js: The default configuration file can save all the basic configurations.
- env: The env speicific file. You can also set the env in the CLI. The CLI --env=prod value will overwrite the env file's configuration.
- config.${env}.js: The configuration file for the target env. It will overwrite the config.default.js.

3. Do the build:
```
yarn run dev
# OR
yarn run production
```



## Configurations:
```javascript

exports.publicPath = '/'; // Optional: The public path for the build. Default is /.

exports.less = {
  // Enable less

  // If enable CSS modules.
  enableCSSModule: true,
  // If use post css:
  enablePostCSS: true,
  // Exclude folder. node_modules is the default folder. Do not need to add it.
  exclude: [/iconfont/],
}

exports.enableAntD = true;  // If you are using antd.

exports.useMoment = true; // If you are using moment.js.

exports.chunks = ['vendor', 'components']; // The chunk key you want to do the chunk.

exports.htmlPath = 'public/index.html'; // If you want to pack index.html with the <script> inject. You need the speicific your index template path.

exports.cleanBeforeBuild = true; // If you want to clean the build folder before job start.

```

If you want to use the dev mode. There are some addional configurations under config/config.dev.js:
```javascript
// This can be put in config.dev.js so that the production will not excuted.
exports.devServer = {
  "HTTPS": "https", // Optional: Default value is http.
  "HOST": "0.0.0.0", // Optional: Default value is 0.0.0.0.
  "PORT": "8888", // Optional: Default value is 8888.
}; // If you want to enable the devServer.
```