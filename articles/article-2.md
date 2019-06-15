[< Back](../README.md)

# Working With Multiple Developers
When you are a developer you propably have heard/worked with Git and Github. Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency ( Git, 2019 ). Github is a software development platform that is build around Git togheter with some of its own functionalities. 

Now I got a couple of years of expierence working with Git and Github but this was always on my own. During the last project in de @cmda-minor-web I started working on a project with three other people. This provided us with some healthy challenges surrounding Git and Github. 

In this article I will explain why and how we tackeld some of these challenges and help prepare ourselfs for a real life environment.

## Git Version Control
When working with Git these are some of the most important things you will be working with: `commits` and `branches`. When working alone you can do pretty much whatever you want but when you are working in a team you have to go about it a bit differently. Other people are gonna we reading and working with the code that you have written and a clear `commit` message can make al the difference. So you have to set up some guidelines to make sure that your repositorie doen't become the wild west.

### Commit
Personally when I write a commit message I use [gitmoji](https://gitmoji.carloscuesta.me/). This adds a emoji infront of your commit so you can show what kind of commit it is. ✨ is a new feature and 📝 is for wrting new docs for example. Now because this is more of a personal preference we used some guide lines that [Maikel van Veen](https://github.com/Maikxx) setup which came pretty close to what I was already doing. [Version Control Guidelines](https://github.com/Maikxx/360-wallscope/blob/master/docs/guidelines/VERSION_CONTROL.md) sets a clear set of rules as to how your commits (and branches) should look. So something like `action(scope): description`.

When you write a commit you whe choose to start with one of the following:

* **feature:** This is for when you create a new feature.
* **styling:** This is for when you have only been working on CSS.
* **fix:** This is for when you fixed a bug.
* **refactor:** This is for when you rewrite a piece of code so that it looks better, or is written in a nicer way.
* **copy:** This is for when you change the copy of a piece of text in the application or are writing docs.

Then the `(scope)` can be whatever you are working on. For example `(create-event)`. We took some liberties with [Maikel van Veen](https://github.com/Maikxx) his guidelines but mostly followed by them. I personally also make sure some elements match with how they look when writing the commit message. For example:

* Files have their file extention next to them. For example `style.css` or `script.js`.
* HTML elements are put between `< >`. So for example when you have added a section you write `<section>`.
* New CSS styling looks like this for example `.shiney-class` or `#important-id`.

The most important thing is that your fellow developers can easly see what you have been working on.

### Branches

