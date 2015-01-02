Building blocks of HTML5 as an open platform
-------

HTML5 adds many new syntactic features such as <code>&lt;video&gt;</code>, <code>&lt;audio&gt;</code> & <code>&lt;canvas&gt;</code> elements, as well as the integration of scalable vector graphics (SVG) content (that replaces the uses of generic <code>&lt;object&gt;</code> tags) and MathML for mathematical formulae. These features are designed to make it easy to include and handle multimedia and graphical content without having to resort to proprietary plugins and APIs such as Flash.

Semantic HTML
------

The use of <a href="http://en.wikipediorg/wiki/HTML">HTML</a> markup to reinforce the meaning of the information in webpages.
e.g. <code>&lt;section&gt;, &lt;article&gt;, &lt;nav&gt;, &lt;header&gt;, &lt;footer&gt;, &lt;audio&gt;, &lt;video&gt;</code>

New HTML5 elements
------

<code>&lt;article&gt;, &lt;aside&gt;, &lt;bdi&gt;, &lt;command&gt;, &lt;details&gt;, &lt;figure&gt;, &lt;figcaption&gt;, &lt;summary&gt;, &lt;header&gt;, &lt;footer&gt;, &lt;hgroup&gt;, &lt;mark&gt;, &lt;meter&gt;, &lt;nav&gt;, &lt;progress&gt;, &lt;ruby&gt;, &lt;rt&gt;, &lt;section&gt;, &lt;time&gt;,</code> and <code>&lt;wpr&gt;.</code>

Elements removed from HTML5
------

 <code>&lt;frame&gt;</code> and <code>&lt;frameset&gt;</code> have been eliminated. Other elements that are no longer supported include: <code>&lt;noframe&gt;, &lt;applet&gt;, &lt;bigcenter&gt; </code>and <code>&lt;basefront&gt;.</code>

HTML data attributes
------

Custom data attributes are intended to store custom data private to the page or application, for which there are no more appropriate attributes or elements.

<pre><code>&lt;audio controls="controls"&gt;
	&lt;source src="track1.mp3"type ="audio/mpeg"data-duration="1min5secs" data-tempo="125bpm"data-artist="The Beatles"/&gt;
&lt;/audio&gt;</code></pre>

DOCTYPE definition
------

 Including <code>&lt;!DOCTYPE html&gt;</code> will cause browsers that don't presently support HTML5 to enter into standards mode, meaning they'll interpret the long-established parts of HTML while ignoring the new features they don't support. The DOCTYPE must be at the beginning of the HTML document, otherwise quirks mode will be triggered in IE9 or below.

Standards Mode vs Quirks Mode
------

In quirks mode, layout emulates nonstandard behaviour in Navigator 4 and Internet Explorer 5 for Windows. In almost standards mode (or strict mode), there are only a very small number of quirks implemented. In full standards mode, the behaviour is described by the HTML and CSS specifications.

XHTML limitations
------

XHTML has poor browser support. Internet Explorer and a number of other user agents cannot parse XHTML as XML. The W3C <a href="http://www.w3.org/TR/xhtml-media-types/#media-types">recommends only sending xhtml to browsers that specifically declare support</a> in the HTTP Accept header and ignoring those browsers that don't specifically declare support. Note that headers aren't always reliable and it has been known to cause issues with caching.

Serving a page with content in multiple languages
------

* Properly sort strings based on locale
* Format date based on locale
* Always show times in the user's time zone
* Show distance measurements for the user's locale (ie: Miles versus Kilometres?)
* Lay out the website in right-to-left for languages like Hebrew
* Think about how you pluralize your messages. <code>String message = "Please fix the following error" + (errors.size() &gt; 1 ? "s" : "");</code> doesn't work in an internationalized program
* Think about how to lay out your web pages when the length of text may vary wildly.. and never assume that a character is more-or-less a certain width (a single character in Kanji might be 8 times wider than a lower case 'i')
* Use the <a href="https://support.google.com/webmasters/answer/answer.py?answer=62399">geotargeting tool</a> in Webmaster Tools to indicate to Google that your site is targeted at a specific country

<a title="http://stackoverflow.com/questions/3876213/design-patterns-for-multiple-language-website" href="http://stackoverflow.com/questions/3876213/design-patterns-for-multiple-language-website">http://stackoverflow.com/questions/3876213/design-patterns-for-multiple-language-website</a>

Designing & developing for multilingual sites
-------

* Consider length of words as the font size may not be suitable for all languages
* Use unicode &lt;meta charset=”UTF-8”&gt;
* Use the lang pseudo class e.g.

<pre><code>:lang(en) {font-size: 85%; font-family: arial, verdana, sans-serif;}

:lang(zh) {font-size: 125%; font-family: helvetica, verdana, sans-serif;}
</pre></code>

Cookies, sessionStorage and localStorage.
------

HTML5 web storage is a generic term for the new client-side data storage options.

* Local Storage is persistent and scoped to the domain. 'default' stores name/value pairs and ‘Web SQL’ (aka Web Database) uses a SQL database
* Session Storage is non persistent and scoped only to the current window. The one exception to this is when a browser crashes, and is restarted. Typically, browsers will in this case reopen all the windows that were open when the browser crashed. The specification allows in this situation for sessionStorage to persist for reopened windows from before the crash (WebKit, Mozilla and Opera browsers support this and IE9 and up).
* Cookies is the old way of doing all of the above. Stores name/value pairs per domain

<a title="http://www.webdirections.org/blog/webstorage-persistent-client-side-data-storage/" href="http://www.webdirections.org/blog/webstorage-persistent-client-side-data-storage/">http://www.webdirections.org/blog/webstorage-persistent-client-side-data-storage/</a>

The difference between 'get' & 'post'
------

POST requests are used to send data to the server to be processed in some way, like by a CGI script. GET requests include all required data in the URL. A POST request is different from a GET request in the following ways:

* A block of data is sent with the request, in the message body. There are usually extra headers to describe this message body, like <tt>Content-Type:</tt> and <tt>Content-Length:</tt>
* The request URI is not a resource to retrieve and is usually a program to handle the data you're sending
* The HTTP response is normally program output, not a static file
* Parameters are not saved in the browser history or in web server logs so are more secure

<a title="http://www.diffen.com/difference/GET_(HTTP)_vs_POST_(HTTP)" href="http://www.diffen.com/difference/GET_(HTTP)_vs_POST_(HTTP">http://www.diffen.com/difference/GET_(HTTP)_vs_POST_(HTTP)</a>

HTML5 Boilerplate files : humans.txt, 404 page,  robots.txt, .htaccess
------

Humans.txt is a text file that contains information about the people who created the site. <a title="http://humanstxt.org/Standard.html" href="http://humanstxt.org/Standard.html">http://humanstxt.org/Standard.html</a>

“404 Not Found” is a HTTP standard response code indicating that the client was able to communicate with the server, but the server could not find what was requested.

Robots.txt is a text file that restricts access to your site by search engine robots that crawl the web. The file can be created using Google Webmaster Tools.

.Htaccess is a configuration file for use on web servers running Apache Web Server. The file can be used to alter the configuration of the Apache Web Server software to enable/disable additional functionality and features that the Apache Web Server software has to offer. These facilities include basic redirect functionality, for instance if a 404 file not found error occurs, or for more advanced functions such as content password protection or image hot link prevention. <a title="http://htaccess-guide.com/" href="http://htaccess-guide.com/">http://htaccess-guide.com/</a>
