## Technical writing practice
---
### Purpose

This article will describe the practical steps of how to format a resume by markup language and then host it as a static website page. I will use the most common tools to demonstrate this process. The tools are Markdown Language, Git, GitHub Pages, and Jekyll. When I describe the practical steps, I will also explain how they can relate to the general principles of current technical writing talked in Andrew Etter’s book Modern Technical Writing. By following this instructions, you may gain some ideas about how to make your documentation publicly accessible and updated in time. These are two main metrics for modern technical writing.

### Prerequisites
Before we try to host a resume on GitHub Page, we should have a resume formatted by markup language. [Here is an example](https://github.com/ZsCitrus/zscitrus.github.io/blob/main/index.md). There are several most common markup languages, like HTML, XML, Markdown, etc,. You may have heard some of them. As advised by Etter’s book, here we will use Markdown for its simplicity. Markdown is a lightweight and cross-platform markup language. And its basic syntax is relatively simple. However, since my focus is to describe how to host a markdown file (like the example resume) on GitHub Pages, I will not go into details about Markdown syntax. Under the More Resources section, you will find some tutorial information about Markdown.

### Instructions

[Here is what the final output looks like](https://zscitrus.github.io/).

#### Notes before the how-to steps

As talked in Andrew Etter’s book Modern Technical Writing, technical writer should dive into the relevant software or products before writing. And this is a nontrivial and time consuming process. It is! Before I can sit down and write this instruction, I have spent two working days to be familiar with only the very basics. Thus I am not able to talk about the technical details of other tools I used either. If you want to know more, the links in More Resources section is a good start. 

My operating system is Windows 10 Pro 64bit. All my description is based on this running environment. If you have a different running environment with me, I assume you know how to adjust accordingly since you are in computer science major.

#### Steps to host a resume on GitHub Pages

1. Register a [GitHub](https://github.com) account

I use GitHub as suggested by Etter’s book. GitHub is the most popular codes host website. It is also an application for distributed version control software development. Codes hosted on GitHub are easy to be publicly accessible and editable. So it helps others contribute to your projects. To register, go to GitHub website to sign up an account, nothing more than most common procedures.

2. Create a GitHub repository

After registration and sign-in, follow the instructions on the web page to create a new repository. Everything is straight forward. For our GitHub Pages publishing purpose, make sure you have a repository name as this form: username.github.io. The username is your username when registering the account. If there is any upper case letter, change it to lower case. 

3. Give the resume file a right name

In your repository, find the “Add file” button and add a file named index.md. GitHub will use this file as GitHub Pages publish source as default. If there is no such index.md file, readme.md will be used. If there are neither, you will get a 404 not found page in the end. After you have this index.md file, you can write in what you want as long as the content is in markdown format. For the purpose of this article, the content is the resume. 

4. Download Git

You will need [Git](https://git-scm.com/) to interact with GitHub. Downloading and installation is straightforward. If you already had some knowledge software engineering, you may be familiar with Git. If not, it’s fine since the focus here is not Git.  

5. Download Ruby to use Jekyll

For the static site generator, I use Jekyll here because it is recommended in Etter’s book and is built in GitHub. Follow [this instruction](https://jekyllrb.com/docs/installation/)to download and install Jekyll and related tools. Note that different operating system will have different procedures. This is also the reason why I omit details here. It’s tedious and unnecessary. The official sites have very detailed procedures. 

6. Clone a local GitHub repository on your computer

GitHub is a codes host website, not a IDE. So you need to clone your repository to your local computer for any development related operations. Follow the steps below to finish this task.
- open a command prompt
- run command “git --version” to make sure you have Git installed correctly
- run command “git clone URL” to clone the repository
- replace the URL above with the real URL of your repository
- this URL can be found by click the green “code” button at top of your repository web page

7. Use Jekyll to build a local static site

- your local repository will have a same folder name as your hosted repository name
- run command “cd repository folder name” to make that folder working directory
- run “jekyll new PATH --skip-bundle” to build a local static site
- replace the PATH with your local path, which is a sub folder under your local repository folder
- run “cd folder name” to make the new sub folder created just now working directory
- run “notepad Gemfile” to open the Gemfile
- add "#" to the beginning of the line that starts with gem "jekyll" to comment out this line
- edit the line starting with # gem "github-pages" as [gem "github-pages", "~>221", group: :jekyll_plugins], 221 is the latest GitHub gem version
- save and close the Gemfile
- run command “bundle install” to finish this task
- Be careful the “--skip-bundle” argument in the third step, it is fatal. Myself wasted tremendous time for error fixing by omitting this argument. 

8. Push the update back to GitHub

You need to push the update back to GitHub to let it uses the generated site.
- run command “cd  ..” to go back to the repository folder
- run command “git add  .” and command “git commit -m “commit message”” to update all local changes
- run command “git push origin main” to finish this task
- If Git ask you for identity authentication during the process, follow its instruction. Then repeat the second to fourth steps, make sure you can see your new jekyll generated folder in your online repository.

9. Configure your GitHub settings

- find the “setting” icon at the top of your online repository web page
- click it, then find the “page” menu at the right
- click it, under “Source” setting choose main branch and root folder, click save
- you can choose site theme if you like

10. See your resume hosted on GitHub Pages

- wait for a moment, then refresh the web page
- now you can see you index.md file published as a static site, the URL is at top of the web page

#### More Resources:

1. [Here is Etter’s Book](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
2. [A useful and friendly Markdown Tutorial](https://www.markdownguide.org/basic-syntax/)
- If you do not want to install a Markdown editor, here is a [online editor](https://dillinger.io/).
- You can also directly edit a markdown file in GitHub.
3. [GitHub’s official instructions for GitHub Pages](https://docs.github.com/en/pages)
4. [Jekyll’s website](https://jekyllrb.com/)

### Acknowledgments

Thanks for my classmates to help me realize technical errors
- Adam Donen
- Joseph Godard
- Jishan Arora
- Tanisha Turner

### Frequent Asked Questions

1. Why is Markdown better than a word processor?

Markdown file is cross-platform. Once it is written, it can be used by varieties of applications. However, mainstream word processors are not cross-platform, the files can only be read in particular applications. This is because Markdown is lightweight. It can be seen as plain text plus some relatively simple format syntax.

2. Why is my resume not showing up?

Make sure you have right repository name and right publish source file name. As described above, the repository name must be in this form “yourusername.github.io” (all letters in lower case) and the the publish source file name must be index.md no matter what the contents are. I made mistakes about these two aspects during the learning process, thus wasting tremendous time to look for errors and fix them. 
