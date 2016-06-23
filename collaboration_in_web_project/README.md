## Collaborate on a web development project

For the final master exercise in my Minor Everything Web I developed a web application from scratch. Not by myself, but in a team with 2 other developers/designers. The thing I want to talk about is, you can't start a project like this on three different computers and just go. You have to think this over and make important choices. If you don't choose your tools proparly, everything will be harder to combine at a later stadium. I am writing this article because my opinion on collaborating in a project like this is totally changed. 

### The tools 

After we decided to work in a team, rather than working individually, we sat down and talked about how we could make this work. We decided to work with [GIT](https://github.com/) and [Trello](https://trello.com/), so we could create a structured and organized work environment. Trello as an organization board, where everyone has his, her or their personal tasks. GIT as a online repository for the application and all it's features.

### Working with GIT

It's the first time we've worked with GIT in this minor. In the first few courses we had to share our code on Github, so commiting, pushing and writing a readme wasn't totally new for us. Before the minor I only used Github as a source for code snippets. And besides that I almost never worked on a project like this with more developers. 

This time I wasn't working alone on a project. We were going to build an application with the three of us. Luckely is GIT a very powerfull tool if you want to write code with others. So we started looking how we could use GIT for this project. First of all we created a repository (which wasn't new offcourse), that is the - let's call it the online space reserved for your files -. Each of us cloned the repository to it's local computer by opening their terminal, going to the local directory and type the following command:

``` 
$ git clone https://github.com/path/path
```

After doing this, everyone had the same repository now locally on his or her computer. So we started setting up all necessary files and there we go. 

Now one of the great features of GIT comes in place. The repository automatically creates a branch called "master". Let's say that's the place were all files work properly, without errors or any weird code we don't want in our final application. 

We divided tasks and I started working on geolocation and the Google Maps API, so I created a second branch called "maps-location". In my terminal I check out of the master branch and switch to the new "maps-location" branch. 

```
$ git checkout maps-location
```

By entering this command, GIT automatically creates a new branch in the repository. This is now a save place where I can do everything without messing up the code in the "master" branch. My collegues create their branches and we develop each our own piece of code. When someone is done with their part, has double checked everything you can merge the code it to the "master" branch and done. 

First commit your own code with the following commands:

```
$ git commit -a -m "Bugs fixed, feature is now working" // The actual commit
$ git push // Pushing the code to the GIT repository
```

After this commit is pushed to your branch, you will need to checkout to the master branch to merge this branch into the master's.

```
$ git checkout master // You are now working checked in the master branch
$ git merge maps-location // By this command you will merge maps-location into master
```

You now updated the master branch with a fully working piece of code. Amazing how this works, everyone works from their feature branch while the master branch keeps getting updated with new working code. But watch out! When changing big pieces of code while the other one is still working with that old piece of code you are completely changing, it will likely cause a problem called: "merge conflicts". This means that there are some pieces of the merged code is in conflict with the excisting code in the master branch. When this happens, it looks like this:

```
the number of planets are
<<<<<<< HEAD
nine
=======
eight
>>>>>>> master
```

Which means that in the master file, the number of planets was eight and in your current working branch the number of planets is nine. Don't worry, the conflicts can get way more complex, this is easily fixed. Just remove the part you don't need and commit the new changes. Like this:

```
$ git commit -m "Merged master fixed conflict."
```

Apart from the very annoying merge conflicts, working together in branches with GIT was a big eye opener. Every piece of code is visible apart from the application, every change of code is visible and even reversible. When you are building a local application this is so hard that is almost impossible. Next to that, you have a really good overview on what everyone is working and how the app is evolving. 


### Working with Trello

It was also not the first time I worked with Trello. Besided my study Comminucation & Multimedia design I develop and design websites for different clients. Most of the time I work alone and don't need a organization tool. But sometimes I work for companies like [Aimforthemoon](https://www.aimforthemoon.com) or [GR8THNGS](http://gr8things.nl/), and to look at my process they wanted me to create a Trello board. It never worked for me, I could even say that I hated working in Trello. I know what I need to do, I know where I am in the process of the website. So why moving cards, why wasting time on looking through the board where that single card is. 

But when working in a team like this, I had another eye opener. What an amazing tool is Trello. Not only to get a clear view the total project, what's already done, what bugs you still need to fix but totally forgot, where everyone is working on and what to do if you have time left. The workflow is clear, nobody thinks, hey what is he doing all day, you just look at the "Week 4 Doing", search for the card with my label on it and there you go. 

Because this is a school project, we need to deliver a readme file in which we explain everything we did during the project. Even there is Trello very powerfull, every week has an own board with everything thats done in that week. So you just sum up every task with your name label and there you go.

Example of how a Trello board looks like when you finished a project like this.

![N-Festival Trello Board](http://www.tijsluitse.com/trello_board.png)

## Conclusion

The things I have learned from working with these two amazing tools is that the really create a structured and clear working environment. Especially when you work in a group of developers, but also when you work alone. Every change can be reversed in GIT and you never forget the little bugs you've seen at friday afternoon before the weekend. 



