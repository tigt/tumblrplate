##Figure out swappable search engines, as Tumblr's built-in search is wimpy

````
<meta name="select:Blog Search Engine" content="default-tag-search" title="Default Tumblr tag search">
<meta name="select:Blog Search Engine" content="google-search" title="Google">
<meta name="select:Blog Search Engine" content="no-search" title="Hide Search Bar">

    <form class="tumblrsearch" action="/search">
        <input type="search" name="q" placeholder="Search for a tag" value="{SearchQuery}" required />
        <input type="submit" value="Search" />
    </form>
    
    <form class="googlesearch" action="http://www.google.com/search">
        <input type="hidden" name="as_sitesearch" value="{BlogURL}" />
        <input type="search" name="q" placeholder="Search with Google" value="" required />
        <input type="submit" value="Search" />
    </form>
    </nav>
````

##Pinned sites/tiles integration
```
<meta name="msapplication-tooltip" content="{MetaDescription">              
<meta name="msapplication-starturl" content="{BlogURL}">
<meta name="msapplication-TileImage" content="{PortraitURL-128}">
<meta name="msapplication-square70x70logo" content="{PortraitURL-96}">
<meta name="msapplication-square150x150logo" content="{PortraitURL-128}">
<meta name="msapplication-navbutton-color" content="{AccentColor}">
<meta name="msapplication-TileColor" content="{AccentColor}">
{block:AskEnabled}
<meta name="msapplication-task" content="name={AskLabel};action-uri={BlogURL}/ask">
{/block:AskEnabled}
{block:SubmissionsEnabled}
<meta name="msapplication-task" content="name={SubmitLabel};action-uri={BlogURL}/submit">
{/block:SubmissionsEnabled}
```

##Sharing options

sms: protocol for text messages?
list a bunch of URL queries if the designers wish to include various sites
