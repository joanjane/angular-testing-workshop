# AngularTestingWorkshop

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.1.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

## Docs
- [Component testing scenarios](https://angular.io/guide/testing-components-scenarios#component-testing-scenarios)
- [Testing Asynchronous Code](https://codecraft.tv/courses/angular/unit-testing/asynchronous/)
- [Jasmine - Your first test suite](https://jasmine.github.io/tutorials/your_first_suite)
- [Configure CLI for CI testing](https://angular.io/guide/testing#configure-cli-for-ci-testing-in-chrome)

## CI setup
1. Install deps:
`npm i -D puppeteer karma-chrome-launcher`

2. Configure karma.conf.js:
2.1. Include this import at the top:
`process.env.CHROME_BIN = require('puppeteer').executablePath()`
2.2. Add launcher for CI
```js
browsers: ['Chrome', 'ChromeHeadlessCI'],
customLaunchers: {
  ChromeHeadlessCI: {
    base: 'ChromeHeadless',
    flags: ['--no-sandbox']
  }
}
```
3. Add script on package.json: `"test:ci": "ng test --no-watch --no-progress --browsers=ChromeHeadlessCI"`
4. Run `npm run test:ci`

## Topics
### Counter exercise:

Create a counter component that has the following features:

1. A button that increments a value on click.
2. A button that decrements a value on click.
3. A text element that displays the current counter value.
4. Counter starts with 0 by default.
5. Counter can be initialized with any number instead of 0.
6. Counter emits the count value when changes.
7. Test it!

### ToDo list exercise:

Create a ToDo list component that has the following features:

1. Contains an input to type a new todo note and a button to add id on click.
2. Lists the existing todo notes
3. On each todo note, displays a button to remove the note.
4. Saves all notes on local storage through using a service in component.
5. Test component with an integration test between component and service.
6. Test component with unit tests.
7. Test service with unit tests.
