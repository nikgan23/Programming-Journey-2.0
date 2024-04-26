### [Introduction](https://www.theodinproject.com/lessons/foundations-setting-up-git#introduction)

[Git](https://git-scm.com/) is a very popular version control system. You’ll become very familiar with this piece of software throughout TOP, so don’t worry too much about understanding it at this point. There are many lessons focused on Git later in the curriculum.

[GitHub](https://github.com/) is a service that allows you to upload, host, and manage your code using Git with a nice web interface.

Even though GitHub and Git sound like they could be the same thing, they are not the same thing or even created by the same company.

### [Step 1: Install Git](https://www.theodinproject.com/lessons/foundations-setting-up-git#step-1-install-git)

Click the Operating System you have chosen below:

Linux

MacOS

[](https://docs.brew.sh/Installation#macos-requirements)

2. [![Brew Doctor Sample Output](https://cdn.statically.io/gh/TheOdinProject/curriculum/284f0cdc998be7e4751e29e8458323ad5d320303/foundations/installations/setting_up_git/imgs/00.png)](https://cdn.statically.io/gh/TheOdinProject/curriculum/284f0cdc998be7e4751e29e8458323ad5d320303/foundations/installations/setting_up_git/imgs/00.png)

ChromeOS

[](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-debian-10#installing-git-from-source)

### [Step 2: Configure Git and GitHub](https://www.theodinproject.com/lessons/foundations-setting-up-git#step-2-configure-git-and-github)

#### Step 2.1: Create a GitHub account

Go to [GitHub.com](https://github.com/) and create an account! During the account setup, it will ask you for an email address. This needs to be a real email, and will be used by default to identify your contributions. If you are privacy conscious, or just don’t want your email address to be publicly available, make sure you tick the following two boxes on the [Email Settings](https://github.com/settings/emails) page after you have signed in:

[![GitHub Email Settings](https://cdn.statically.io/gh/TheOdinProject/curriculum/770be14190139683dbe9933ca5e9393c797c63f2/foundations/installations/setting_up_git/imgs/01.png)](https://cdn.statically.io/gh/TheOdinProject/curriculum/770be14190139683dbe9933ca5e9393c797c63f2/foundations/installations/setting_up_git/imgs/01.png)

Having these two options enabled will prevent you accidentally exposing your personal email address when working with Git and GitHub.

You may also notice an email address under the **Keep my email addresses private** option, this is your private GitHub email address. If you plan to use this, make note of it now as you will need it when setting up Git in the next step.

#### Step 2.2: Setup Git

For Git to work properly, we need to let it know who we are so that it can link a local Git user (you) to GitHub. When working on a team, this allows people to see what you have committed and who committed each line of code.

The commands below will configure Git. Be sure to enter your own information inside the quotes (but include the quotation marks)!

```bash
git config --global user.name "Your Name"
git config --global user.email "yourname@example.com"
```

Copy

If you opted to use the private GitHub email address, the second command will look something like this:

```bash
git config --global user.email "123456789+odin@users.noreply.github.com" # Remember to use your own private GitHub email here.
```

Copy

GitHub recently changed the default branch on new repositories from `master` to `main`. Change the default branch for Git using this command:

```bash
git config --global init.defaultBranch main
```

Copy

To enable colorful output with `git`, type

```bash
git config --global color.ui auto
```

Copy

You’ll also likely want to set your default branch reconciliation behavior to merging. You’ll learn what all those terms mean later in the curriculum, but for now just know that we suggest running the below command as part of the Git setup process when doing The Odin Project.

```bash
git config --global pull.rebase false
```

Copy

To verify that things are working properly, enter these commands and verify whether the output matches your name and email address.

```bash
git config --get user.name
git config --get user.email
```

Copy

**macOS Users:** Run these two commands to tell Git to ignore .DS_Store files, which are automatically created when you use Finder to look into a folder. .DS_Store files are invisible to the user and hold custom attributes or metadata (like thumbnails) for the folder, and if you don’t configure Git to ignore them, pesky .DS_Store files will show up in your commits. Remember to copy and paste each of these commands into your terminal.

```bash
echo .DS_Store >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```

Copy

#### Step 2.3: Create an SSH key

An SSH key is a cryptographically secure identifier. It’s like a really long password used to identify your machine. GitHub uses SSH keys to allow you to upload to your repository without having to type in your username and password every time.

First, we need to see if you have an Ed25519 algorithm SSH key already installed. Type this into the terminal and check the output with the information below:

```bash
ls ~/.ssh/id_ed25519.pub
```

Copy

If a message appears in the console containing the text “No such file or directory”, then you do not yet have an Ed25519 SSH key, and you will need to create one. If no such message has appeared in the console output, you can proceed to step 2.4.

To create a new SSH key, run the following command inside your terminal.

```bash
ssh-keygen -t ed25519
```

Copy

- When it prompts you for a location to save the generated key, just push Enter.
- Next, it will ask you for a password; enter one if you wish, but it’s not required.

#### Step 2.4: Link your SSH key with GitHub

Now, you need to tell GitHub what your SSH key is so that you can push your code without typing in a password every time.

First, you’ll navigate to where GitHub receives our SSH key. Log into GitHub and click on your profile picture in the top right corner. Then, click on `Settings` in the drop-down menu.

Next, on the left-hand side, click `SSH and GPG keys`. Then, click the green button in the top right corner that says `New SSH Key`. Name your key something that is descriptive enough for you to remember what device this SSH key came from, for example `linux-ubuntu`. Leave this window open while you do the next steps.

Now you need to copy your public SSH key. To do this, we’re going to use a command called [`cat`](http://www.linfo.org/cat.html) to read the file to the console. (Note that the `.pub` file extension is important in this case.)

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy

Highlight and copy the entire output from the command. If you followed the instructions above, the output will likely begin with `ssh-ed25519` and end with your `username@hostname`.

Now, go back to GitHub in your browser window and paste the key you copied into the key field. Keep the key type as `Authentication Key` and then, click `Add SSH key`. You’re done! You’ve successfully added your SSH key!

#### Step 2.5 Testing your key

Follow the [GitHub directions for testing your SSH connection](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection?platform=linux). Make sure the fingerprint output in the terminal matches [one of the four GitHub’s public fingerprints](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints). **(Don’t forget to omit the `$` when you copy and paste the code!)**.

You should see this response in your terminal: **Hi username! You’ve successfully authenticated, but GitHub does not provide shell access.** Don’t let GitHub’s lack of providing shell access trouble you. If you see this message, you’ve successfully added your SSH key and you can move on. If the output doesn’t correctly match up, then try going through these steps again or come to [the Discord chat](https://discord.gg/fbFCkYabZB) to ask for help.

### [Step 3: Let us know how it went!](https://www.theodinproject.com/lessons/foundations-setting-up-git#step-3-let-us-know-how-it-went)

You’ve completed the basic installations section, good job! As you progress through the Paths there will be other tools to install, so keep an eye out!

You probably felt like you were way in over your head, and you probably didn’t understand much of what you were doing. That’s 100% normal. Hang in there. You can do this! And we’ve got your back.

### [Additional resources](https://www.theodinproject.com/lessons/foundations-setting-up-git#additional-resources)

This section contains helpful links to related content. It isn’t required, so consider it supplemental.

- [Understanding SSH Key Pairs](https://winscp.net/eng/docs/ssh_keys) SSH is a secure network protocol that uses an implementation of public-key cryptography, also known as asymmetric cryptography. Having a basic understanding of how it works can help you understand what an SSH key is all about.
- [Asymmetric Encryption - Simply explained](https://www.youtube.com/watch?v=AQDCe585Lnc) a short video explaining Asymmetric Encryption.