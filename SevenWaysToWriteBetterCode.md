# 7 ways to write better code
##### Source：https://www.androidauthority.com/write-better-android-code-815622/
I know bad code.

Trust me. My code is still not great, but it used to be very bad.

I don’t just mean it wasn’t technically perfect; I mean I wouldn’t even do the basic stuff. I built apps as a hobby and I flew solo. So, I had no reason to add comments. And to my mind, there was no reason not to create variables with names like monkeyWrench just because that was the first thing that popped into my head.

--------

# the hundreds of thousands of lines of code were now entirely foreign to me

Don’t need that variable anymore? No problem, just leave it there! Same goes for that disused method.

I would regularly copy and paste large amounts of code because I was too – lazy, I guess? – to create a method to handle it.

My bad behavior was never discouraged as I actually managed to build some pretty successful apps. I knew my way around the code and it was the marketing rather than the programming finesse that would ultimately drive sales. Sloppy code didn’t affect the performance because they weren’t performance intensive apps and modern phones were fast enough for it not to matter.

But then I took a break from my ‘big app’ and came back to it to create an update. Suddenly hundreds of thousands of lines of code were entirely foreign to me. Tiny changes could result in bugs that were impossible to trace.

If I ever wanted to sell the monstrosity, I’m pretty sure I’d have had a hard time. Which is a shame, because at the time that would probably have been a good exit strategy.

So yeah, you do need to write better code. Once you start to get into good habits, it can be quite rewarding. Even if you code alone, even just as a hobby, I encourage you to consider some of these points to keep everything clean and readable.

## 1. Use smart variables
This is the most boring advice you’re likely to get in an article like this, but don’t ignore it. Using smart variables is very important if you want to make your code even slightly decipherable after a time away.

But how should you go about naming those variables?

The obvious tip is to name the variables based on what they do. So, maybe don’t call the user name string MonkeyWrench –  call it UserName.

Where possible, try to make your code read in a manner similar to English. This is something that becomes especially apparent when using Booleans (true or false statements).

```php
If (volumeOff) {
`

If you’re really anal about it (or maybe the word is ‘professional’, these are foreign concepts to me), then you may even create some kind of key or reference for your variables. What I like to do instead, is to simply make sure that my variables follow their own consistent, logical nomenclature.

So, when I made a multiscreen multitasking app, I dealt with many similar variables describing aspects of different ‘mini’ apps that could be moved around the screen. I always named these in the same way, such that paintTaskbarLength did the same thing as notepadTaskbarLength. This then meant that I didn’t have to look around for the name of that variable. If I had called one notepadTaskbarWidth instead, then it would have led to confusion.

Eventually, if your code is large enough, the variables can become almost a kind of meta-code all of their own! That’s pretty cool.

Of course, you should also be equally logical when choosing names for methods and classes.
