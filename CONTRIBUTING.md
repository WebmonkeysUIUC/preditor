# Contributing to the project
Thank you for taking the time to contribute! Please take a moment to review this document in order to make the
contribution process easy and effective for everyone involved. These are just guidelines, not rules, so use your best
judgment and feel free to propose changes to this document in a pull request or issue.

## Using the issue tracker
The [issue tracker](https://github.com/WebmonkeysUIUC/preditor/issues) is the preferred channel for bug reports, feature
requests and [submitting pull requests](#pull-requests).

Bug reports are extremely helpful, and are encouraged! Information about your environment, such as your browser and
Operating System, and steps to reproduce the issue will help to fix any potential bugs, and will be highly appreciated.

## Development environment set up
1.  [Set up Git](https://help.github.com/articles/set-up-git/) and install [Node.js](https://nodejs.org/).
    Node's package manager ([npm](https://www.npmjs.org/)) comes bundled.

2.  Globally install [Bower](http://bower.io/) and [Grunt](http://gruntjs.com/)
    (you might need to use `sudo` or run the command as an Administrator if it fails due to missing permissions,
    because of the [location npm installs global packages](https://www.npmjs.org/doc/files/npm-folders.html) in):  
    `npm install -g bower grunt-cli`

3.  [Fork](https://help.github.com/articles/fork-a-repo/) this repository. Clone your forked git repository:  
    `git clone https://github.com/<your-username>/preditor.git`

4.  Navigate to the newly cloned directory:  
    `cd preditor/`

5.  Configure Git to be able to update your fork with the changes from the original repository:  
    `git remote add upstream https://github.com/WebmonkeysUIUC/preditor.git`

6.  Install dependencies and set up the project:  
    `npm install`

7.  Start a local development server and launch the application:  
    `grunt serve`

## Pull requests
Pull requests --- patches, improvements, new features --- are a fantastic help.

Please ask first before embarking on any significant pull request.
You can comment on the relevant issue or open a new issue to start or join a discussion.
It is also a good idea to discuss your solution/changes/approach before starting any implementation.

Pull requests should remain focused in scope and avoid containing unrelated commits.
They should also adhere to the [coding guidelines](#code-guidelines) used throughout the project.

Adhering to the following process is the best way to get your work included in the project:

1.  [Set up your development environment](#development-environment-set-up) if not done already.

2.  [Sync your local `master` branch](https://help.github.com/articles/syncing-a-fork/) with the upstream repository
    and then update your fork on GitHub:  
    `git checkout master`  
    `git pull upstream master`  
    `git push origin master`

3.  Make sure all the dependencies are installed and up-to-date:  
    `npm install`

4.  Create a new topic branch (off the main project development branch) to contain your feature, change, or fix:  
    `git checkout -b <topic-branch-name>`

5.  Stage your changes before committing. Type the following for every individual added/modified/deleted file
    (instead of staging all changes in one go, to ensure you do not accidentally add any sensitive or
    unnecessary files):  
    `git add path/to/modified_file`

6.  Commit your changes in logical chunks. Please adhere to the git commit message guidelines in the
    [Git and GitHub guidelines and tips](#git-and-github-guidelines-and-tips) section.  
    `git commit`

7.  Locally [merge (or rebase)](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) the upstream development
    branch into your topic branch (if merge conflicts arise then please fix them):  
    `git pull [--rebase] upstream master`

8.  Push your topic branch up to your fork:  
    `git push origin <topic-branch-name>`

9.  [Create a pull request](https://help.github.com/articles/creating-a-pull-request) for merging into the
    upstream `master` branch. You're all set! Now wait for someone to review your code and merge your changes.

**IMPORTANT**: By submitting a patch, you agree to allow the project owners to license your work as
mentioned [in the License section at the bottom](#license).

### After your pull request is merged
Thank you and congratulations! After your pull request is merged, you can safely delete your branch and pull the
changes from the main (upstream) repository:

1.  Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:  
    `git push origin --delete <topic-branch-name>`

2.  Check out the master branch:  
    `git checkout master`

3.  Delete the local branch:  
    `git branch -D <topic-branch-name>`

4.  Update your local `master` branch with the latest upstream version:  
    `git pull upstream master`

5.  Update your fork on GitHub:  
    `git push origin master`

## Code guidelines
* Please include tests whenever possible.
* Make sure all tests pass. Use the command `grunt test` to run the tests.
* We have an [editor config](.editorconfig) file for maintaining a consistent coding style. Read more and download
  plugins at <http://editorconfig.org>. Using EditorConfig will considerably help you to adhere to the code style
  guidelines below.

### HTML
* [Adhere to the Code Guide by @mdo](http://codeguide.co/#html) (however, use soft tabs with **four** spaces instead
  of two).
* Use tags and elements appropriate for an HTML5 doctype (e.g., self-closing tags).
* Download JS scripts using Bower to be included in the distribution, instead of loading them from third-party URLs.
* If you have to use third-party JS, use CDNs and HTTPS when possible.
* Use [WAI-ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) attributes to promote accessibility.

### CSS
* [Adhere to the Code Guide by @mdo](http://codeguide.co/#css) (however, use soft tabs with **four** spaces instead
  of two).
* When feasible, default color palettes should comply with
  [WCAG color contrast guidelines](http://www.w3.org/TR/WCAG20/#visual-audio-contrast).

### JavaScript
* We use [JSHint](http://jshint.com/about/) to detect errors and potential problems in JavaScript code. Use
  `grunt jshint` to run JSHint on your code. The file [.jshintrc](.jshintrc) contains the configuration used for JSHint.

* [JSHint can be suppressed](http://jshint.com/docs/#inline-configuration) in particular parts of code when necessary.
  Use this sparingly, though.

**NOTE**: If you encounter any code not adhering to these guidelines, feel free to open an issue, or better, open a
(separate) pull request fixing the violations. Also feel free to discuss changing/adding/removing any guideline if you
have a compelling reason for it.

## Git and GitHub guidelines and tips
* Please adhere to the guidelines mentioned in the excellent post
  [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/). The post
  [5 Useful Tips For A Better Commit Message](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message)
  also contains helpful guidelines.

* Avoid pushing changes to the `master` branch of your fork. Changes should be in their own branch, which should then
  be merged into `upstream/master` through a pull request. Your fork's `master` branch should always be in sync
  with `upstream/master`. If you open a pull request with changes made directly on your `master` branch, and your pull
  request happens to get rejected, your fork's `master` branch will remain ahead of `upstream/master`, which is a
  [messy situation to fix](https://stackoverflow.com/questions/5916329/cleanup-git-master-branch-and-move-some-commit-to-new-branch).
  Therefore, always make changes in a new branch.

* If your pull request contains a fix for a bug or implements a new feature, you can have the corresponding issue
  [closed automatically](https://github.com/blog/1506-closing-issues-via-pull-requests) when the pull request is merged.

## Useful tools and tips for development
* Run `grunt serve` to start a local development server. It will automatically launch the default browser and navigate to
  the local application. It will also watch files for changes - automatically running JSHint on changed JS files,
  automatically compiling changed SASS files, etc. Livereloading is also enabled, so your browser refreshes automatically
  after you make any changes.

* If you want to run the tests in a browser, run `grunt serve:test` to start a local test server, then
  navigate to `http://localhost:9001`.

## License
By contributing your code, you agree to license your contribution under the terms of the
[project's license](LICENSE.md).
