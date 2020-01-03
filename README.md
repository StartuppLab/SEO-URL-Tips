# SEO-URL-Tips

Here is some list of URL rules which we use for most of our application to make their URLs more SEO friendly. Let's have a look at them.

The first mistake which is very common is a page has a few URL addresses. For example: the main page of you site is available by next addresses: www.startupplab.com, startupplab.com, www.startupplab.com/, www.StartuppLab.com, www.startupplab.com/home, www.startupplab.com/home/index and etc. SEO engines think that these pages are the different pages, because of their addresses but they have the same content which means that your content is not unique.

First of all, let's add rule to redirect from startupplab.com to www.startupplab.com

1) The next rule redirects users from www.startupplab.com/index.php to www.startupplab.com.

    `<rule name="Index.php to home">`
    
      `<match url="^index.php" />`
      
      `<action type="Redirect" url="http://{HTTP_HOST}"></action>`
      
    `</rule>`
    
2) Removes the / at the end of a URL. For example: www.startupplab.com/ to www.startupplab.com.

    `<rule name="Remove trailing slash">`
    
      `<match url="(.*)/$" />`
      
      `<action type="Redirect" redirectType="Permanent" url="{R:1}"></action>`
      
    `</rule>`
    
3) Removes the "home" at the end of a URL. For example: www.startupplab.com/home to www.startupplab.com.

    `<rule name="Home">`
    
     `<match url="^home$" />`
     
     `<action type="Redirect" url="http://{HTTP_HOST}"></action>`
     
    `</rule>`
    
4) Removes the "home/index" at the end of a URL. For example: www.startupplab.com/home/index to www.startupplab.com.

    `<rule name="Home-index">`
    
      `<match url="^home/index$" />`
      
      `<action type="Redirect" url="http://{HTTP_HOST}"></action>`
      
    `</rule>`
    
5) This rule converts all symbols of a URL address to a lower case. For example: www.StartuppLab.com, www.STARTUPPLAB.COM and etc. will be redirected to the page with address www.startupplab.com.

    `<rule name="Convert to lower case" stopProcessing="true">`
    
      `<match url=".*[A-Z].*" ignoreCase="false" />`
      
      `<action type="Redirect" url="{ToLower:{R:0}}" redirectType="Permanent" />`
      
    `</rule>`
    
    
