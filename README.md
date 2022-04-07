# How to solve the layout tasks on Github
<details>
  <summary><b>If you are not familiar with Git and Github</b></summary>

  - **IMPORTANT** Install Node.js 14 (not 15)
  - Watch the [Git and Github lesson](https://mate.academy/ru/learn/javascript-advanced/git-basics/theory)
  - Finish [githowto](https://githowto.com/)
  - Learn how to use [GitHub Pages](https://pages.github.com/)
  - Read about [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
  - Create a repo following [this workflow](./github-workflow.md)
</details>

> Learn [Useful GIT commands](https://mate-academy.github.io/fe-program/tools/git/useful-commands)

> Learn [Terminal commands](https://mate-academy.github.io/fe-program/tools/terminal/useful-commands)

## !!!!!!!!! MUST READ !!!!!!!

To avoid permissions issues **DO NOT place your projects folder on desktop**
There should be **NO SPACES in the path**. e.g. `C:\Users\Your Name\projects`.
It is better to put repositories into `D:\projects` or `C:\Users\YourName\projects`.

## Follow this steps:
1. Open the task on the platform and click `Make a fork`
2. Open the project on Github and **Fork** the repo.
    <details>
      <summary>Show the screenshot</summary>
  
      - Before the fork ![How to fork the repo](./images/fork-the-repo.png)
      - After the fork ![After the repo fork](./images/after-the-repo-fork.png)
    </details>

    <details>
      <summary>If you want to delete the repo</summary>

      - Open project settings ![Open project settings](./images/open-project-settings.png)
      - Delete the repo ![Delete the repo](./images/delete-the-repo.png)
    </details>
3. Update the topic on the platform to see that the button changed to `Open the task`
    - if not open personal data and connect your github account
4. **Clone** the forked repo be running `git clone the-link-from-github` (!!! Replace `the-link-from-github` with link from your repo)
    <details>
      <summary>Show the details</summary>

      - Open **Git Bash** (Windows) or **Terminal** (macOS) in your projects folder
      - The path to your projects should not contain spaces or non-latin letters
      - run `git clone the-link-from-github`
      - The project link should have your name but not `mate-academy`
        ![Clone the repo](./images/clone-the-repo.png)
    </details>
   
    <details>
      <summary>How to open Git Bash</summary>
   
      ![Git Bash here](./images/git-bash-here.png)
    </details>

    <details>
      <summary>How to paste the project URL to Terminal (Git Bash)</summary>
   
      ![How to paste the URL into terminal](./images/paste-url-to-terminal.png)
    </details>

    <details>
      <summary>Clone success screenshot</summary>
   
      ![Clone success](./images/clone-success.png)
    </details>

5. Open the project in IDE
    - run `code layout_hello-world`
    - or just run VSCode and open the project folder
  
    <details>
      <summary>Project is opened correctly</summary>
   
      ![The project opened correctly](./images/project-in-vscode-correct.png)
    </details>

    <details>
      <summary>Project is opened WRONG</summary>
   
      ![The project opened correctly](./images/project-in-vscode-wrong.png)
    </details>

6. Open the Terminal in your IDE
   <details>
     <summary>Show the details</summary>
   
     - Use the shortcut ``ctrl + ` ``
     - Check if you are inside the project (The project name is the last part in the terminal)
     - Check if you use Git Bash (Windows) of zsh (macOS)
   </details>
   
   <details>
     <summary>How to Select default shell</summary>
   
     - Choose `Select default shell` option ![Select default shell](./images/select-default-shell.png)
     - Select Git Bash (Windows) or zsh (macOS) ![Default shell popup](./images/default-shell-popup.png)
     - Close all the opened terminals
     - All the new terminals will be Git Bash (or zsh)
   </details>

7. Run `npm install` (or just `npm i`).
   <details>
     <summary>If you don't have Node.js</summary>
   
     ![If you don't have Node.js](./images/if-you-have-node-15.png)
   </details>
   
   <details>
     <summary>If you run `npm i` outside the project</summary>
   
     ![If you run npm install outside the project](./images/if-you-run-npm-i-outside-the-project.png)
   </details>
   
   <details>
     <summary>If you have Node.js 15 or later</summary>
   
     ![If you have Node.js 15 or later](./images/if-you-have-node-15.png)
   </details>
   
   <details>
     <summary>How to reinstall Node.js</summary>
   
     - Open `Add and remove programs` ![Open Add and Remove programs](./images/open-add-remove-programs.png)
     - Uninstall Node.js ![Uninstall Node.js](./images/uninstall-node-js.png)
     - Download and install Node.js https://nodejs.org/download/release/v14.16.1/ 
     - Delete `node_modules` ![Delete node_modules](./images/delete-node-modules.png)
     - Run `npm i` again ![npm install success](./images/npm-install-success.png)
   </details>

8. Run `npm start` to check if it works. (Terminal command will never finish, so you need one mote terminal)
   <details>
     <summary>Show the details</summary>

     - At this point you should see the starting markup of the page at `http://localhost:8080/` opened in your Google Chrome
     - Add some text to `src/index.html`. The change should be immediately updated in the browser.
     - If the page is not updated automatically press `ctrl + r` (`cmd + r` for macOS)
   </details>

   <details>
     <summary>If the page is empty after you added some text</summary>
   
     - Update the page by pressing `ctrl + r` (`cmd + r` for macOS)
     - If the page is still empty check if you saved the changes ![Autosave is disabled](./images/autosave-is-disabled.png)
     - Enable autosave ![Enable autosave](./images/enable-autosave.png)
   </details>
   
   <details>
     <summary>If the page is opened at the other port (not :8080)</summary>
   
     - If you see the other port ![Wrong port](./images/wrong-server-port.png)
     - It means you already have another terminal running `npm start` command (maybe it is another project)
     - Stop the `npm start` command in current terminal by pressing `ctrl + c` (all operating systems)
     - Close the other terminal running `npm start`
     - Run the command again for your current project
     - The URL should be now `http://localhost:8080/`
     - If the URL is still wrong, just restart the computer
   </details>

9. Open one more terminal for the next steps.
   <details>
     <summary>Show the screenshot</summary>
   
     ![Open one more terminal](./images/open-one-more-terminal.png)
   </details>

10. Create the `develop` branch (run `git checkout -b develop`)
    <details>
      <summary>If you see that develop already exists</summary>
   
      ![Develop already exists](./images/develop-already-exists.png)
      - run `git branch` to see all existent branches ![Show git branches](./images/show-git-branch.png)
      - If `develop` is marked with `*` then everything is correct
      - Otherwise, run `git checkout develop` (without `-b` key) ![Switch to develop](./images/switch-to-develop.png)
    </details>

11. Open `readme.md` file and replace a text `<your_account>` with your Github username in the `DEMO LINK` and `TEST REPORT LINK`
    <details>
      <summary>Example</summary>
    
      ![Update demo link](./images/update-demo-link.png)
    </details>

12. Implement the task described in the `readme.md`. 
    - You should write the code in `index.html` and other files inside `src` folder.
    
13. Run `npm run lint` to check the code style.
    <details>
      <summary>If you have some errors</summary>

      - Fix all the errors and run the command again

      ![Linter errors](./images/linter-errors.png)
    </details>

    <details>
      <summary>How to find the lines with linter errors</summary>
    
      ![The lines with errors](./images/lines-with-linter-errors.png)
    </details>

    <details>
      <summary>This error means you need to fix CRLF</summary>
    
      ![CRLF linter error](./images/crlf-linter-error.png)

      - run `git config --global core.autocrlf false`
      - and fix the CRLF in all the files you changed
  
      ![CRLF in current file](./images/crlf-error-after-global-config.png)
    </details>

    <details>
      <summary>How to fix autoformatting in VSCode</summary>

      - Here is [the documentation](https://code.visualstudio.com/docs/languages/html#_formatting) 
      - Run `Alt + Shift + F` to format the document

      ![HTML autoformat settings](./images/html-autoformat-settings.png)
      ![HTML autoformat json](./images/html-autoformat-json.png)
    </details>

14. To check if your solution matches all the expectations you can run `npm test`
    - If test results are not opened in a browser, check if you fixed all the code style errors (`npm run lint`)
    - If you can't run tests for some weird reason just use a screenshot from
      `backstop_data/bitmaps_reference/Entire_document.png` to ensure your page looks as expected.

    <details>
      <summary>If you see a failing test</summary>
  
      ![Failed tests](./images/failed-tests.png)
      ![How to compare a test with reference](./images/how-to-compare-test-with-reference.png)
    </details>
    
    <details>
      <summary>If you see ERR_CONNECTION_REFUSED</summary>

      ![Connection refused error](./images/connection-refused-error.png)

      - it means you don't have a running server
      - Open new terminal and run `npm start`
      - Check if the page is opened at `:8080` port (`http://localhost:8080/`)
      - Run `npm test` again to see the results
    </details>

15. Add your changed or created files to commit history `git add path/to/changed_file path/to/new_file`
`git commit -am 'some message'`
    - You can add all files in a certain folder using `.` character: `git add src/.`
    - Don't add irrelevant files at this point, like `package-lock.json` or test snapshots.
    - You can always check which files were changes or added using `git status` command.

16. Create a commit with all added files using `git commit -m 'commit message'`
    - Commit message should describe the changes made in the files, e.g. `'added header'`
      
    <details>
      <summary>fatal: unable to auto detect email address</summary>

      - it means you forgot to configure you GIT name and email
      - See the commands above the error message and run them one by one with your email and name

      ![If you forgot to set GIT name and email](./images/forgot-to-configure-git.png)
      ![Set GIT name and email](./images/set-git-name-and-email.png)
    </details>

    <details>
      <summary>no changes added to commit</summary>
    
      ![No changes added to commit](./images/no-changes-added-to-commit.png)
    </details>
    
    <details>
      <summary>LF will be replaced with CRLF</summary>
    
      - You forgot to fix CRLF 
  
      ![Forgot to fix CRLF](./images/forgot-to-fix-crlf.png)
    </details>
    
17. Send your code to Github by running `git push origin develop`
    <details>
      <summary>failed to push some refs</summary>

      ![Forgot to create develop](./images/forgot-to-create-develop.png)
      ![Reset and create develop](./images/reset-head-and-create-develop.png)
    
      - Commit changes again after creating `develop` branch 
    </details>

    <details>
      <summary>If you asked for the Authorization</summary>
    
      ![Github auth popup](./images/github-auth-popup.png)
      ![Authorize GIT credentials manager](./images/authorize-git-credentials-manager.png)
      ![Push success](./images/push-success.png)
    </details>

    <details>
      <summary>fatal: unable to access</summary>
    
      ![Permission denied](./images/permissions-denied.png)
      ![Add correct origin](./images/add-correct-origin.png)
    </details>

18. Run `npm run deploy` to publish your site to GitHub pages.
    - Open `Setting` tab of your repo on Github and choose `Pages` section from panel on the left
    - There should be a link to your public page (the same as `DEMO LINK` in your `readme.md`)
    - Wait until it becomes green (refresh a page if needed)
    - Open the page and check if you see the all the latest changes
    - If the page is not updated yet, just add `?any-random-text` after the URL in the Browser
      and press `Enter` to reload the page discarding cached data (if any)

19. Create a Pull Request (PR) from your branch `develop` to branch `master` of original repo.
    - Select `Pull requsts`
    - Click `New pull request` button
    - Change the branch to `develop`
    - Click `Create pull request` button
    - Copy `DEMO LINK` and `TEST REPORT LINK` from `readme.md` to the PR description.
    - Click `Create pull request` button one more time

    <details>
      <summary>New pull request</summary>

      ![New pull request](./images/new-pull-request.png)
    </details>

    <details>
      <summary>Create pull request</summary>

      ![Create pull request](./images/create-pull-request.png)
    </details>

    <details>
      <summary>Check your DEMO LINK</summary>

      - You forgot to put your Github name into `DEMO_LINK` and `TEST_REPORT_LINK`

      ![Forgot to fix DEMO LINK](./images/forgot-to-put-your-name-to-demo-link.png)
    </details>

    <details>
      <summary>Check your TEST REPORT LINK</summary>

      - You forgot to run tests before `npm run deploy`

      ![Forgot to run tests before deploy](images/forgot-to-run-tests-before-deploy.png)
    </details>
    
20. Check your work using checklist (look for it in the root directory of the project) before submitting it for review.
21. To update you PR repeat steps 13-17 (no need to create the PR one more time).

> If you need an ADDITIONAL CODE REVIEW, click on re-request button at the PR page.
![Image of re-request button](https://user-images.githubusercontent.com/38065883/104471439-89929200-55c3-11eb-824a-596bfb8aa246.png)

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
- [Useful GIT commands](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [Terminal commands](https://mate-academy.github.io/fe-program/tools/git/useful-commands)
- [HTML, CSS styleguide](https://mate-academy.github.io/style-guides/htmlcss.html)
- [Working with figma](./figma.md)
- [Creating a pull request from a fork](https://help.github.com/en/articles/creating-a-pull-request-from-a-fork)
- [How to use pixel perfect extension](https://youtu.be/zqRko57AurU)
