//Just occasionally, you will want to force a line break. You do
//this using the br element, for example when you want to
//include a postal address:
<p>The Willows<br>
21 Runnymede Avenue<br>
Morton-in-the-marsh<br>
Oxfordshire OX27 3BQ</p>


//Browsers automatically wrap text to fit within the margins.
//Line breaks can be introduced wherever space characters appear in
//the markup. Sometimes you will want to prevent the browser from
//wrapping text between two particular words. For instance between
//two words in a brand name such as "Coca Cola". The
//trick is to use &nbsp; in place of the space
//character, for example:
Sweetened carbonated beverages, such as Coca&nbsp;Cola,
have attained world-wide popularity.


//Let's assume that each section starts with a heading, for
//instance:
<h2>Local Night Spots</h2>


//You make the heading into a potential target for a hypertext
//link by enclosing its contents with 
//<a name=identifier> .... </a>
<h2><a name="night-spots">Local Night Spots</a></h2>


//The name attribute specifies the name you will use to identify
//the link target, in this case: "night-spots". The table
//of contents can now include a hypertext link using this name, for
//instance:
<ul>
  ...
  <li><a href="#night-spots">Local Night Spots</a></li>
  ...
</ul>


//The # character is needed before the target name. If the
//target is in a different document, then you need to place the web
//address of that document before the # character. For example if
//the document is in "http://www.bath.co.uk/", then the
//link becomes:
<a href="http://www.bath.co.uk/#night-spots">Local Night Spots</a>


//In the future, you will eventually be able to define link
//targets without the need for the <a> element. The
//new method is much easier, as all you need to do is to add an 
//id attribute to the heading, for instance:
<h2 id="night-spots">Local Night Spots</h2>


//One advantage of the Web is that text is automatically
//wrapped into lines fitting within the current window size.
//Sometimes though, you will want to disable this behavior. For
//example when including samples of program code. You do this using
//the pre element. For instance:
<pre>
    void Node::Remove()
    {
        if (prev)
            prev->next = next;
        else if (parent)
            parent->SetContent(null);

        if (next)
            next->prev = prev;

        parent = null;
    }
</pre>


//Which renders as:
    void Node::Remove()
    {
        if (prev)
            prev->next = next;
        else if (parent)
            parent->SetContent(null);

        if (next)
            next->prev = prev;

        parent = null;
    }


//The text and background colors were set via the style sheet.
//Note that all line breaks and spaces are rendered exactly as they
//appear in the HTML. The exception is a newline immediately after
//the start tag <pre> and immediately before the end
//tag </pre>, which are discarded. This means that the
//following two examples are rendered identically:
<pre>preformatted text</pre>

<pre>
preformatted text
</pre>


//Preformatted text is generally rendered using a monospaced
//font where each character has the same width. If you define a
//style rule for the pre element, some browsers forget to
//use the monospace font, necessitating the use of the font-family
//property. For instance if you want to render all pre elements in
//green you can define the style rule:
<style type="text/css">
  pre { color: green; background: white; font-family: monospace; }
</style>


//When setting the foreground color for text, you are advised to
//also set the color for the background. This will prevent accidents
//where the background color is hard to distinguish from the
//foreground. Rather than setting the background color on the pre
//element, you may find it more convenient to set it on the body
//element, for instance:
<style type="text/css">
  body { color: black; background: white; }
  pre { color: green; font-family: monospace; }
</style>


//With HTML, you can choose whether any given image is treated
//as part of the current text line or is floated to the left or
//right margins. You control this via the align attribute.
//If the align attribute is set to left the image floats to
//the left margin. If it is set to right the image floats to
//the right margin. For instance:
<p><img src="sun.jpg" alt="sunburst graphic"
width="32" height="21" align="left"> This text will be
flowed around the right side of the graphic.</p>


//The following uses align="right"
<p><img src="sun.jpg" alt="sunburst graphic"
width="32" height="21" align="right"> This text will be
flowed around the left side of the graphic.</p>


//To force rendering to continue below the floated image you can
//use the <br clear=all> element, for
//example:
<p><img src="sun.jpg" alt="sunburst graphic"
width="32" height="21" align="left"> This text will be
flowed around the right side of the graphic.<br clear="all">
This starts a new line below the floated image.</p>


//The markup for this is as follows:
<p align="center">
   <img src="pages.gif" width="384" height="245"
      alt="site map" usemap="#sitemap" border="0">
   <map name="sitemap">
      <area shape="circle" coords="186,44,45" 
         href="Overview.html" alt="Getting Started">
      <area shape="circle" coords="42,171,45" 
         href="Style.html" alt="A Touch of Style">
      <area shape="circle" coords="186,171,45"
         alt="Web Page Design">
      <area shape="circle" coords="318,173,45"
         href="Advanced.html" alt="Advanced HTML">
   </map>
</p>


//If two or more defined regions overlap, the region-defining
//element that appears earliest in the document takes precedence
//(i.e., responds to user input). For a complex shape such as an
//anular ring, you can make part of a region inactive by overlaying
//it with another region using the nohref attribute, for
//example:
      <area shape="circle" coords="186,44,50" nohref>
      <area shape="circle" coords="186,44,100" 
         href="Overview.html" alt="Getting Started">


//The markup for this is:
<table border="1">
<tr><th>Year</th><th>Sales</th></tr>
<tr><td>2000</td><td>$18M</td></tr>
<tr><td>2001</td><td>$25M</td></tr>
<tr><td>2002</td><td>$36M</td></tr>
</table>


//You can increase the amount of padding for all cells using the
//cellpadding attribute on the table element. For instance,
//to set the padding to 10 pixels:
<table border="1" cellpadding="10">


//By contrast the cellspacing attribute sets the space
//between the cells. Setting the cell spacing to 10:
<table border="1" cellpadding="10" cellspacing="10">


//You can set the width of the table using the width
//attribute. The value is either the width in pixels or a
//percentage value representing the percentage of the space
//available between the left and right margins. For instance to set
//the width to 80% of the margins:
<table border="1" cellpadding="10" width="80%">


//By default browsers center heading cells (th), and left align
//data cells (td). You can change alignment using the align
//attribute, which can be added to each cell or to the row (tr
//element). It is used with the values "left",
//"center" or "right":
<table border="1" cellpadding="10" width="80%">
<tr align="center"><th>Year</th><th>Sales</th></tr>
<tr align="center"><td>2000</td><td>$18M</td></tr>
<tr align="center"><td>2001</td><td>$25M</td></tr>
<tr align="center"><td>2002</td><td>$36M</td></tr>
</table>


//The former occurs when a cell is empty:
<td></td>


//To prevent this, include a non-breaking space:
<td>&nbsp;</td>


//The heading "Year" now spans two rows, while the
//heading "Sales" spans three columns. This is done by
//setting the rowspan and colspan attributes
//respectively. The markup for the above is:
<table border="1" cellpadding="10" width="80%">
<tr align="center"><th rowspan="2">Year</th><th colspan="3">Sales</th></tr>
<tr align="center"><th>North</th><th>South</th><th>Total</th></tr>
<tr align="center"><td>2000</td><td>$10M</td><td>$8M</td><td>$18M</td></tr>
<tr align="center"><td>2001</td><td>$14M</td><td>$11M</td><td>$25M</td></tr>
</table>


//You can simplify this by taking advantage of the fact that
//browsers don't need the end tags for table cells and
//rows:
<table border="1" cellpadding="10" width="80%">
<tr align="center"><th rowspan="2">Year<th colspan="3">Sales
<tr align="center"><th>North<th>South<th>Total
<tr align="center"><td>2000<td>$10M<td>$8M<td>$18M
<tr align="center"><td>2001<td>$14M<td>$11M<td>$25M
</table>


//This was produced using the following markup:
<table border="0" cellspacing="0" cellpadding="10">
<tr><th>Year</th><th>Sales</th></tr>
<tr><td>2000</td><td>$18M</td></tr>
<tr><td>2001</td><td>$25M</td></tr>
<tr><td>2002</td><td>$36M</td></tr>
</table>


//This page uses a style sheet to
//set the background colors for tables, with a different color for
//heading and data cells. The style rules I used are as
//follows:
table {
  margin-left: -4%;
  font-family: sans-serif;
  background: white;
  border-width: 2;
  border-color: white;
}
th { font-family: sans-serif; background: rgb(204, 204, 153) }
td { font-family: sans-serif; background: rgb(255, 255, 153) }


//Another way to set the background color is to use the 
//bgcolor attribute. This works with nearly all browsers, and
//doesn't rely on style sheet support. The first step is to
//determine the hexadecimal values for the red, green and blue
//components of the color you wish to use. A convertor is included in the style page.
<table border="0" cellspacing="0" cellpadding="10">
  <tr>
    <th bgcolor="#CCCC99">Year</th>
    <th bgcolor="#CCCC99">Sales</th>
  </tr>
  <tr>
    <td bgcolor="#FFFF66">2000</td>
    <td bgcolor="#FFFF66">$18M</td>
  </tr>
  <tr>
    <td bgcolor="#FFFF66">2001</td>
    <td bgcolor="#FFFF66">$25M</td>
  </tr>
  <tr>
    <td bgcolor="#FFFF66">2002</td>
    <td bgcolor="#FFFF66">$36M</td>
  </tr>
</table>


//You can position your tables midway between the left and right
//margins by using some CSS. If your style sheet includes the
//following rule, then all tables will be centered:
table {
   margin-left: auto;
   margin-right: auto;
}


//First here is the style rule:
table.centered {
   margin-left: auto;
   margin-right: auto;
}


//and here is the table markup:
<table class="centered" border="1">
<tr><th>Year</th><th>Sales</th></tr>
<tr><td>2000</td><td>$18M</td></tr>
<tr><td>2001</td><td>$25M</td></tr>
<tr><td>2002</td><td>$36M</td></tr>
</table>


//which was produced by the following markup:
<table border="1" cellpadding="10" width="80%">
<caption>Projected sales revenue by year</caption>
<tr align="center">
  <th>Year</th><th>Sales</th>
</tr>
<tr align="center"><td>2000</td><td>$18M</td></tr>
<tr align="center"><td>2001</td><td>$25M</td></tr>
</table>


//The table element's summary attribute should be
//used to describe the structure of the table for people who
//can't see the table. For instance: "the first column
//gives the year and the second, the revenue for that
//year".
<table summary="the first column gives the year
and the second, the revenue for that year">


//Applying this to the example table gives:
<table border="1" cellpadding="10" width="80%">
<caption>Projected sales revenue by year</caption>
<tr align="center">
  <th scope="col">Year</th>
  <th scope="col">Sales</th>
</tr>
<tr align="center"><td>2000</td><td>$18M</td></tr>
<tr align="center"><td>2001</td><td>$25M</td></tr>
</table>


//A final point is that you should consider using the 
//abbr attribute to specify an abbreviation for long headers.
//This makes it tolerable to listen to lists of headers for each
//cell, for instance:
<th abbr="W3C">World Wide Web Consortium</th>


//In the most common form, a roll-over consists of an image
//serving as a hypertext link. While the mouse pointer is over the
//image, it changes appearence to attract attention to the link.
//For example, you could add a glow effect, a drop shadow or simply
//change the background color. Here is an example:
<script type="text/javascript">
if (document.images)
{
    image1 = new Image;
    image2 = new Image;
    image1.src = "enter1.gif";
    image2.src = "enter2.gif";
}

function chgImg(name, image)
{
    if (document.images)
    {
        document[name].src = eval(image+".src");
    }
}
</script>

...

<a href="/" onMouseOver='chgImg("enter", "image2")'
onMouseOut='chgImg("enter", "image1")'><img name="enter"
src="enter1.gif" border="0" alt="Enter if you dare!"></a>


//If your website has several sponsors, then you can use an
//image link that cycles through each of the sponsors in turn. The
//first step is to create an image for each of your sponsors. All
//the images should have the same size. The corresponding URLs for
//the images and for the websites are then placed into the arrays
//named adImages and adURLs defined at the start of
//the script. The img element for the link should be initialized to
//the first image in the array. The cycle is started off using the
//onload event on the body element.
<html>
<head>
<title>cycling banner ads</title>
<script type="text/javascript">
if (document.images)
{
    adImages = new Array("hosts/csail.gif",
                "hosts/ercim.gif", "hosts/keio.gif");
    adURLs = new Array("www.csail.mit.edu",
                "www.ercim.org", "www.keio.ac.jp");
    thisAd = 0;
}

function cycleAds()
{
    if (document.images)
    {
        if (document.adBanner.complete)
        {
            if (++thisAd == adImages.length)
                thisAd = 0;

            document.adBanner.src = adImages[thisAd];
        }
    }

    // change to next sponsor every 3 seconds
    setTimeout("cycleAds()", 3000);
}

function gotoAd()
{
    document.location.href = "http://" + adURLs[thisAd];
}
</script>
</head>
<body onload="cycleAds()">
...

<a href="javascript:gotoAd()"><img name="adBanner"
src="hosts/csail.gif" border="0" alt="Our sponsors"></a>


//The content of a noscript element is only shown if the
//browser doesn't support scripting. It should be used when you want
//to give people access to information that would otherwise be
//inaccessible to people with browsers that don't support scripting.
//Let's assume that you want to make the links for your sponsors
//available as text:
<noscript>
Our sponsors: <a href="http://www.lcs.mit.edu/">MIT</a>,
<a href="http://www.inria.fr/">INRIA</a>, and
<a href="http://www.keio.ac.jp/">Keio University</a>.
</noscript>


//The next step is to create a playlist file with the file
//extension .m3u. This avoids the lengthy wait before users start
//to hear the music that  typically occurs if you link directly
//to the mp3 file. You can create the playlist with a text editor
//and it just needs to include the URL for the mp3 file. For the
//example sound file, this would be:
http://example.com/music/myband.mp3


//Upload the m3u playlist file to your web server. You can
//now add a link to your band's web page as follows:
<a href="http://example.com/music/myband.m3u"
type="audio/x-mpegurl">listen to our band</a>


