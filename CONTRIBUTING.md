# Contributing to Charts

Yippee! If you're here, you _must_ be interested in contributing something to Charts—and if that's the case, it's safe to say that one: we like you already 🤓 and two: we would like to personally thank you ahead of time ❤️

Please take a moment to review this document in order to make the contribution process easy and effective for everyone involved.

## Table of contents

- [Issue guidelines](#issue-guidelines)
- [Pull request guidelines](#pull-request-guidelines)
  - [Contribution process](#contribution-process)
  - [NPM commands](#npm-commands)
- [Code guidelines](#code-guidelines)
  - [Resources](#resources)
  - [Philosophy](#philosophy)

## Issue guidelines

- **Before submitting**, confirm the issue doesn't already exist by browsing through [existing issues](https://github.com/IBM/carbon-charts/issues). _Duplicates are just a waste of space._
- Keep issues **specific to one topic**. _Do not open an issue that describes multiple defects._
- Provide a **short descriptive title** that mentions the component being addressed.
- Provide enough of the **relevant information** below to initiate a clear issue description. Most of this content comes out-of-the-box as a template when [creating a new issue](https://github.com/IBM/carbon-charts/issues/new).
  - Type of issue
  - Version of charts
  - Description of the issue
  - Steps taken to produce the issue
  - Expected behavior
  - Current behavior
  - Screenshots or recording
  - Code snippets
  - Links to your application source code or running demo
    - Include any connection/authentication information we may need to view the links
- Add **relevant labels** (accessibility, bug, design, discussion, feature, etc.) to help organize and identify issues. For a complete list of our labels, see the [labels page](https://github.com/IBM/carbon-charts/labels).
- If you are interested in contributing, feel free to **assign the issue** to yourself, otherwise leave it unassigned.

## Pull request guidelines

- Before creating the pull request:
  - Update the "[Unreleased]" section of `CHANGELOG.md`.
  - Update the demo _as needed_.
  - Update the documentation _as needed_.
  - Make sure the **linter passes** by running `npm run lint`.
  - **Do not** change the version number.
  - Keep in mind there will be a **code review checklist** against the following requirements at time of review:

    Requirement | Description
    ----------- | -----------
    Demos all features | All interactions spec'd out in the Design Guide has visual support and a demo as proof.
    Documented/annotated | All rule blocks, placeholders, mixins, and functions has associated comment blocks that convey purpose and list inline notations referencing declarations that need further explanation.
    Matches UI/UX specs | All features are pixel perfect when compared to the Design Guide.
    Meets the [code style guide](https://github.com/IBM/carbon-charts/wiki/Code-style-guide) | All code adheres to our custom style guide giving off the impression that it was written by one developer.
    Accessible | All code passes the [Dynamic Assessment Plugin (DAP)](https://w3-connections.ibm.com/wikis/home?lang=en-us#!/wiki/W88ee03f8907c_412b_a3a8_988dabb72b35/page/Dynamic%20Assessment%20Plugin) scan in Chrome.
    Mobile first | All visual elements are elegantly responsive.
    RTL support | All visual elements reflect bidirectional text appropriately.
    Performant | All Sass code is strategically written in a way to limit bloat in the compiled CSS.

- While creating the pull request:
  - Prepend "WIP: " to the title of your pull request if it is **not ready** to be merged.
  - Provide enough of the **relevant information** below to initiate a clear contribution description. Most of this content comes out-of-the-box as a template when [creating a pull request](https://github.com/IBM/carbon-charts/compare).
    1. A list of updates with references to the related issue (see: [Closing issues using keywords](https://help.github.com/articles/closing-issues-using-keywords/))
    2. Screenshots or recording
    3. @mention any key stakeholders that need to be aware of the changes
  - Add **relevant labels** (needs review, accessibility, bug, design, feature, etc.) to help organize and identify issues. For a complete list of our labels, see the [labels page](https://github.com/IBM/carbon-charts/labels)

### Contribution process

1. [Run Charts locally](https://github.com/IBM/carbon-charts/blob/master/README.md#run-charts-locally), then **configure the remotes** from your `charts/` directory:

   ```bash
   # Assign the original repo to a remote called "upstream"
   git remote add upstream git@github.com:IBM/carbon-charts.git
   ```

2. **Create a new topic branch** (off the original remote branch) to contain your code changes:

   ```bash
   git checkout -b <topic-branch-name> upstream/master
   ```

3. **Commit your changes in small logical chunks.** Refer to these [git commit
   message guidelines](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
   to maintain consistency. For funsies, prefix your commit with relevant emojis from the list below:

    Emoji | Short code | Use case
    ----- | ---------- | --------
    🎨 | `:art:` | when improving the format/structure of the code
    🐎 | `:racehorse:` | when improving performance
    ♿️ | `:wheelchair:` | when improving accessibility
    🌐 | `:globe_with_meridians:` | when improving bidirectional support
    📝 | `:memo:` | when writing docs
    🆕 | `:new:` | when adding new features or patterns
    🐛 | `:bug:` | when fixing a bug
    🔧 | `:wrench:` | when refactoring code
    🔥 | `:fire:` | when removing code or files
    💚 | `:green_heart:` | when fixing the build
    ✅ | `:white_check_mark:` | when adding tests
    ⬆️ | `:arrow_up:` | when upgrading dependencies
    ⬇️ | `:arrow_down:` | when downgrading dependencies
    👕 | `:shirt:` | when removing linter warnings

4. If time passes between development, **locally merge (or rebase) the upstream master branch** into your topic branch to avoid conflicts in your pull request. We recommend using Git's [interactive rebase](https://help.github.com/articles/interactive-rebase) feature to tidy up a messy commit history.

   ```bash
   # Fetch and merge commits history
   git pull upstream master
   # Reapply one commit at a time
   git rebase --interactive upstream/master
   ```

5. Complete step 5 first, before **pushing your topic branch** up to your fork:

   ```bash
   git push origin <topic-branch-name>
   ```

6. [Open a Pull Request](https://github.com/IBM/carbon-charts/compare) with a clear title and description from the template provided.

    - See [Creating a pull request from a fork](https://help.github.com/articles/creating-a-pull-request-from-a-fork/) for step-by-step instructions.
    - Ensure the base branch is assigned to `master`.

### NPM commands

We use specific NPM scripts to test, lint, and build our demo and distributed files. Here are the scripts to choose from:

- `npm run demo:server` to run the demo server on port 9090 and watch for changes
- `npm run demo:build` to build the demo directory in `carbon-charts/demo/`
- `npm run build` to build the distributed directory in `carbon-charts/dist/`
- `npm run lint` to run TS lint on the source files
- `npm run test` to run unit tests on the source files

## Code guidelines

Adhere to the code guide enforced with our _very specific_ TS rules defined in our very own [linter file](https://github.com/IBM/carbon-charts/blob/master/tslint.json).

Run `npm run lint` before committing to ensure your changes follow our coding standards.

### Resources

- [Dynamic Assessment Plugin (DAP)](https://w3-connections.ibm.com/wikis/home?lang=en-us#!/wiki/W88ee03f8907c_412b_a3a8_988dabb72b35/page/Dynamic%20Assessment%20Plugin)
- [IBM Accessibility Checklist](http://www-03.ibm.com/able/guidelines/ci162/accessibility_checklist.html)
- [Charts Wiki pages](https://github.com/IBM/carbon-charts/wiki)
- [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/)

### Philosophy

- Components should be fully equipped with _all_ features and interactions defined in the latest Design Guide and UX Specifications.
- Components should be _pixel perfect_ when compared to the latest Design Guide.
