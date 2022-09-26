# Semantic UI theming using Parcel and React.JS
> This is a step by step guide on how to set-up and use SemanticUI theming in a Parcel React.js app.
### Setup
1. Install the following dependecies

```json
"devDependencies": {
	"@parcel/transformer-less": "^2.5.0",
	"less": "^4.1.2",
	"parcel": "latest"
},
"dependencies": {
	"react": "^17.0.0",
	"react-dom": "^17.0.0",
	"semantic-ui-less": "^2.4.1",
	"semantic-ui-react": "^2.1.2"
}

```
3. Create a `.lessrc` file on the same level as your package.json
```json
{
	"math" : "always"
}
```
3. Create a `craco.config.js` file on the same level as your package.json
```js
// craco.config.js

module.exports = {
  plugins: [{ plugin: require('@semantic-ui-react/craco-less') }],
}
```
4. Copy the contents from `./semantic-ui-theming-files` to `src/semantic-ui`
5. Import `semantic.less` from the `src/semantic-ui` folder into your entry file.
```js
// index.js

import './semantic-ui/semantic.less';
```
### Usage

- The editable theme files are found in `src/semantic-ui/site`. 
  - Each Semantic UI component is found in a subfolder that matches the component type (Collections, Views, Elements, etc)
- Themes are made up of two files: a `.variables` file and a `.overrides file`. A theme can include both variables and overrides, or just either one alone.
- A `.variables` file specifies variables which should be adjusted for a theme.
  - For simple changes like background color, padding, margin etc, you should use a `.variables` file.
- An `.overrides` file specifies additional CSS rules to be added to a definition for a theme. This file also has access to all inherited variables for a component.
  - If the theming is more complicated, e.g. adds new CSS properties, you should resort to using a `.overrides` file.
- Definition files are found in `src/semantic-ui/definitions`
  - They can be used to find the variable names and css classes that you want to edit.



### Resources
- [Using themes](https://semantic-ui.com/usage/theming.html)
- [React theming setup](https://semantic-ui.com/usage/theming.html)
- [Example implementation](https://github.com/zitsen/parcel-semantic-ui-less)



