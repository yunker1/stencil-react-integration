This repository was built by following the documentation: https://stenciljs.com/docs/react#step-2---react-component-library

It fails to build due to the generated code not being able to find the type definitions from the stencil components:
```
> react-library:build

react-library: > react-library@0.0.1 build
react-library: > npm run tsc
react-library: > react-library@0.0.1 tsc
react-library: > tsc -p . --outDir ./dist
react-library: lib/components/stencil-generated/components.ts(13,93): error TS2307: Cannot find module 'stencil-library/dist/components/my-component.js' or its corresponding type declarations.
react-library: npm ERR! Lifecycle script `tsc` failed with error: 
react-library: npm ERR! Error: command failed 
react-library: npm ERR!   in workspace: react-library@0.0.1 
react-library: npm ERR!   at location: /home/user/workspace/github/junk/junk2/stencil-demo/packages/react-library 
react-library: npm ERR! Lifecycle script `build` failed with error: 
react-library: npm ERR! Error: command failed 
react-library: npm ERR!   in workspace: react-library@0.0.1 
react-library: npm ERR!   at location: /home/user/workspace/github/junk/junk2/stencil-demo/packages/react-library 
```
I believe it is the same issue described in https://github.com/ionic-team/stencil-ds-output-targets/issues/477
This pattern worked when the react-output-target v0.5.3 was used, and no longer works in v0.7.1
To see the problem, the build steps are:
```
# npm install
# npm run build
```
