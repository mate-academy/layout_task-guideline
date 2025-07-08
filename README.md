# How to Solve the Layout Tasks on GitHub
This document explains everything you need to solve GitHub Layout tasks and send them for review.

- ❗ To avoid permissions issues, **DO NOT** place your projects folder on the `Desktop`.
- ❗ There should be **NO SPACES** in the path, e.g., `C:\Users\Your Name\projects`.
- It is better to put repositories into `D:\projects` or `C:\Users\YourName\projects` on Windows, or `/Users/YourName/projects` on MacOS.

## Before Implementing the First Task on GitHub
Connect GitHub to your Mate account.

- Open your profile page on [the MA Platform](https://mate.academy/profile).
- Scroll down and press the `Connect` button next to GitHub.
- Confirm Mate Academy app authorization.

## Follow These Instructions for All HTML/CSS Tasks on GitHub:

1. [Open the task on the MA platform](#open-the-task-on-the-ma-platform)
2. [Fork the repo](#fork-the-repo)
3. [Check your forked repo URL](#check-the-url-of-the-forked-repo)
4. [Clone the forked repo](#clone-the-forked-repo)
5. [Open the project in IDE](#open-the-project-in-vscode)
6. [Open the Terminal in your IDE](#open-the-terminal)
7. [Run `npm i`](#codenpm-installcode-or-just-codenpm-icode)
8. [Run `npm start` to open the page in a browser](#codenpm-startcode-to-open-the-page)
9. [Open another terminal](#open-one-more-terminal-for-the-next-steps)
10. [Create the `develop` branch](#create-the-codedevelopcode-branch)
11. [Update DEMO and TEST REPORT links](#update-codedemo-linkcode-and-codetest-report-linkcode)
12. [Implement the task](#implement-the-task-described-in-the-codereadmemdcode) 
13. [Run `npm run lint` to check the code style](#codenpm-run-lintcode-to-check-the-code-style)
14. [Run `npm t` to pass tests](#codenpm-testcode-to-check-if-solution-is-correct)
15. [Run `git add ./src` to prepare your code for saving](#codegit-addcode-to-prepare-changed-files-for-saving)
16. [Run `git commit -m 'add solution'` to save changes](#codegit-commitcode-to-save-changes)
17. [Run `git push origin develop` to send your code to GitHub](#codegit-push-origin-developcode-to-send-your-code-to-github)
18. [Run `npm run deploy` to publish your site to GitHub Pages](#codenpm-run-deploycode-to-publish-to-github-pages)
19. [Create a Pull Request (PR) with a correct description](#create-a-pull-request-pr)
20. [If you need to update your PR](#to-update-your-pr-repeat-steps-13-18-no-need-to-create-the-pr-one-more-time)

- [NPM Commands](#npm-commands)
- [Useful links](#useful-links)

### 1. Open the Task on the MA Platform
Click the `Make a fork` button. It will open the task repo on GitHub.

### 2. Fork the Repo
<details>
  <summary><b>Click the `Fork` button on GitHub</b></summary>

  ![How to fork the repo](./images/fork-the-repo.png)
</details>

### 3. Check the URL of the Forked Repo
After the Fork process is finished, you should see the repo in your account (not the `mate-academy`).
![After the repo fork](./images/after-the-repo-fork.png)

Now you can check if it was synced to the MA platform.
- Go back to the task on the MA platform.
- The button should change to `Open the task`.
- If not, reload the page.
- Get back to the forked repo on GitHub.

<details>
  <summary><b>If you need to delete a forked repo</b></summary>

  - Open project settings. ![Open project settings](./images/open-project-settings.png)
  - Delete the repo. ![Delete the repo](./images/delete-the-repo.png)
</details>

### 4. Clone the Forked Repo
Now you need to clone the forked project to your computer. Follow the next steps (and see screenshots below):

- Click the green `Code` button.
- Select the `HTTPS` tab.
- Ensure the link contains your GitHub name (NOT `mate-academy`).
- Copy the link.
- Open **Git Bash** (Windows) or **ZSH** (macOS) in your projects folder (You installed it in the Git and Terminal course).
- Run `pwd` in the terminal to check that you are in the `projects` folder.
  - If not, navigate to it using the `cd` command with the required path.
- Clone the repo by running the `git clone` command with the URL you copied on GitHub.
    ```shell
    git clone replace-this-with-the-URL-from-github
    ```

<details>
  <summary><b>How to open Git Bash</b></summary>

  ![Git Bash here](./images/git-bash-here.png)
</details>
<details>
  <summary><b>How to paste the project URL to Terminal (Git Bash)</b></summary>

  ![How to paste the URL into the terminal](./images/paste-url-to-terminal.png)
</details>
    
![Clone the repo](./images/clone-the-repo.png)
![Clone success](./images/clone-success.png)

### 5. Open the Project in VSCode
Now you need to open the project in your code editor (`VSCode`).
- Run `code project-name` in the terminal (for example, `code layout_hello-world`).
- You will see the project name as a root folder name in VSCode.

![The project opened correctly](./images/project-in-vscode-correct.png)

<details>
  <summary><b>Project is opened WRONG</b></summary>

  ![The project opened correctly](./images/project-in-vscode-wrong.png)
</details>

### 6. Open the Terminal
- Use the shortcut ``ctrl + ` `` (Windows) or ``cmd + ` `` (MacOS).
- Check if you are inside the project (The project name is the last part in the terminal).
- Check if the terminal in VSCode is Git Bash (Windows) or ZSH (macOS).

<details>
 <summary><b>Click here to see how to select the default terminal in VSCode</b></summary>

 - Choose the `Select default shell` option. ![Select default shell](./images/select-default-shell.png)
 - Select Git Bash (Windows) or zsh (macOS). ![Default shell popup](./images/default-shell-popup.png)
 - Close all the opened terminals.
 - All the new terminals will be Git Bash (or zsh).
</details>

### 7. `npm install` (or just `npm i`).
And wait until it downloads all the packages and finishes.

> Note: You should run it once for every new task.

<details>
 <summary><b>If you don't have Node.js</b></summary>

 ![If you don't have Node.js](./images/if-you-dont-have-node-js.png)
</details>

<details>
 <summary><b>If you run `npm i` outside the project</b></summary>

 ![If you run npm install outside the project](./images/if-you-run-npm-i-outside-the-project.png)
</details>

### 8. `npm start` to Open the Page

The command in the terminal will never finish.

- The command should open your browser at `http://localhost:8080/`.
- At this point, you should see the starting markup of the page.
- If the page is empty, add some text to the `<body>` in the `src/index.html` file.
- The text should appear in the browser.

<details>
 <summary><b>If the page is still empty after you added some text</b></summary>

 - Update the page by pressing `ctrl + r` (`cmd + r` for macOS).
 - If the page is still empty, check if you saved the changes. ![Autosave is disabled](./images/autosave-is-disabled.png)
 - Enable autosave. ![Enable autosave](./images/enable-autosave.png)
</details>

<details>
 <summary><b>If the page is opened at a different port (not :8080)</b></summary>

 - If you see a different port. ![Wrong port](./images/wrong-server-port.png)
 - It means you already have another terminal running the `npm start` command (maybe it is another project).
 - Stop the `npm start` command in the current terminal by pressing `ctrl + c` (all operating systems).
 - Close the other terminal running `npm start`.
 - Run the command again for your current project.
 - The URL should now be `http://localhost:8080/`.
 - If the URL is still wrong, just restart the computer.
</details>

### 9. Open One More Terminal for the Next Steps.

Use `+` or just press ``ctrl + shift + ` `` or ``cmd + shift + ` ``.

![Open one more terminal](./images/open-one-more-terminal.png)

### 10. Create the `develop` Branch

Run:
```
git checkout -b develop
```
or
```
git switch -c develop
```

<details>
  <summary><b>If you see that the "develop" branch already exists</b></summary>

  ![Develop already exists](./images/develop-already-exists.png)
  - Run `git branch` to see all existing branches. ![Show git branches](./images/show-git-branch.png)
  - If `develop` is marked with `*`, then everything is correct.
  - Otherwise, run `git checkout develop` (without the `-b` key). ![Switch to develop](./images/switch-to-develop.png)
</details>

### 11. Update `DEMO LINK` and `TEST REPORT LINK`
- Open the `readme.md` file.
- Replace the text `<your_account>` with your GitHub username in the `DEMO LINK` and `TEST REPORT LINK`.

![Update demo link](./images/update-demo-link.png)

### 12. Implement the task described in the `readme.md`. 

You should write the code in `index.html` and other files inside the `src` folder.

### 13. `npm run lint` to Check the Code Style
Run:
```
npm run lint
```

<details>
  <summary><b>If you have some errors</b></summary>

  - Fix all the errors and run the command again.

  ![Linter errors](./images/linter-errors.png)
</details>

<details>
  <summary><b>How to find the lines with linter errors</b></summary>

  ![The lines with errors](./images/lines-with-linter-errors.png)
</details>

<details>
  <summary><b>This error means you need to fix CRLF</b></summary>

  ![CRLF linter error](./images/crlf-linter-error.png)

  - Run `git config --global core.autocrlf false`.
  - Then, fix the CRLF in all the files you changed.

  ![CRLF in current file](./images/crlf-error-after-global-config.png)
</details>

<details>
  <summary><b>How to fix autoformatting in VSCode</b></summary>

  - Here is [the documentation](https://code.visualstudio.com/docs/languages/html#_formatting). 
  - Run `Alt + Shift + F` to format the document.

  ![HTML autoformat settings](./images/html-autoformat-settings.png)
  ![HTML autoformat json](./images/html-autoformat-json.png)
</details>

### 14. `npm test` to Check if Solution is Correct
- Read the `checklist.md`;
- Fix your code if needed;
- Run `npm run lint` again to ensure nothing is broken.
- Run the tests:
    ```
    npm test
    ```
- Test results should be opened in a browser;
- If not, check if you fixed all the code style errors (`npm run lint`).

#### If you see a failing test

Fix your HTML and CSS to make your page identical to the expected result.

![Failed tests](./images/failed-tests.png)
![How to compare a test with reference](./images/how-to-compare-test-with-reference.png)

#### If you need to debug tests
- [Open this DOC](layout-tests.md)

> If you can't run tests for some reason, just use a screenshot from
  `backstop_data/bitmaps_reference/Entire_document.png` to ensure your page looks as expected.

### 15. `git add` to Prepare Changed Files for Saving
```
git add ./src
```
- Don't add irrelevant files at this point, like `package-lock.json` or test snapshots.
- You can always check which files were changed or added using the `git status` command.
- Also, don't forget to add the readme.md file.
```
git add readme.md
```

### 16. `git commit` to Save Changes

Run the `commit` with a message describing what this code does.

```
git commit -m 'add task solution'
```

<details>
  <summary><b>fatal: unable to auto-detect email address</b></summary>

  - It means you forgot to configure your GIT name and email.
  - See the commands above the error message and run them one by one with your email and name.

  ![If you forgot to set GIT name and email](./images/forgot-to-configure-git.png)
  ![Set GIT name and email](./images/set-git-name-and-email.png)
</details>

<details>
  <summary><b>no changes added to commit</b></summary>

  ![No changes added to commit](./images/no-changes-added-to-commit.png)
</details>

<details>
  <summary><b>LF will be

 replaced with CRLF</b></summary>

  - You forgot to fix CRLF.

  ![Forgot to fix CRLF](./images/forgot-to-fix-crlf.png)
</details>

### 17. `git push origin develop` to send your code to GitHub
Run:
```
git push origin develop
```

<details>
  <summary><b>failed to push some refs</b></summary>

  ![Forgot to create develop](./images/forgot-to-create-develop.png)
  ![Reset and create develop](./images/reset-head-and-create-develop.png)

  - Commit changes again after creating the `develop` branch. 
</details>

<details>
  <summary><b>If you are asked for Authorization</b></summary>

  ![GitHub auth popup](./images/github-auth-popup.png)
  ![Authorize GIT credentials manager](./images/authorize-git-credentials-manager.png)
  ![Push success](./images/push-success.png)
</details>

<details>
  <summary><b>fatal: unable to access</b></summary>

  ![Permission denied](./images/permissions-denied.png)
  ![Add correct origin](./images/add-correct-origin.png)
</details>

### 18. `npm run deploy` to Publish to GitHub Pages.
Run:
```
npm run deploy
```

> If you are getting some errors, run `npm run deploy -- -l` to see more details.

The deploy process requires some time to prepare your page on GitHub after the command is finished.

To check if the page was deployed successfully, you need to check in the project settings on GitHub:
- Open the forked repo on GitHub;
- Click the `Settings` tab at the top;
- Choose the `Pages` section from the panel on the left;
- There should be a link to your public page at the top (the same as your `DEMO LINK` in the `readme.md`).
- If there is no link at the top, check if the `gh-pages` branch appeared in the repo;
  - If not, run `npm run deploy -- -l` to see more details.
- Wait for about 2 minutes and reload the `Settings > Pages` again to see the link;
- Open it to see your page.

### 19. Create a Pull Request (PR)
- Select the `Pull Requests` tab;
- Click the `New pull request` green button;
- Change the `compare` branch on the right to `develop`;
- Click the `Create pull request` button;
- Copy the `DEMO LINK` and `TEST REPORT LINK` from `readme.md` to the PR description;
  - Links should contain your GitHub name (not `mate-academy`)!!!
- Click the `Create pull request` button one more time;
- Check that your `DEMO LINK` and `TEST REPORT LINK` work as expected (open the page and test results);
- Check if the task appeared in the table (only for full-time students).

![New pull request](./images/new-pull-request.png)
![Create pull request](./images/create-pull-request.png)
![Add DEMO Links](./images/add-demo-links.png)

> ❗ Do NOT close the PR and ❗ do NOT open several PRs.
> Only the first PR made after the fork is synced to the platform.

- If you have closed the PR - reopen it and request mentor review.
- If you can't open the PR - do another fork and create a new PR.

<details>
  <summary><b>Check your DEMO LINK</b></summary>

  - You forgot to put your GitHub name into `DEMO_LINK` and `TEST_REPORT_LINK`.

  ![Forgot to fix DEMO LINK](./images/forgot-to-put-your-name-to-demo-link.png)
</details>

<details>
  <summary><b>Check your TEST REPORT LINK</b></summary>

  - You forgot to run tests before `npm run deploy`.

  ![Forgot to run tests before deploy](images/forgot-to-run-tests-before-deploy.png)
</details>

### 20. To update your PR, repeat steps 13-18 (no need to create the PR one more time).

> If you need an ADDITIONAL CODE REVIEW, click on the re-request button on the PR page.
![Image of re-request button](https://user-images.githubusercontent.com/38065883/104471439-89929200-55c3-11eb-824a-596bfb8aa246.png)

## Linux Users
> If you use _Linux_, please make sure you adjusted writing permissions to let 
scripts work without `sudo`. Correct permissions mean you don't see errors like
`permission denied` after running commands in the terminal.

## NPM Commands
- `npm install` installs the project dependencies and runs `postinstall`
  - This creates reference files for pixel-perfect and tests
- `npm start` runs the server required for development and tests
- `npm test` runs the linter and tests
  - `npm run lint` runs the linter (code style check)
  - `npm run test:only` runs pixel-perfect tests
- `npm run deploy` publishes the page and test report to `gh-pages`

## Useful Links
- [How to Understand and Debug Layout Tests](layout-tests.md)
- [HTML, CSS Code Style Rules](html-css-code-style-rules.md)
- [Working with Figma](./figma.md)
- [Useful GIT Commands](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [Terminal Commands](https://mate-academy.github.io/fe-program/tools/terminal/useful-commands)
- [Creating a Pull Request from a Fork](https://help.github.com/en/articles/creating-a-pull-request-from-a-fork)
