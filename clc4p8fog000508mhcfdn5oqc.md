# What is Emmet?

Emmet is a plugin for code editors that gives fast and easy-to-use snippets for HTML and other code formats. It allows developers to expand abbreviations into full HTML, or other code blocks by using a few words.

As an example, if you type div followed by the Tab key in an HTML file, Emmet will automatically expand the abbreviation into a full `<div>` element. Similarly, if you type `ul>li\*3` followed by the Tab key, Emmet will expand the abbreviation into an unordered list with three list items:

```xml
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

Or more complexly, writing `section.container>div.row>(div.col-md-8\*2>p)+footer` and pressing the Tab will give

```xml
<section class="container">
    <div class="row">     
        <div class="col-md-8">       
            <p></p>     
        </div>         
        <div class="col-md-8">       
            <p></p>         
        </div>   
    </div>   
    <footer></footer> 
</section> 
```

The `\*2` syntax tells Emmet to repeat the preceding element twice, and the `>` and `+` symbols indicate that the following element is a child or sibling of the preceding element, respectively. They were meant to be simple and basic, but it can get complicated, so if it takes more time to write the Emmet syntax than the expanded syntax, one has already erred.

Emmet was originally built by Sergey Chikuyonok, a Russian software developer in 2007 as a plugin for the text editor called Zen Coding.

But in 2011, Emmet was released as a plugin and became available for a wide range of text editors. It has since become a popular tool for developers and is supported by many popular text editors, including Sublime Text, Visual Studio Code, and Atom. Emmet is currently maintained by a team of developers, with Sergey Chikuyonok as the lead. The project is open source and is available on [GitHub.](https://github.com/emmetio/emmet)