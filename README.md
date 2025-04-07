# Verified-Commits-GitHub
This is a step by step process on setting up verified commits for every commit in GitHub.

# Steps To Follow In A Nutshell.
1. **"# Steps To Create GPG Key."**
2. **"# Steps To Configure GPG Key."**
3. Close and Open the Termianl again.
4. Commit and then push your repository. You'll be asked for Passphrase you've set.
5. Once done, check GitHub and you should see the verified badge.


# Steps To Create GPG Key.
1. Download and install gpg. (https://www.gpg4win.org/)
2. Open Vscode Terminal (Preferably Powershell run as Administrator)
3. Write **"gpg --full-generate-key"** for generating gpg key.
4. Write **"1"** to choose **"(1) RSA and RSA"** type of key.
5. Write **"4096"** for the RSA key size.
6. Write **"0"** if you want the key to never expire.
7. In **"Real Name:"** provide your real name on GitHub.
8. In **"Email address:"** provide your email address your GitHub account is set. For security, you can use your GitHub noreply email. (See **# How To Get Noreply Email From GitHub?**)
9. In **"Comment:"** you can skip by pressing enter.
10. In **"Change (N)ame, (C)omment, (E)mail, or (O)kay,/(Q)uit?"** press **"O"** to preceed further.
11. Write your passphrase. (**DO NOT SHARE THIS WITH ANYONE**).
12. Now that the key is made, we need to configure the GPG Key into the local machine. (See **# Steps To Configure The GPG Key Into The Local Machine.**)


# Steps To Configure The GPG Key Into The Local Machine.
1. In terminal write **"gpg --list-secret-keys --keyid-format=LONG"**
2. In line **"sec"** copy the string after **"rsa4096/"**. E.g., rsa4096/xxxxxxxx **(copy the x values only)**
3. Write **"gpg --armor --export"** and then your rsa4096 key. E.g., **"gpg --armor --export xxxxxxxx"**
4. Copy the generated block from **"-----BEGIN PGP PUBLIC KEY BLOCK-----"** till **"-----END PGP PUBLIC KEY BLOCK-----"**
5. Add it to your GitHub GPG Key. (See **# Steps To Configure The GPG Key In GitHub**)
6. To configure the terminal, write **"git config --global user.name "User Name"".** E.g., **"git config --global user.name "Mike Tyson""**
7. Write "git config --global user.signingkey" and write your **"Key ID"** (you can take it from your GPG Keys in the SSH and GPG Keys (Tab)). E.g., **"git config --global user.signingkey xxxxxxxx"**
8. Write **"git config --global commit.gpgsign true"**
9. Write **"git config --global tag.gpgsign true"**
10. Now we need to specify the GPG installation file for terminal. (See **"# How To Find The GPG Installation File."**)
11. Copy the path and write **"git config --global gpg.program "path/gpg.exe""** E.g., **"git config --global gpg.program "C:\Program Files\GnuPG/bin/gpg.exe""**
12. Write **"git config --global --list"** to see what we've made so far.
13. Proceed to step 3 of **"# Steps To Follow In A Nutshell."**


# Steps To Configure The GPG Key On GitHub.
1. GitHub -> Profile -> Settings -> SSH and GPG Keys
2. In GPG Keys click **"New GPG key"**
3. For title, you can use your noreply GitHub email or anything you want.
4. For Key, just paste the PGP PUBLIC KEY block and then click **"Add GPG Key"**


# How To Get Noreply Email From GitHub?
1. Login to GitHub **->** Profile -> Settings **->** Emails (Tab) **->** Copy the nonvisible email that goes as follows, xxxxxx+username@users.noreply.github.com


# How To Find The GPG Installation File?
1. Open Command Prompt (Preferrably run as administrator)
2. Write **"where gpg"**
