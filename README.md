# How to solve the layout tasks on Github
This doc explains everuthing you need to solve Github Layout tasks and send then for review

- ❗ to avoid permissions issues **DO NOT** place your projects folder on the `Desktop`;
- ❗ there should be **NO SPACES** in the path e.g. `C:\Users\Your Name\projects`;
- it is better to put repositories into `D:\projects` or `C:\Users\YourName\projects` on Windows, or `/Users/YourName/projects` on MacOS.

## Before implementing the first task on Github
Connect Github to you Mate account

- Open your profile page on [the MA Platform](https://mate.academy/profile)
- Scroll down and press `Connect` button next to Github
- Confirm Mate academy app authorization

## Follow these instructions for all HTML/CSS tasks on Github:

1. [Open the task on the MA platform](#1-open-the-task-on-the-ma-platform)
2. [Fork the repo](#2-fork-the-repo)
3. [Check your forked repo URL](#3-you-should-see-your-name-in-the-url-instead-of-mate-academy)
    - [Instructions to delete a forked repo](#if-later-you-will-need-to-delete-a-forked-repo)
4. [Clone the forked repo](#4-clone-the-forked-repo)
5. [Open the project in IDE](#5-open-the-project-in-ide)
6. [Open the Terminal in your IDE](#6-open-the-terminal-in-your-ide)
7. [Run `npm i`](#7-run-npm-install-or-just-npm-i)
8. [Run `npm start` to open the page in browser](#8-run-npm-start-to-check-if-it-works)
9. [Open another terminal](#9-open-one-more-terminal-for-the-next-steps)
10. [Create the `develop` branch](#10-create-the-develop-branch)
11. [Update DEMO and TEST REPORT links](#11-update-demo-link-and-test-report-link)
12. [Implement the task](#12-implement-the-task-described-in-the-readmemd)
13. [Run `npm run lint` ro check the code style](#13-check-the-code-style)
14. [Run `npm t` to pass tests](#14-check-if-your-solution-matches-all-the-expectations)
    - [Handling a failing test](#if-you-see-a-failing-test)
    - [Debugging tests](#if-you-need-to-debug-tests)
15. [Run `git add ./src` to prepare your code for saving](#15-prepare-your-changed-files-for-saving)
16. [Run `git commit -m 'add solution'` to save changes](#16-save-your-changes)
17. [Run `git push` to send your code to Github](#17-send-your-code-to-github)
18. [Run `npm run deploy` to publish your site to GitHub pages](#18-publish-your-site-to-github-pages)
19. [Create a Pull Request (PR) with correct description](#19-create-a-pull-request-pr)
20. [If you need to update your PR](#20-to-update-you-pr-repeat-steps-13-18-no-need-to-create-the-pr-one-more-time)

### 1. Open the task on the MA platform
Click `Make a fork` button. It will open the task repo page on Github.

### 2. **Fork** the repo
Click the `Fork` button on Github

![How to fork the repo](./images/fork-the-repo.png)

### 3. You should see your name in the URL instead of "mate-academy"
After the Fork process is finished you should see the repo in your account (not the `mate-academy`)
![After the repo fork](./images/after-the-repo-fork.png)

Now you can check if it was synced to the MA platform
- Go back to the task on the MA platform
- The button should change to `Open the task`
- If no, reload the page
- Get back to the forked repo on Github

#### If later you will need to delete a forked repo
<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">Click here to see the instructions</summary>

  - Open project settings ![Open project settings](./images/open-project-settings.png)
  - Delete the repo ![Delete the repo](./images/delete-the-repo.png)
</details>

### 4. **Clone** the forked repo
Now you need to clone the forked project to you computer. Follow the next steps (and see screenshots below):

- click the green `Code` button;
- select `HTTPS` tab;
- ensure that link contains your Github name (NOT `mate-academy`)
- copy the link;
- open **Git Bash** (Windows) or **ZSH** (macOS) in your projects folder (You installed it in Git and Termianl course);
  <details>
    <summary>
      <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">
      How to open Git Bash
    </summary>

    ![Git Bash here](./images/git-bash-here.png)
  </details>

- run `pwd` in the terminal to check that you are in the `projects` folder;
  - if not, navigate to it using the `cd` command with a required path;
- clone the repo by running `git clone` command with the URL you copied on Github
  ```shell
  git clone the-link-from-github
  ```
    
  <details>
    <summary>
      <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">How to paste the project URL to Terminal (Git Bash)</summary>
  
    ![How to paste the URL into terminal](./images/paste-url-to-terminal.png)
  </details>
    
![Clone the repo](./images/clone-the-repo.png)
![Clone success](./images/clone-success.png)

### 5. Open the project in IDE
Now you need to open the project in you code editor (`VSCode`)
- run `code project-name` in the terminal (for example `code layout_hello-world`);
- you will see the project name as a root folder name in VSCode;

![The project opened correctly](./images/project-in-vscode-correct.png)

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">Project is opened WRONG</summary>

  ![The project opened correctly](./images/project-in-vscode-wrong.png)
</details>

### 6. Open the Terminal in your IDE
- Use the shortcut ``ctrl + ` `` (Windows) or ``cmd + ` `` (MacOS)
- Check if you are inside the project (The project name is the last part in the terminal)
- Check if the terminal in VSCode is Git Bash (Windows) of ZSH (macOS)

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">Click here to see how select the default terminal in VSCode</summary>

 - Choose `Select default shell` option ![Select default shell](./images/select-default-shell.png)
 - Select Git Bash (Windows) or zsh (macOS) ![Default shell popup](./images/default-shell-popup.png)
 - Close all the opened terminals
 - All the new terminals will be Git Bash (or zsh)
</details>

### 7. Run `npm install` (or just `npm i`).
And wait until it downloads all the packages and finish.

> Note: You should run it once for every new task

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you don't have Node.js</summary>

 ![If you don't have Node.js](./images/if-you-have-node-15.png)
</details>

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you run `npm i` outside the project</summary>

 ![If you run npm install outside the project](./images/if-you-run-npm-i-outside-the-project.png)
</details>

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you have Node.js 15 or later</summary>

 ![If you have Node.js 15 or later](./images/if-you-have-node-15.png)
</details>

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">How to reinstall Node.js</summary>

 - Open `Add and remove programs` ![Open Add and Remove programs](./images/open-add-remove-programs.png)
 - Uninstall Node.js ![Uninstall Node.js](./images/uninstall-node-js.png)
 - Download and install Node.js https://nodejs.org/download/release/v14.16.1/ 
 - Delete `node_modules` ![Delete node_modules](./images/delete-node-modules.png)
 - Run `npm i` again ![npm install success](./images/npm-install-success.png)
</details>

### 8. Run `npm start` to check if it works

The command in the terminal will never finish.

- The command should open your browser at `http://localhost:8080/` opened.
- At this point you should see the starting markup of the page.
- If the page is empty add some text to the `<body>` in the `src/index.html` file.
- The text should appear in the browser.

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If the page is still empty after you added some text</summary>

 - Update the page by pressing `ctrl + r` (`cmd + r` for macOS)
 - If the page is still empty check if you saved the changes ![Autosave is disabled](./images/autosave-is-disabled.png)
 - Enable autosave ![Enable autosave](./images/enable-autosave.png)
</details>

<details>
 <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If the page is opened at the other port (not :8080)</summary>

 - If you see the other port ![Wrong port](./images/wrong-server-port.png)
 - It means you already have another terminal running `npm start` command (maybe it is another project)
 - Stop the `npm start` command in current terminal by pressing `ctrl + c` (all operating systems)
 - Close the other terminal running `npm start`
 - Run the command again for your current project
 - The URL should be now `http://localhost:8080/`
 - If the URL is still wrong, just restart the computer
</details>

### 9. Open one more terminal for the next steps.

Use `+` or just press ``ctrl + shift + ` `` or ``cmd + shift + ` ``.

![Open one more terminal](./images/open-one-more-terminal.png)

### 10. Create the `develop` branch
Run:
```
git checkout -b develop
```
or
```
git switch -c develop
```

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you see that "develop" branch already exists</summary>

  ![Develop already exists](./images/develop-already-exists.png)
  - run `git branch` to see all existent branches ![Show git branches](./images/show-git-branch.png)
  - If `develop` is marked with `*` then everything is correct
  - Otherwise, run `git checkout develop` (without `-b` key) ![Switch to develop](./images/switch-to-develop.png)
</details>

### 11. Update `DEMO LINK` and `TEST REPORT LINK`
- open `readme.md` file
- replace the text `<your_account>` with your Github username in the `DEMO LINK` and `TEST REPORT LINK`

![Update demo link](./images/update-demo-link.png)

### 12. Implement the task described in the `readme.md`. 

You should write the code in `index.html` and other files inside `src` folder.

### 13. Check the code style
Run:
```
npm run lint
```

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you have some errors</summary>

  - Fix all the errors and run the command again

  ![Linter errors](./images/linter-errors.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">How to find the lines with linter errors</summary>

  ![The lines with errors](./images/lines-with-linter-errors.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">This error means you need to fix CRLF</summary>

  ![CRLF linter error](./images/crlf-linter-error.png)

  - run `git config --global core.autocrlf false`
  - and fix the CRLF in all the files you changed

  ![CRLF in current file](./images/crlf-error-after-global-config.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">How to fix autoformatting in VSCode</summary>

  - Here is [the documentation](https://code.visualstudio.com/docs/languages/html#_formatting) 
  - Run `Alt + Shift + F` to format the document

  ![HTML autoformat settings](./images/html-autoformat-settings.png)
  ![HTML autoformat json](./images/html-autoformat-json.png)
</details>

### 14. Check if your solution matches all the expectations
- read the `checklist.md`;
- fix your code if needed;
- run `npm run lint` again to ensure nothing is broken
- run the tests;
    ```
    npm test
    ```
- Test results should be openned in browser;
- If not, check if you fixed all the code style errors (`npm run lint`)

#### If you see a failing test

Fix you HTML and CSS to make your page identical to the expected result.

![Failed tests](./images/failed-tests.png)
![How to compare a test with reference](./images/how-to-compare-test-with-reference.png)

#### If you need to debug tests
- [Open this DOC](layout-tests.md)

> If you can't run tests for some weird reason just use a screenshot from
  `backstop_data/bitmaps_reference/Entire_document.png` to ensure your page looks as expected.

### 15. Prepare your changed files for saving
```
git add ./src
```
- Don't add irrelevant files at this point, like `package-lock.json` or test snapshots.
- You can always check which files were changes or added using `git status` command.
- Also don't forget to add readme.md file.
```
git add readme.md
```

### 16. Save your changes

Run the `commit` with a message describing what this code does.

```
git commit -m 'add task solution'
```

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">
    fatal: unable to auto detect email address
  </summary>

  - it means you forgot to configure you GIT name and email
  - See the commands above the error message and run them one by one with your email and name

  ![If you forgot to set GIT name and email](./images/forgot-to-configure-git.png)
  ![Set GIT name and email](./images/set-git-name-and-email.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">no changes added to commit</summary>

  ![No changes added to commit](./images/no-changes-added-to-commit.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">LF will be replaced with CRLF</summary>

  - You forgot to fix CRLF 

  ![Forgot to fix CRLF](./images/forgot-to-fix-crlf.png)
</details>

### 17. Send your code to Github
Run:
```
git push origin develop
```

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">failed to push some refs</summary>

  ![Forgot to create develop](./images/forgot-to-create-develop.png)
  ![Reset and create develop](./images/reset-head-and-create-develop.png)

  - Commit changes again after creating `develop` branch 
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">If you are asked for the Authorization</summary>

  ![Github auth popup](./images/github-auth-popup.png)
  ![Authorize GIT credentials manager](./images/authorize-git-credentials-manager.png)
  ![Push success](./images/push-success.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">fatal: unable to access</summary>

  ![Permission denied](./images/permissions-denied.png)
  ![Add correct origin](./images/add-correct-origin.png)
</details>

### 18. Publish your site to GitHub pages.
Run:
```
npm run deploy
```

> If you are getting some errors run `npm run deploy -- -l` to see more details

Deploy process requires some time to prepare your page on Github after the command is finished.

To check if the page was deployed succesfully you need to check in the project settings on Github:
- Open the forked repo on Github;
- Click the `Setting` tab at the top;
- Choose `Pages` section from the panel on the left;
- There should be a link to your public page at the top (the same as your `DEMO LINK` in the `readme.md`)
- If there are no link at the top check if `gh-pages` branch appeared in the repo;
  - If not run `npm run deploy -- -l` to see more details
- Wait for about 2 minutes and reload the `Settings > Pages` again to see the link;
- Open it to see your page.

### 19. Create a Pull Request (PR)
- Select `Pull requsts` tab;
- Click `New pull request` green button;
- Change the `compare` branch  at the right to `develop`;
- Click `Create pull request` button;
- Copy `DEMO LINK` and `TEST REPORT LINK` from `readme.md` to the PR description;
  - Links should contain your Github name (not `mate-academy`)!!!
- Click `Create pull request` button one more time;
- Check that your `DEMO LINK` and `TEST REPORT LINK` work as expected (open the page and test results);
- Check if the task appeared in the table (only for full-time students)

![New pull request](./images/new-pull-request.png)
![Create pull request](./images/create-pull-request.png)
![Add DEMO Links](./images/add-demo-links.png)

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">Check your DEMO LINK</summary>

  - You forgot to put your Github name into `DEMO_LINK` and `TEST_REPORT_LINK`

  ![Forgot to fix DEMO LINK](./images/forgot-to-put-your-name-to-demo-link.png)
</details>

<details>
  <summary>
    <img alt="hint" src="https://placehold.co/80x24/ffedeb/e25544?text=< Expand">Check your TEST REPORT LINK</summary>

  - You forgot to run tests before `npm run deploy`

  ![Forgot to run tests before deploy](images/forgot-to-run-tests-before-deploy.png)
</details>

### 20. To update you PR repeat steps 13-18 (no need to create the PR one more time).

> If you need an ADDITIONAL CODE REVIEW, click on re-request button at the PR page.
![Image of re-request button](https://user-images.githubusercontent.com/38065883/104471439-89929200-55c3-11eb-824a-596bfb8aa246.png)

## Important 
In order to allow us to review your homework - do not close PR and do not open several PR's.
If there is a fork and PR, then any subsequent PR for that fork will be ignored
and it won't be synced to the platform, only the first PR made after the fork will

- If you have closed the PR - reopen it and request mentor review.
- If you can't open the PR - do another fork and create a new PR.

## Linux users
> If you use _linux_ please make sure you adjusted writing permissions to let 
scripts work without `sudo`. Correct permissions mean you don't see errors like
`permission denied` after running commands in terminal.

## NPM commands
- `npm install` installs the project dependencies and runs `postinstall`
  - which create reference files for pixel perfect and tests 
- `npm start` runs the server required for development and tests
- `npm test` runs linter and tests
  - `npm run lint` runs linter (code style check)
  - `npm run test:only` runs pixel perfect tests
- `npm run deploy` publishes the page and test report to `gh-pages` 

## Useful links

- [How to understand and debug Layout Tests](layout-tests.md)
- [Working with figma](./figma.md)
- [HTML, CSS Code Style Rules](html-css-code-style-rules.md)
- [Useful GIT commands](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [Terminal commands](https://mate-academy.github.io/fe-program/tools/terminal/useful-commands)
- [Creating a pull request from a fork](https://help.github.com/en/articles/creating-a-pull-request-from-a-fork)
- [HTML, CSS styleguide](https://mate-academy.github.io/style-guides/htmlcss.html)
