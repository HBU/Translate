# 7 ways to write better code
##### Source：https://www.androidauthority.com/write-better-android-code-815622/
I know bad code.

Trust me. My code is still not great, but it used to be very bad.

I don’t just mean it wasn’t technically perfect; I mean I wouldn’t even do the basic stuff. I built apps as a hobby and I flew solo. So, I had no reason to add comments. And to my mind, there was no reason not to create variables with names like monkeyWrench just because that was the first thing that popped into my head.

--------

## the hundreds of thousands of lines of code were now entirely foreign to me

Don’t need that variable anymore? No problem, just leave it there! Same goes for that disused method.

I would regularly copy and paste large amounts of code because I was too – lazy, I guess? – to create a method to handle it.

My bad behavior was never discouraged as I actually managed to build some pretty successful apps. I knew my way around the code and it was the marketing rather than the programming finesse that would ultimately drive sales. Sloppy code didn’t affect the performance because they weren’t performance intensive apps and modern phones were fast enough for it not to matter.

But then I took a break from my ‘big app’ and came back to it to create an update. Suddenly hundreds of thousands of lines of code were entirely foreign to me. Tiny changes could result in bugs that were impossible to trace.

If I ever wanted to sell the monstrosity, I’m pretty sure I’d have had a hard time. Which is a shame, because at the time that would probably have been a good exit strategy.

So yeah, you do need to write better code. Once you start to get into good habits, it can be quite rewarding. Even if you code alone, even just as a hobby, I encourage you to consider some of these points to keep everything clean and readable.

# 1. Use smart variables
This is the most boring advice you’re likely to get in an article like this, but don’t ignore it. Using smart variables is very important if you want to make your code even slightly decipherable after a time away.

But how should you go about naming those variables?

The obvious tip is to name the variables based on what they do. So, maybe don’t call the user name string MonkeyWrench –  call it UserName.

Where possible, try to make your code read in a manner similar to English. This is something that becomes especially apparent when using Booleans (true or false statements).

```php
If (volumeOff) {
```

If you’re really anal about it (or maybe the word is ‘professional’, these are foreign concepts to me), then you may even create some kind of key or reference for your variables. What I like to do instead, is to simply make sure that my variables follow their own consistent, logical nomenclature.

So, when I made a multiscreen multitasking app, I dealt with many similar variables describing aspects of different ‘mini’ apps that could be moved around the screen. I always named these in the same way, such that paintTaskbarLength did the same thing as notepadTaskbarLength. This then meant that I didn’t have to look around for the name of that variable. If I had called one notepadTaskbarWidth instead, then it would have led to confusion.

Eventually, if your code is large enough, the variables can become almost a kind of meta-code all of their own! That’s pretty cool.

Of course, you should also be equally logical when choosing names for methods and classes.

# 2 Avoid magic numbers
In some ways, magic numbers are more of a problem than randomly named variables. These are numbers that you assign special meaning to that are completely arbitrary.

For example, I created an ‘overshoot’ animation from scratch so that a view would slide in from the edge of the screen, overshoot its end destination, and then appear to ‘ping’ back into the correct place.

## We know that ‘0’ is left and ‘1’ is right. But does everyone else?

To do this, I allowed the image to overshoot its mark by 30 pixels before pinging back. The question you should ask at this point is ‘why 30’?

A more common example of this might be the old ‘Facing’ variable in a basic 2D game. The player can face left or right and in many cases, we will assign one of these directions to ‘0’ and one of these directions to ‘1’. We know that ‘0’ is left and ‘1’ is right. But does everyone else? Will we still know that in one month, or one year?

What should you do instead? Well, you could create constants. For instance:

```java
private static final int left = 0;
private static final int right = 1;
```
Now you can say if (Facing = left) and that is hugely more readable.

Likewise, instead of pinging back at ‘30’ we could ping back at overshootAmount or something similar. This also has the added bonus of allowing us to easily tweak how exaggerated our animations are. We could even make this an option available for the user to change.

# 3. Methods and classes for everything
Create methods and classes wherever possible to break up your code. If you then give those methods logical, readable names, then your code will end up short and easy to follow with the option to dig into the nuts and bolts of each step only as necessary: if this, get this number, then draw picture on screen, then save this file…

If you follow this line of logic, larger methods will be broken down into multiple smaller methods. This not only keeps everything nicely organized on the screen allowing you to handle it in digestible chunks; it also makes them more portable for using in future projects. Just grab a method and drop it into your next program and you’ve saved yourself a ton of time.

# 4. Comment and comment well
Not only should you comment your code but you should also keep in mind a tip someone taught me: don’t just write what a section of code does, write why it is important. This helps to contextualize the code and presents the bigger picture of how this method or line fits into the grand scheme of things.

You can also use comments for a variety of other purposes. One trick I like is to use a kind of ‘keyword’ for code that needs looking at later, or code that I’m about to jump back to. If I need to quickly jump into another part of the code for reference, then using this keyword I can then perform a search to get back to where I just was. Likewise, if I earmark lines that need polish in this way, I can quickly sift through the page to find things that need brushing up.

## avoid the temptation to simply comment out the code you no longer want

One last pointer: avoid the temptation to simply comment out the code you no longer want. This can be tempting as it allows you to save said code for later in case you need it, but it can hurt readability and make a project harder to navigate. If you’re anxious to delete old code, keep it in a notepad document or something instead.
```java
//This is also a good place to write jokes for yourself, which will amuse/irritate you when you come back to 
//look over your code.
```
# 5. Don’t reinvent the wheel
The great thing about programming is that a lot of it is done for you. There are so many libraries, classes and example snippets of code that you’re free to use, that with some smart Googling you can pretty much build your app out of ready-made parts.

This saves a lot of time when building something complex. What’s more, is that if you’re liberating a piece of open source code from Github, chances are it has been worked on by multiple people and fine tuned to perfection. In other words, it’s probably better than the code you’d make if you quickly tried to piece something together yourself. You might even learn some good habits by looking at it.

Of course, it’s very important that you always give credit where it’s due and only use code with a Creative Commons license.

#6. Make sure you understand everything!
The danger of creating a Frankenstein app this way is that you can end up with code that you don’t actually understand. This is dangerous. It not only means you can end up making mistakes, but also that you likely won’t be utilizing the code you’ve written to the fullest extent possible. I’ve definitely been guilty of this one in the past and upon actually reading what those additional classes did, I found I could streamline whole projects significantly.

Make sure you can actually understand the code that you’re using. That means being able to follow the line of logic from start to end and explain what everything does to someone if necessary. Think in terms of the ‘Feinman technique’ of being able to teach in order to fully understand.

# 7. Don’t go mad over it
You know what? While this is all good advice, you shouldn’t go too mad over writing the most beautiful code possible that does incredible things with just three lines. While I was definitely too relaxed in my approach to programming back in my younger years, I’ve also encountered people who go too far the other way. These are the people who will spend so long working on the way the code looks, that they actually forget to build the app.

I have a theory that this can sometimes be a convenient form of procrastination for those that are afraid to unleash their idea out into the wild and see if it’s a success. That’s why I prefer the ‘fail fast’ approach of rapidly developing new ideas and testing the market for them with an MVP.

That means my code needs to be clean so that I can build on the idea in future if I need to. But it doesn’t need to be a masterpiece! There is definitely a law of ‘diminishing returns’ at play here eventually.

Keep in mind as well that there are points at which making your code more concise can actually become a destructive thing. There is actually a difference between code that is readable and efficient and code that is just clever for the sake of being clever. No one likes a show off.

## There is a difference between code that is readable and efficient and code that is just clever for the sake of being clever

# Conclusions
With that, you hopefully are on track to writing cleaner and more understandable code. You shouldn’t be afraid of having your own style and potentially developing some of your own quirks. Just make sure they are quirks the rest of your team can work with if you’re working on a large collaborative project!
