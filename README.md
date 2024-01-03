## smastrom

# Contributing

First of all, thank you for considering contributing to my projects. I really appreciate your interest in improving the ecosystem.

<br />

## Projects

Projects currently open to code contributions are:

- [notivue](https://github.com/smastrom/notivue)
- [vue-collapsed](https://github.com/smastrom/vue-collapsed)
- [vue-global-loader](https://github.com/smastrom/vue-global-loader)
- [vue-use-fixed-header](https://github.com/smastrom/vue-use-fixed-header)
- [react-email-autocomplete](https://github.com/smastrom/react-email-autocomplete)

For the ones not listed above I've other plans such as major releases with new features, full rewrites, etc and it's better to avoid code contributions at the moment. Of course for all of them, you can still open issues to report bugs and propose new features.

<br />

## Contribution guidelines

### Bug Fixes - Issue Reporting

To report a bug, please open an issue with a minimal reproduction on [StackBlitz](https://stackblitz.com/). This is the most important contribution you can make.

### Bug Fixes - Code Contributions

To fix a bug, please open an issue with a minimal reproduction and then open a pull request referencing the issue. One or more test cases are mandatory in order to merge the PR.

### Improvements

If you think anything can be improved, simply open a pull request. As long as the current tests pass, there's an high chance that your changes are going to be merged very soon if they make sense.

### New Features

Please raise an issue prefixed with the `[FEAT]` tag so we can discuss it together before we start dedicating time to it.

<br />

## Development Environment

### Machine

In order to make code contributions you need a Apple macOS, Unix or Windows with WSL machine. Development on Windows without WSL is not supported.

### Package Manager

Projects use [pnpm](https://pnpm.io/it/) as package manager.

If you never used it before, you can read more about it [here](https://pnpm.io/) and install it by running the following command:

```bash
curl -fsSL https://get.pnpm.io/install.sh | sh -
```

### Getting Started

Once installed, clone the repository you want to contribute to and run the following command in the project root:

```bash
pnpm install && pnpm dev
```

For UI libraries, I do not use Storybook or similar tools, I rather prefer a custom playground that also matches the demo website.

It will start as soon as you run the `dev` command and it will reload automatically when you apply changes to the source code.

<br />

## Styling and Formatting

### Code Style / Linting

I have no specific stylistic preferences, as long as the code is solid and readable I'm fine with it. None of my projects uses ESLint, so please do not introduce it in your PRs.

### Code Formatting

Code is formatted with [Prettier](https://prettier.io/) using the configuration file in the project root.

If you don't use or like it, don't worry about setting it up in your editor. Git hooks will take care of formatting when you commit the changes.

Hence feel free to use your favourite formatter with your own custom rules while developing.

<br />

## Testing

### Integration Tests

For any UI library, I prefer integration tests rather than unit tests using
[Cypress CT](https://docs.cypress.io/guides/component-testing/overview) in a real browser (Chrome and Firefox).

Ideally, an ad-hoc test-component should be added in `tests/components` and then imported and tested in a spec file in the parent folder.

Make sure you have installed the `cypress` binary in the `tests` workspace before running the tests using the `npx cypress install` command.

Please do not introduce tests running on pseudo environments such as JSDOM or Happy DOM.

### Unit Tests

If you think your contribution requires unit tests, please use [Vitest](https://vitest.dev/) (which should already be installed either in the `tests` or `packages/<package-name>` workspace). You can verify that by checking if in the root package.json file the command `pnpm test:unit` is available.

If it's not, feel free to install it in the `tests` workspace. If a `tests` workspace is not available, install it in the `packages/<package-name>` workspace.

It will be my responsibility to add/edit related scripts, workflows and configurations. In such case, don't forget to enable edits on your PR so I can do that before merging.

### Commands

Any test command can be run from the project root using the following commands:

- Integration tests in the browser (in watch mode): `pnpm test:gui`
- Integration tests: `pnpm test`
- Unit tests: `pnpm test:unit`
