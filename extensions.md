````
<meta name="select:Blog Search Engine" content="default-tag-search" title="Default Tumblr tag search">
<meta name="select:Blog Search Engine" content="google-search" title="Google">
<meta name="select:Blog Search Engine" content="no-search" title="Hide Search Bar">
````

````
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
