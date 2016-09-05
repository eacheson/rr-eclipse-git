![](figures/header.png)

# RR Workshop Tutorial: How to use Git with Eclipse

This tutorial in the context of the **Reproducible Research Workshop** provides you with the first steps on how to use Git with the Eclipse IDE. Eclipse is heavily used to program in Java, as well as in other languages like C++, and even Python (via PyDev).

The repository provides you with a step-by-step tutorial, which you are reading right now, and is at the same time the repository you _play_ with to create your first Git project in Eclipse and make some simple file changes within it.

**Objectives of this tutorial:**

* Set up and install Eclipse with EGit, and get a GitHub account
* Clone/fork an existing project from GitHub and import it into Eclipse
* Commit changes to a file in the GitHub project from Eclipse

## Part 1: Installation and setup

To get started you need the following software installed on your computer: **Eclipse**, and **EGit**. Additionally you will also need a **GitHub** account.

1. **Eclipse ([Download Eclipse](https://www.eclipse.org/downloads/)):** Download and install Eclipse (if not already installed). The recommended version tested with this tutorial is [Eclipse Mars 4.2](https://eclipse.org/downloads/packages/release/Mars/2), _Eclipse IDE for Java Developer_.
2. **EGit**: EGit is a plugin for Eclipse which allows you to interface with Git. Since version control is becoming less and less optional, EGit now comes pre-installed with Eclipse downloads! In case you do have an older version of Eclipse, install EGit as described in [Installing EGit in Eclipse] (http://eclipsesource.com/blogs/tutorials/egit-tutorial/).
3. **GitHub account**: On [GitHub](https://github.com/) create yourself a free GitHub account. _If you are new to Git follow the 15 min [TryGit Tutorial](https://try.github.io) to get a quick introduction to Git._ 
4. **Configure EGit:** to use your GitHub username and password.
  1. Click on the 'Window' menu bar option, then choose 'Preferences'.
  2. Type "git" in the search bar, then choose that path 'Team > Git > Configuration'. Click 'Add Entry...'.
  3. Enter `user.name` as the Key, and your GitHub username as the Value, then add another entry with `user.email` as the Key and your corresponding email as the Value.
    
    ![Configure EGit](figures/egit-configure.png)

## Part 2: Create a project with GitHub and Eclipse

There are a few ways you can create a version controlled project to use with Eclipse. We will focus on a very common workflow (and increasingly common as GitHub becomes more ubiquitous): first creating a "remote" repository on GitHub, then importing this repository or "repo" into Eclipse.

**1. _(Optional)_ Create a new (public or private) repo on github:** This step is optional but recommended if you are currently working on a project you want to version control. Creating your own GitHub repo is simply a matter of filling out one screen. Login to your GitHub account and create a new GitHub repository [at this link](https://github.com/new). Give your new repository a short and memorable name, ideally using lowercase letters only and dashes to separate words, e.g. `rr-eclipse-git`, and check the option to initialize this repository with a README:

  **Note:** Public repos are always free, and private repos are free when you get a free student account, and otherwise you currently have to pay $7/month to get unlimited private repos. Applying for a [free student account](https://education.github.com/pack) is highly recommended! (It will probably be several days before you get an application approved.)

  ![GitHub: Create a new repository](figures/github-create-new-repo-named.png)

  Click the green 'Create repository' button to create your repository.  
  You've just created a repo which is 'hosted' by GitHub - it's still only online for now.

**2. Clone the repo:** To get the contents of a remote repository onto your own computer, i.e. to get a 'local' copy, you have to "Clone or download" it. There are a few options here (clone or download? HTTPS or SSH? etc.) but to keep things simple, we will use **Clone** with **HTTPS**. We will use the existing tutorial repo for this step, but you could also use your own repo if you created on in Step 1 above.
  1. Go to the repo homepage at [github.com/eacheson/rr-eclipse-git](https://github.com/eacheson/rr-eclipse-git)
  2. Click the green 'Clone or download' button
  3. A menu appears, which should say 'Clone with HTTPS'; if it instead says 'Clone with SSH', click on 'Use HTTPS'
  4. Click on the copy-to-clipboard button

  ![GitHub: Copy to clipboard](figures/github-https-arrow.png)

**3. Import the repo into Eclipse:** We don't yet physically have a local copy of the repo, but Eclipse is going to take care of the details for us.
  1. Open Eclipse, with E-Git installed (you will quickly find out if you have an older version without it).
  2. In Eclipse, choose 'File' (top left), then 'Import...'
  3. In the dialog that opens, choose 'Git > Projects from Git' and click 'Next'
  4. Click on 'Clone URI', then click 'Next'
  5. Here's where some magic happens: on this next screen the details should already be filled out for you, as shown below.
    
    ![Import Projects from Git](figures/eclipse-import-repo.png)
    
    Ensure that your GitHub username and password are entered under 'Authentication', and click Next.
    
  6. For the `rr-eclipse-git` repo, there should only be one branch showing on the next screen, click 'Next'
  7. Choose a directory where the local copy of the repo should live, and click 'Next'
	*Tip*: On my Windows computer, I have a 'git' directory in my home directory, where any git projects go. So if the repo was called 'example', the directory here would be `C:\Users\eacheson\git\example`
  8. On the next screen choose 'Import as general project', click 'Next'
  9. On the final screen, keep the default Project name, which should match the repo name (this is really recommended!!), and click 'Finish'!!
 
That's it! The project should now be on your local machine, and visible in Eclipse in the 'Project Explorer'. If you don't see this window on the left side, make it visible by clicking on 'Window > Show View > Project Explorer'.  

## Part 2: Interact with the repo from Eclipse

In this part, you will 'commit' changes to your repo from Eclipse.

First of all, make the 'Git Repositories' and the 'Git Staging' windows visible:
  1. 'Window > Show View > Other...'
  2. Expand 'Git' (click on the little arrow on the left) and choose 'Git Repositories' and 'Git Staging', then click ok
  *Tip*: A setup I personally like in Eclipse is to have Project Explorer on the left, Git Repositories/Git Staging/Outline on the right (tabbed), the main editor in the middle, and the Console/History/Javadoc/other below the main editor.

About the **Git Repositories** window:
- This window shows ... (find some text online or in Eclipse/Egit help docs) TODO

About the **Git Staging** window:
This window is where the EGit magic happens. It helpfully shows the graphical equivalent of what has to be done when interacting with Git on the command line. New or modified files show up in the 'Unstaged Changes' area (you may have to press refresh, via F5 or the icon with two little curved yellow arrows (picture needed)). To prepare a commit, files from this area need to be selected and dragged down to the 'Staged Changes' area below. Once dragged, these files are staged and ready to be committed. The message to describe the commit gets written in the 'Commit Message' area, and you commit your changes using one of the buttons at the bottom ('Commit and Push' is what I normally use; 'push' means to send your changes to the remote repository, i.e. for this example on github where others can see the changes also). 


- Add or modify a file... need some details here
- Press 'F5' while the project is selected to reload and see the new files, if you added a file via e.g. Windows File Explorer.
- Now ensure your repo is selected in 'Git Repositories', then go to the 'Git Staging' window. The changed files should appear in 'Unstaged Changes'

