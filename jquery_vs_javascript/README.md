## jQuery !=== Javascript

Before I started this minor, I knew just enough Javascript to create some nice HTML websites. Most of the time for animations, click events or other front-end related stuff. But I did not really understand the link or relationship between native Javascript and let's say jQuery. I thought this was something similair. So I didn't had any opinion what so ever on writing code. This paper is about how my vision changed in a proffesional way about writing Javascript. I personally think that this minor was a huge step forward.

When you look at websites I've developed over the last years, I can tell you, the Javascript files are a total mess. Bits of native Javascript mixed with jQuery, tons of big libraries that do only small things. But in my opinion, this was not a bad practice. I didn't knew better. For instance, performance, page load, HTTP requests, and code structure was never something I thought about. I needed to work hard and get the website working as soon as possible. Money, money, money. 

There is no doubt that jQuery is a very good library to make writing Javascript easier and faster. It is very easy to use and has tons of great functions. The support is enormous because of a strong open source community with great documentation and tutorials. If you search online you will find that "it even support AJAX". (Don't worry, you can write AJAX calls in native Javascript aswell).

After listening to professionals during the weekly nerds (every week we invite a different proffesional to give a lecture), I really began to think differently. How cool is it, when you can build websites or even whole web applications without needing any jQuery or other libraries? But how?

### The black box

I think the main problem for people like me (before this minor) is when you don't have enough knowledge of Javascript, you just don't know that some things are able in native JS. You include the MDN script tag in the head of your HTML file to only make a very small difference in code.

jQuery (simple way):

```
$('header ul li.active').addClass('foo');
```

Javascript (native way):

```
document.querySelector('header ul li.active').classList.add('foo);
```

In native JS there are a bit more characters neccessary, but you don't need a whole library to find this active list item. I think that when looking at the jQuery code you see above, when you use this line of code, you don't know the real thing that's happening. With the ```$``` selector, you can select everything. In native JS you need to have an understanding of what you are selecting. What you type is what you get. 

While I learned more and more about Javascript I started to see why things weren't working before. Let's say you want to add a class to a bunch of items with the same class. Before this minor I tried this a dozen times (with no success).

```
var allItems = document.querySelectorAll('.highLight');

allItems.classList.add('padding-xl');
```

But this code will return an error saying ```Cannot read property 'add' of undefined```. What means that it is not possible to add a class to allItems. So oke this is not working, I add jQuery to the head of my index.html and write the following, very easy piece of code. 

```
$('.highLight).addClass('padding-xl');
```

Sooo and I'm done. I don't know why this works fine in contrast to my native JS code, but it does the trick. And again, you don't have any clue what your code represents. Now I finally know why this code isn't working. What you get back from a ```querySelectorAll``` isn't an array but a [Nodelist](https://developer.mozilla.org/nl/docs/Web/API/NodeList). A Nodelist object is a collection of HTML nodes. So when you are selecting this object, you need to create a ```for``` or a ```forEach``` loop to assign classes to the nodes. The correct use of a ```querySelectorAll``` looks like this:

Simple for loop:

```
var allItems = document.querySelectorAll('.highLight');

for (i = 0; i < allItems.length; ++i) {
 	allItems[i].classList.add('padding-xl'); 
}
```

ForEach loop:

```
allItems.forEach(function(item){
	item.classList.add('padding-xl');
}
```

With this code you added the class to each seperate HTML node. Now you understand what the code really does and didn't have to use a whole library to use only one small function from it. By these small examples I want to show what a black box jQuery can be and most of all, that if you keep going for the short and easy way you are never master Javascript. 

## Conclusion

I think that the things I have learned about Javascript are just the beginning of a greater journey. The feeling when writing code without libraries is fantastic, it feels like you are learning more and more. When you use libraries for everything the problem may be solved but you don't know exactly what happend. That's not only in this profession a big deal but in all things you want to learn. When you want to become a master in deejaying, don't start on the computer but with vinyl, know what a track feels like, how it behaves. I think thats a very important lesson in many jobs. Start at the bottom and don't take shortcuts just to make it easier for yourself. It's nice to say that you can write Javascript, but that's a lie when you use jQuery for every small problem you can't solve. I think my opinion is clear. Start writing native Javascript! 









