# Help
A curated list of online resources for use in software development and associated tasks.

## Licensing
This documentation is licensed under a [Creative Commons Attribution Share Alike 4.0 International license (CC BY-SA 4.0)](
https://creativecommons.org/licenses/by-sa/4.0/) that grants you the rights to distribute and modify this information for personal or commercial use. All I ask in return is that you distribute this information under the same terms, indicate any changes you make, and tip your hat to me for having compiled the list in the first place.

For information on selecting an open source license for your own projects see [Choose a license](https://choosealicense.com).

## Text formatting
This README file is written in **Markdown**, a lightweight markup language used to add formatting elements to plaintext documents. Markdown’s syntax is simple but powerful and designed to be readable even when not rendered. In this regard Markdown is much better than Hypertext Markup Language (HTML), which can be difficult to read in its raw form.

If you’ve never used Markdown before then the easiest way to get started is to read the quick reference guide [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/).

## Git and GitHub
This project is a *repository* of documents hosted on [GitHub](https://github.com). It is a collection of files managed by a program called **Git**, which is a distributed version control system used to track changes to those files over time and by multiple contributors. **GutHub** is a cloud-based service that hosts git repositories, making it easier to share projects and to collaborate on them.

Git can seem complicated and daunting to use at first. However, the basics are quite simple. Nick White on YouTube has created a video called “[Git Tutorial For Dummies](https://youtu.be/mJ-qvsxPHpY?si=oS7hqYT3JCGlbfOy)” that explains how to get started. Nick’s delivery is somewhat exasperated and his use of the Dummies’ logo probably infringes upon Wiley’s trademark but his explanation is short and to the point.

Elsewhere on GitHub, Kate Hudson has created a list of basic git instructions that include ways to recover from common mistakes. “[Flight rules for Git](https://github.com/k88hudson/git-flight-rules)” is inspired by the *Flight Rules* document written by *NASA* technicians since the 1960s. It can be handy to refer to when things don’t go quite right.

### Linking local git repositories to GitHub
The whole point of using GitHub is to store your local repositories in the cloud, either as a backup or to share them with others. For this to work you must be able to `push` files to GitHub's remote servers. However, if you follow their own instructions when making a new repository you will receive an error:
 
     user:~/dev/my_repo$ git push -u origin main
     Username for 'https://github.com': my@username.com
     Password for 'https://my@username.com@github.com':
     remote: Support for password authentication was removed on August 13, 2021.
     remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-
     repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
     fatal: Authentication failed for 'https://github.com/MyUser/my_repo.git/'

This is because GitHub has (quite rightly) disabled password authentication to make their site more secure. To resolve this it is necessary to create a **secure shell** [SSH] **pass key**.

The process of creating a SSH passkey is mostly described in [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh). Following this guide will allow you to create a public and private key pair, store the private key on your local computer, and copy the public key to your GitHub account. Note it will be necessary to store the public key *twice*: once as an Authentication key and again as a Signing key.

What this guide fails to mention is that the URL given in the `push` instructions is wrong! It can only be used with password authentication, which we now know is disabled. Instead, the remote origin URL must be pointed to GitHub's SSH server:

  	user:~/dev/my_repo$ git remote set-url origin git@github.com:MyUser/my_repo.git

Once the correct URL has been set the git commands will work as expected.

## Questions and answers

