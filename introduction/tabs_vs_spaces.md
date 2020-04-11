# Tabs vs Spaces
When writing source code, developers indent different clauses of their program to form a hierarchy in order to make it more readable. A holy war has been fought for eons over the which character to use when indenting code: tabs or spaces? **A common misconception is that you should use spaces to indent. This is a false statement.** Here is a diagram below visually showing the differences between tabs and spaces.

[![Spaces vs Tabs](https://i.ytimg.com/vi/SsoOG6ZeyUI/maxresdefault.jpg)](https://www.youtube.com/watch?v=SsoOG6ZeyUI)


Each dot represents a space, while each arrow represents a tab.
![Tab vs Spaces Diagram](introduction/media/tabs_vs_spaces.png)
As you can see, **spaces are a waste of disk space** as it takes 2-4 space characters to indent, while it only takes 1 tab character to indent.

## An objective analysis on both sides of the debate
In order to remain unbiased on why **tabs are better than spaces in every single way for indentation**, we will objectively list all of the advantages and disadvantages for using each.

### Why should I use tabs?
- The tab character was specifically developed for indentation.
- You are able to configure how many characters a tab takes up, depending on your preference (typically 2 or 4 characters).
- All the cool kids are doing it.

### Why should I use spaces?

### Why do some people think it's okay to sin?
- Some people prefer to indent with spaces so "the code looks the same no matter your computer or IDE".
  - **This is false.** When using tabs, developers configure how many characters a tab should take up. You cannot do this with spaces. Developers should be able to change the indentation width of their code to whatever they like, similar to how they can change the font size of the code to whatever they like.
- Some people prefer to indent with spaces so "their code can stay aligned".
  - **This is false.** If you need to use tabs to align code, then you are doing it wrong. **Use spaces for alignment, and tabs for indenting lines.**

## **Please make sure you configure your IDE to use tabs and not spaces!**
Even though you are pressing the 'tab' key in order to indent your code, you might not necessarily be using tabs over spaces. Most IDE's allow you to insert x amount of spaces when you press the tab key. In order to make sure you are inserting a tab character instead of 2 or 4 spaces, look in the settings, config, or preferences of your favorite IDE.

## Disclaimer
In all seriousness, the MICDS Programming Club will use tabs as standard, but **it is more important to stay consistent throughout a whole project.** If you mix tabs and spaces, the code could be all scrambled up, and be unreadable. 

## Other Resources
- [https://en.wikipedia.org/wiki/Religious_war](https://en.wikipedia.org/wiki/Religious_war)
