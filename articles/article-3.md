[< Back](../README.md)

# Working With Multiple Developers
When you are a developer you probably have heard/worked with **Git** and **Github**. Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency (Git, 2019). Github is a software development platform that is build around Git together with some of its own functionalities. 

Now I got a couple of years of experience working with Git and Github but this was always on my own. During the last project in de [@cmda-minor-web](https://github.com/cmda-minor-web) I started working on a project with three other people. This provided us with some healthy challenges surrounding Git and Github and the way we setup our project. 

In this article I will explain why and how we tackled some of these challenges and help prepare ourselves for a real life environment.

## Git Version Control
When working with Git these are some of the most important things you will be working with: `commits` and `branches`. When working alone you can do pretty much whatever you want but when you are working in a team you have to go about it a bit differently. Other people are gonna we reading and working with the code that you have written and a clear `commit` message can make al the difference. So you have to set up some guidelines to make sure that your repository doesn't become the wild west where everybody does his own thing.

### Commit
Personally when I write a commit message I use [gitmoji](https://gitmoji.carloscuesta.me/). This adds a emoji infront of your commit so you can show what kind of commit it is. ✨ is a new feature and 📝 is for writing new docs for example. Now because this is more of a personal preference we used some guidelines that [Maikel van Veen](https://github.com/Maikxx) setup which came pretty close to what I was already doing. [Version Control Guidelines](https://github.com/Maikxx/360-wallscope/blob/master/docs/guidelines/VERSION_CONTROL.md) sets a clear set of rules as to how your commits (and branches) should look. So something like `action(scope): description`.

When you write a commit you start with one of the following `action` tags:

* **feature(scope):** This is for when you create a new feature.
* **styling(scope):** This is for when you have been working on CSS.
* **fix(scope):** This is for when you fixed a bug.
* **refactor(scope):** This is for when you rewrite a piece of code so that it looks better, or is written in a nicer way.
* **copy(scope):** This is for when you change the copy of a piece of text in the application or are writing docs.

Then comes the `(scope)`, which can be whatever you are working on. For example `(create-event)` or `(login)`. We took some liberties with [Maikel van Veen](https://github.com/Maikxx) his guidelines but mostly followed by them. 

Then comes the `description`. I personally always make sure elements match with how they look when writing the `description`. For example:

* Files have their file extension next to them. For example `style.css` or `script.js`.
* HTML elements are put between `< >`. So for example when you have added a section you write `<section>`.
* New CSS styling looks like this for example `.shiney-class` or `#important-id`.

The most important thing is that your fellow developers can easily see what you have been working on.

### Branches
When it comes to creating and working with branches there are a couple of things you want to do. First create a hierarchy for your branches. Let me explain. You don't want to be working directly on the `master` branch because this is the branch that will always be live. You want everything that is on here to be working 100%. So you create a branch called `development`. This is the branch that you and your team will be working on. But you can't all start working on the same branch, this would cause an unending amount of merge conflicts. 

Every time you start working on a new feature you create a feature branch. This branch looks something like `feature/brach-name`. This way you can work in your own separate 'environment' without having to worry too much about your fellow developers.

And last but surtenly not the least important is to activate branch protection. This allows to to set sertain rules for a branch. For example when you are finished working on a feature you can't just merge it with `development` and push it to the repository. You have to create a pull request that has the required number of approving reviews before it is allow to be merged into master.

![Branch Protection](https://i.imgur.com/ixlVbpz.png)
> Branch Protection Settings

### Modules
Having seperate branches is a good first step in avoiding unnecessary problems. But when you start to pair branches with **modules** is when you start being really producitve. Modules allow you to seperate your code into different files that get imported into the main file like `app.js`, `script.js` or `style.css`. 

When you do this you and your team are able to almost entirly eliminate merge conflicts because you are all working in seperate files so you almost never have to work in the same file at the same time. 

## Conclusion
When you first start working together on a project it can be pretty difficult and frustrating. Everybody has their owm style and way of doing this. Setting a clear set of rules/guidelines early on is the key to a prodictive work flow.