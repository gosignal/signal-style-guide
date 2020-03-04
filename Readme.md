# Signal Style Guide

> very much a WIP...

- An attempt at comprehensive global guides to working on / with / around any products that [Signal](http://fullsignal.co) touches. Heavily influenced from the Airbnb guide.

## A few notes

- _Typescript vs. JS_: - at this time, javascript is recommneded only so as not to slow down development, however, at this is subject to change anytime as the ecosystem matures.
- _css/styles/jss_: - if your project requires use of styles do not use css/less/sass, rather use [styled components](http://styled-components.com) or, even better [Material-UI](http://material-ui.com) (which has styled components built in).
- _API's_ we are a graphql shop. We deprecated REST as of the beginning of 2020.
- _Languages_:
  - Javascript / Typescript (preferred)
  - Rust (preferred when needed)
  - Python (allowed when needed)

## Configs

- [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
- [prettier integrated w/ eslint](https://github.com/prettier/eslint-config-prettier)
- [babel](http://babeljs.com) - configured as follows:
- [css in javascript](https://github.com/airbnb/javascript/tree/master/css-in-javascript) use this styleguide.
  ```json
  {
    "presets": ["airbnb"],
    "plugins": [
      [
        "module-resolver",
        {
          "root": ["./"],
          "extensions": [".js", ".jsx"],
          "alias": {
            "*": "./src/*",
            "~components/*": "./src/components/*"
          }
        }
      ]
    ]
  }
  ```
  _*note*_ read more [here](https://github.com/airbnb/babel-preset-airbnb)

## Patterns

- Repositories:

  ```
  ./
  lerna.json
  package.json (named @projectname)
    /scripts
        any shell scripts needed
    /packages
        /package-name
            ... contents of package/app
            name this (@projectname/package-name)
    /_notes
        notes.md (shared communal notes for your peers)
  ```

- folder structure for applications.

  ```
  ./
  package.json
  Readme.md (with instructions... see Readme section...)
  .env here (do not commit)
  (configs here, or better... in ./config)
      /src
          /components (react apps only)
              /ComponentName
                  index.js
                  ComponentName.jsx
                  ComponentStyles.js
          /pages (any composed pages)
              /about
                  index.js
          /theme
              theme.js
              colors.js (export color specific vars)
          /utils
              useAuth.js
              useTheme.js
              useWhatever.js
  ```

## React Specific Notes

If using react use this [config](https://github.com/airbnb/javascript/tree/master/react)

- use functional components, with hooks.
- try to stick with `useState()` unless `useReducer()` is absolutely necessary.
- For data-sources, WE NOW ONLY WORK WITH APOLLO/ GraphQL. NO MORE REST.

## Technologies

Try to use these technologies

_package tools_

- [lerna](https://lerna.js.org/)
- [yarn workspaces](https://yarnpkg.com/lang/en/docs/workspaces/)

_build tools_

- [webpack](https://webpack.js.org/)
- [babel](https://babeljs.io/)

_config tools_

- [eslint](https://eslint.org/)
- [prettier](https://prettier.io/)
- [style-lint](https://stylelint.io/)

_devops tools_

- [serverless](http://serverless.com)
- [docker](https://www.docker.com/)
- [docker-compose](https://docs.docker.com/compose/)

_design system tools_

- [bit.dev](http://bit.dev)
- [Styled-Components](http;//styled-components.com)

_general tech_

- [next.js](https://nextjs.org/)
- [react](https://reactjs.org/)
- [express](https://expressjs.com/)
- [mongoose](http://mongoosejs.com)
- [Mong Atlas](https://mongodb.com)
- [KeystoneJS](http://keystonejs.com)
- [Apollo](http://apollographql.com)
