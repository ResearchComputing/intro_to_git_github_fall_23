# Introduction to Git and GitHub

You’ve probably heard of GitHub, but maybe you're not quite sure what it's all about or the best ways to use 
it. In this introductory workshop, we'll demystify the world of version control and provide an introduction 
to both Git and GitHub. We'll cover what these widely used tools are, when (and when not to) use them as part 
of your research process, and provide examples of workflows that allow individuals to collaborate using Git 
and GitHub. Then we'll jump into some hands-on experience with a walkthrough of how to create and update Git 
repositories.

Please note that no programming knowledge is necessary. However, this is meant to be a highly interactive 
workshop and will involve some use of the command line interface. Thus, you should ensure that you have a 
laptop that has Git installed on it or that you can access CU Research Computing resources via a terminal. 

## Git/GitHub Homework

For this presentation we will be doing a hands on tutorial. To make this tutorial run 
smoothly, you can use CU Research Computing Resources (CURC), if you have access to 
our system. If you do have access to our system, please follow the following instructions
to setup Git for your username. 

1. Create a free account at: https://github.com/signup
    - Remember the email you used!

2. SSH into a login node:
    ```
    ssh <username>@login.rc.colorado.edu
    ```

    or 

    Open up a terminal in Open OnDemand.

3. Add your git user name
    ```
    git config --global user.name <github user name>
    ```

4. Add your git user email
    ```
    git config --global user.email <github account email>
    ```

5. Check that everything was set (should display user.name and user.email)
    ```
    git config --list
    ```

6. Create your ssh key
    ```
    ssh-keygen -t ed25519 
    ```
    - Press enter for all prompts (accepts default options)
    - This will put the ssh key in `~/.ssh/`

7. Display your public key so we can provide it to GitHub:
    ```
    cat ~/.ssh/id_ed25519.pub
    ```

8. Go to [github.com](https://github.com/) and follow this procedure:
    - Login, if you are not
    - Click on the drop-down menu on your profile icon located in the top right corner
    - Select "Settings" from the drop-down menu
    - On the left hand side under the "Access" section select "SSH and GPG keys"
    - Click the green box that says "New SSH key"
    - Add a title (e.g. my_rc_key)
    - Leave "Key type" as "Authentication Key"
    - In the "Key" box paste your ssh key provided by step 7. You do not need to include 
the end portion "<username>@loginXX"
    - Select "Add SSH key"
   
9.  Add the following to `~/.ssh/config`:
    ```
    Host github.com
        Hostname github.com
        IdentityFile ~/.ssh/id_ed25519
        IdentitiesOnly yes
    ```

10. Verify that your ssh key has been correctly set up:
    ```
    ssh -T git@github.com
    ```

    - You should see the message: "Hi \<username\>! You've successfully authenticated, but GitHub does not 
provide shell access."

=======
### Setup Git on your Windows Computer

2. Download and run the Git for Windows setup program from https://git-scm.com/download/win

3. Select launch Git Bash

4. Add your git user name
    ```
    git config --global user.name "[github user name]"
    ```
	
4. Add your git user email
    ```
    git config --global user.email "[github account email]"
    ```

5. Check that everything was set (should display user.name and user.email)
    ```
   git config --global user.name
   git config --global user.email
    ```

6. Install GitHub CLI (Command Line Interface)
    ```
	winget install --id GitHub.cli 
    ```
	Select Y

7. Open Windows Command Prompt
    ```
	gh auth login
	```
8. Select "GitHub.com"

9. Select "HTTPS"

10. When prompted with "Authenticate with your GitHub credentials" type Y and Enter

11. Select "Login with web browser"

12. Copy your one time code

13. Press Enter to open GitHub in a browser

14. Login to your GitHub account

15. Enter the one time code
