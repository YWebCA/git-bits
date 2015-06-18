# Git Bits

Worksheets for learning Git and GitHub

## Getting Started

This document assumes that you're working with OS X Mavericks or Yosemite and
have already installed the XCode command line tools.

Pick an email address that you intend to use for your professional life. It's
vitally important that you use this same email address for everything we do in
this configuration.

### Sign up for GitHub

Browse to [http://www.github.com](github.com) and sign up for an account. Please
pick your handle (username) carefully. As a developer, your GitHub handle is the
way by which a lot of the community will know you. It should reflect your
professional Internet persona. And if you have a Twitter account, you might
consider matching your GitHub and Twitter usernames so it's easier for people
you meet in meatspace to find you. It's totally valid to use some or all of your
real name in your GitHub handle.

### Configure Git

Open iTerm. Remember that `$` stands for your command prompt.

In the next commands, replace `Your Actual Name` with your actual name and
`Your Actual Email` with your actual email. **Keep** the quotation marks.

    $ git config --global user.name "Your Actual Name"
    $ git config --global user.email "Your Actual Email"
    $ git config --global color.ui auto

#### Verify

    $ git config --get user.name

Expected output: your name

    $ git config --get user.email

Expected output: your email address

### Create an SSH key

    $ ls ~/.ssh/id_rsa

Expected result:

    No such file or directory

Do, replacing `student@example.com` with your actual email address:

    $ ssh-keygen -C student@example.com -t rsa

You will be asked for a **passphrase**. Press [RETURN] to accept a
blank passphrase.

Expected result:

    Generating public/private rsa key pair.
    Enter file in which to save the key (/Users/student/.ssh/id_rsa):
    Created directory '/Users/student/.ssh'.
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /Users/student/.ssh/id_rsa.
    Your public key has been saved in /Users/student/.ssh/id_rsa.pub.
    The key fingerprint is:
    88:54:ab:77:fe:5c:c3:7s:14:37:28:8c:1d:ef:2a:8d student@example.com

### Verify and Use

    $ eval "$(ssh-agent -s)"
    $ ssh-add ~/.ssh/id_rsa

Expected result:

    Enter passphrase for /Users/student/.ssh/id_rsa:
    Identity added: /Users/student/.ssh/id_rsa (/Users/student/.ssh/id_rsa)"

### Add your SSH key to GitHub

    $ pbcopy < ~/.ssh/id_rsa.pub

1.  Go to GitHub and sign in.
2.  Click your profile picture and choose **Settings**.
3.  In the menu on the left, click **SSH keys**.
4.  Click the **Add SSH key** button.
5.  In the Title field, add a descriptive label for the new key. For example,
    you might call this key "YWeb MacBook Air".
6.  Paste [Command+V] your key into the **Key** field.
7.  Click the **Add key** button.
8.  Confirm by entering your GitHub password.

#### Verify

    $ ssh -T git@github.com

You may get this warning:

    The authenticity of host 'github.com (207.97.227.239)' can't be established.
    RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
    Are you sure you want to continue connecting (yes/no)?

If so, type:

    $ yes

Expected output:

    Hi username! You've successfully authenticated, but GitHub does not
    provide shell access.

## Where to Go Next

Follow the in-class instruction.
