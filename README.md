# StringBean
The featherweight responsive CSS Framework based on a 16-point system, rather than the traditional 12-point system that other frameworks use. 

Sometimes, 12 is just too few, especially on a high resolution screen, such as 4K - at 4K String Bean comes into its own!  This gives the developer the power to divide the screen up in more finite segments providing you with greater control over the widths of content on your site, especially at higher resolutions (think 2k, 3k, and 4k screens).

In addition to this, String Bean also has 5 breakpoints, instead of the traditional 4, so you can implement your design with: xsmall, small, medium, large, and xlarge.

## How it works
This demonstrates a page layout with StringBean classes applied.  You will notice a number of things specified, but take note of the line "column xsmall-16 small-16 medium-10 large-11 xlarge-12" - this defines the division as a column (floats left) then applies a point system with the xsmall-x small-x etc, similar to Bootstrap and Foundation 5, but with a twist:- we use a 16 point system rather than the limiting 12 point system used in the aforementioned.

    <header class="container">
      <nav class="row">
        <div class="column xsmall-16 small-16 medium-10 large-11 xlarge-12">
          <h1>
            StringBean
          </h1>
        </div>
        <div class="column xsmall-16 small-16 medium-5 large-4 xlarge-3">
          <p id="Strapline">
            Powering the internet, gently.
          </p>
        </div>
      </nav>
    </header>

#### Breakpoint Breakdown

    SELECTOR        (x)POINTS       DEVICE WIDTHS
    xsmall-x        1 to 16         =< 399px
    small-x         1 to 16         400px to 899px
    medium-x        1 to 16         900px to 1279px
    large-x         1 to 16         1280px to 1919px
    xlarge-x        1 to 16         >= 1920px
    full-16         16 (Fixed)      All Resolutions

##### Using breakpoint specific selectors
You can stack the breakpoint selectors on an element.

    class="xsmall-5 small-9 medium-10 large-2"

##### Taking full width on all breakpoints
If you apply this class then it will take 16 points (full width of parent) in all breakpoints.

    class="full-16"

### Layouts
Layouts give you the power to set a max-width size on the content so that when viewing the site above that breakpoint the site will be fixed width.  Viewing the site below that size (on a mobile or tablet etc) will make the site responsive.

    <main class="container">
        <article class="row layout-960">
            <h1>
                Hello World!
            </h1>
            <p>
                Some content goes in here.
            </p>
        </article>
    </main>

### Showing/Hiding Elements at Certain Breakpoints
You can use different sets of show/hide selectors to present the right content to the right device users without having to inject content - just mark the elements you wish to show/hide with StringBean selectors.

##### Hiding Content Below Breakpoints
You can hide content below certain breakpoints - for instance: hide-below-large will hide the element below the large breakpoint.

    <div class="hide-below-medium">
        Hello world!
    </div>

##### Showing Content Below Certain Breakpoints

    <div class="hide-above-medium">
        Hello World!
    </div>

##### Showing Content Only on Certain Breakpoints
You can use the show-only-x set of selectors to show content on certain breakpoints only.  The below example will show your element only on xsmall and large screens, and will be hidden for all other breakpoints.

    <div class="show-only-medium show-only-xlarge">
        Hello World!
    </div>

### Buttons
The button classes provide a beautiful way to display a button to the user.  

    <a href="/login" class="button">Login</a>
    <a href="/login" class="button">Register</a>
    <a href="/login" class="button">Contact</a>

### Element Colour Selectors
you can easily and consistently colour speciality/focus elements with standardised colours using selectors from the below table.

    SELECTOR        COLOUR      HEX CODE
    normal          Black       000000
    inactive        Grey        9d9d9d
    information     Blue        1a75ae
    success         Green       5eae45
    alert           Red         d93f3f
    regal           Purple      774a79

##### Buttons with Colour Selectors
If you combine the button class with other classes such as "information" (blue colour), "alert" (red), and "success" (green) you can display the right button for the action.

    <a href="/login" class="button normal">Login</a>
    <a href="/login" class="button inactive">Register</a>
    <a href="/login" class="button alert">Contact</a>

##### Divisions with Colour Selectors
You can also apply colour sleectors to other elements such as divisions...

    <div class="alert">
        There was an error saving your password!
    </div>

or...

    <aside class="success">
        You are logged in! (<a href="#logout">Logout</a>)
    </aside>

### Grids
The grid class is like the row class, except it accepts "box" sub elements (as per below).  These are used in combination to display a responsive grid to the user - a good use case for this would be a gallery of photos.

    <ul class="grid">
        <li class="box xsmall-16 small-16 medium-7 large-5 xlarge-3">
            Box #1
        </li>
        
        <li class="box xsmall-16 small-16 medium-7 large-5 xlarge-3">
            Box #2
        </li>
        
        <li class="box xsmall-16 small-16 medium-7 large-5 xlarge-3">
            Box #3
        </li>
    </ul>

As simple as that!  You should also check out the button functionality.

### A word on Internet Explorer 8 and Below
This framework has limited support for IE8 and below. The web has moved on since those early days, and we cannot support old browsers forever.  Now that Windows XP is out of support we welcome the deprecation of IE7 & 8, and look forward to a truely responsive internet.

If you require IE8 support then you can use the HTML5Shiv and Respond.js polyfills provided by third party, to give basic StringBean support.
