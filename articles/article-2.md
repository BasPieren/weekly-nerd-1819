[< Back](../README.md)

# How To Deal With Complexity
We have all been there, you have this cool and unique idea for a project that sounds totally wicked inside your head and is unlike anything you have ever done. You start programming and than it hits you: you have absolutly no idea how or where to start. That was my experience during the real-time-web-1819 course. 

I had this super cool idea for a code editor in your browser where people could create a GitHub repository and learn to write HTML together using a chatbox. Setting up the editor and chatbox all went relatively well but when I had to start working with the [GitHub API](https://developer.github.com/v3/) I hit a wall. This was more complex than anything I had ever done.

## Take A Step Back
So I had a problem with the GitHub API. My experience with previous API's was always just basically just getting back data but know I had to use it to create something, a repository, and having to use `OAuth` on top of that. It was pretty overwhelming. Documentation was very vague and I could't find my problem online. So let me explain what I was trying to do:

1. A user needs to login to my web app using GitHub using `OAuth`.
2. The user needs to be able to create a repository within my web app.
3. When the repository is created the user gets redirected to a dashboard that shows the amount of issues, watchers, stars and forks.
4. Here they can chat with some one else that should be able to join their 'room' using [socket.io](https://socket.io/).

Now see what I did there? I made a list. I wrote that what needed to happen in broad lines. When me and three other students had our first weekly mingle at [Elastique](https://www.elastique.nl/) we were asked about our marshmallow. Now let me explain. They had this workshop where they had to build a tower using only spaghetti and a marshmallow. Natuarlly people put the marshmallow on top but this would cause the whole tower to collapse. The marshmallow is the part of a project that you can't wait with until the end.

I told them about my GitHub API problem and got some very usfull feedback from Bob, the Full-Stack developer: Draw and write down what you want your web app to do. Divide it in very small parts so you only have to think about that part before you continue.

Now this wasn't completely new information to me. At CMD the teachers always try to push you to start with drawing out your idea/concept before you strat working behind your laptop but I will be honset and say I have never been the best practitioner of that. But now I tried giving it my best shot. And lord behold, it worked. 

## Write It Down
I started writing and drawing down what I wanted to do and divided my the steps to be taken in even smaller steps. This allowed me to be even more precise with my Google searches and discover that there was already a GitHub API that acts as a wrapper around the API: [octokit/rest.js
](https://octokit.github.io/rest.js/). This wrapper had some pre-written functions that did exactly what I wanted to. Using this wrapper also allowed me to better understand the API itself and how it worked togethter with `OAuth`. 

## Conclusion
Whenever you start working on a new feature you should always start by writing down what that feature needs to do and how it should work. This can and will save you a lot of time in the long run and allows you to have a clear vision of what needs to be done.