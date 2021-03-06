## Facade Pattern

- Our next pattern is facade, which, as I said when I was talking about bridge, people often confused with a bridge.
-  So let's talk about facade.
-  The notion of a facade is that it's a false front.
-  If you think about an old Western town, right, you might have a building where you're walking down the street and it's a bank.
-  And it's a big impressive building with complicated roof stuff and marble columns and lots of doors and stuff.
-  And you go around to the back of this building, and if we look at a side view, what you'd see is a very thin layer.
-  And underneath it would be a little shack that was the actual body of the bank.
-  So that's the notion of a facade is that when you look back behind it, what's there is not what you would think would be there by looking at the front.
-  Now, a traditional facade, like the facade on a building, is actually doing the opposite of what a facade does in a design pattern world.
-  Purpose of a facade is to simplify.
-  So the idea of a facade is that it is a class or a set of classes that you write in order to make it easier to use the things that are on the other side of the facade.
-  So there's a great example of that inside the Life game.
-  Let's take a look at it.
-  So here's our menu site class.
-  We looked at the menu site a while back.
-  The basic idea of a menu site is a menu site provides you with a convenient easy way to put menus together.
-  If we look at Life, for example, let's go to the clock class in Life because clock creates its own menu.
-  Here is the clock getting itself initialized.
-  If we scroll down here a little bit, here is the clock putting its menu together.
-  So the way that it adds things to a menu is it says to the menu site, now the menu site is a singleton.
-  Remember, it was our example of everything is static singleton.
-  So there's only one menu site in the program.
-  And it says to the menu site, I need you to add a line to some menu.
-  And then I want you to add to the go top level menu.
-  And I want you to add this line item.
-  So that's pretty straightforward.
-  When somebody clicks on the menu, you will call whatever callback is specified by this modifier.
-  We'll look at callbacks a little bit in a moment.
-  Now, again, this is a one of a kind singleton, so the receiver here is a class, because everything is static inside this class.
-  So this is pretty straightforward.
-  The other thing that this does, which is actually pretty handy, is this first argument here is just an arbitrary reference.
-  I've used this in this case.
-  But there is a method in the menu site that says remove from the menuing system all menuing items that are tagged with this arbitrary reference.
-  So as I was mentioning way back at the beginning of the class, it is very object oriented, if you will, to think about a UI as an aggregation of UIs that are put together by the classes that comprise the program.
-  And it is the case that a class might activate and want one UI and deactivate and want a different UI.
-  So what this mechanism gives us is a very simple way to say to the menu site, remove everything that I added.
-  And of course, if you then wanted to replace everything that you added with something else, you could do that pretty easily.
-  Now, from my point of view, this is the way the menuing system ought to work in Java.
-  In practice, though, it's not that easy.
-  So if we go back over to my menu site class, I'm just going to start scrolling through it here.
-  But the main thing to notice, as I scroll through the menu site class-- well, this is just comment, so it's not that interesting.
-  But as we go down into the code itself, the main thing that to notice as I scroll through this menu site is that it is huge.
-  There is a vast amount of work that's required to implement that very simple interface into the menuing system.
-  In fact, if we scroll all the way down to the bottom, I have 1,200 lines of code that I need to implement a system that is as easy to use as the four or five lines of code that we were just looking at.
-  So we can argue all day about whether the guys that put this together should have done it the easy way to begin with.
-  From my point of view, the menuing system in the Java UI system, this is Swing, is hideously bad.
-  It is still the case that we can solve that problem by putting a wrapper around it.
-  So when I do menuing, I don't use the Java underlying menuing system.
-  I use the menu site.
-  So what is the difference between that and a bridge? The quick answer is that the purpose of a bridge is to isolate two subsystems from each other.
-  My menu site class is not actually doing any isolation.
-  In other words, the menu site is implementing the 10% of the functionality that I use 90% of the time.
-  Or to put it another way, it is not a complete menuing system in and of itself.
-  There are things that the underlying menu system can do that my menu site system cannot.
-  For example, the underlying menu system could put images onto the line items in a menu.
-  I can't do that inside the menu site.
-  So the menu site does simplify, but it also provides a mechanism to walk around to the back of the facade.
-  In other words, the menu site is not isolating me from the menuing system.
-  It's just providing a simplified interface into the menuing system.
-  If I need to do something complicated, that that simplified interface can't do, I can always make an end run around the menu site and go directly to the menu system and manipulate the underlying menu system.
-  Now, from a design point of view, the tough part there is to design the facade in such a way that you can make an end run around it when you need to.
-  In other words, it shouldn't be extremely difficult to get to the other side of the facade.
-  It should be relatively easy to get to the other side of the facade if you need to actually get any work done.
-  And the menu site has a few classes.
-  We won't bother to look at them.
-  But they just return the menuing classes that underlie the facade classes.
-  So again, you look at structure and bridge and facades seem very similar, which is why people get them confused.
-  Is that in both cases, it is a layer that stands between two other things.
-  But in the case of the bridge, the purpose of that layer is to completely isolate yourself from the other side so that you don't even know what's there.
-  So you could even make changes at runtime without knowing that you've made the change.
-  You can't do anything like that with a facade.
-  The purpose of a facade is to simplify access to an overly complex substance.
-  Is the point, in other words, is to make it easier to program, not to isolate subsystems from each other.
-  So that's the facade class.
-  In the next segment, we're going to move on.
-  And we're going to look at composite.