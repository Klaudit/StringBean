![alt text](https://s3-eu-west-1.amazonaws.com/stringbean/StringBean-Simple.jpg "StringBean")

# Documentation
The featherweight responsive CSS Framework based on a 16-point system, rather than the traditional 12-point system that other frameworks use. 

Sometimes, 12 is just too few, especially on a high resolution screen, such as 4K - at 4K String Bean comes into its own!  This gives the developer the power to divide the screen up in more finite segments providing you with greater control over the widths of content on your site, especially at higher resolutions (think HD & UHD (2K, 3K, 4K, and above).

StringBean also has 5 breakpoints, instead of the traditional 4, so you can implement your design with: xsmall, small, medium, large, mega-hd, and mega-uhd.

## How it works
To define column widths we use a points system - each parent element/page is split into 16 points - you can then specify how wide a column or item is by applying the appropriate sized class.

This defines the division as a column (floats left) and applies a hard width, similar to Bootstrap and Foundation 5, but with a twist:- we use a 16 point system rather than the limiting 12 point system used in the aforementioned.

#### Breakpoint Breakdown

    LABEL     START    END      COLUMNS
    XSMALL    0        319px    16
    SMALL     320px    599px    16
    MEDIUM    600px    900px    16
    LARGE     901px    1600px   16
    MEGA-HD   1601px   2048px   16
    MEGA-UHD  2049px   ~        16
    FULL-16   0        ~        1

##### Using breakpoint specific selectors
You can stack the breakpoint selectors on an element.

    class="xsmall-5 small-9 medium-10 large-2"

##### Normal resolutions (sub-1080p HD)

    <header class="container">
      <nav class="row">
        <div class="column xsmall-16 small-16 medium-10 large-11">
          <h1>
            StringBean
          </h1>
        </div>
        <div class="column xsmall-16 small-16 medium-5 large-4">
          <p id="Strapline">
            Powering the internet, gently.
          </p>
        </div>
      </nav>
    </header>

##### HD and UHD Breakpoints
Notice the additional classes starting "mega-" - these define the breakpoints for HD (High Definition - 1080p to 2K) and UHD (Ultra-High Definition - 3K, 4K, etc).

    <header class="container">
      <nav class="row">
        <div class="column xsmall-16 small-16 medium-10 large-11 mega-hd-13 mega-uhd-14">
          <h1>
            StringBean
          </h1>
        </div>
        <div class="column xsmall-16 small-16 medium-5 large-4 mega-hd-3 mega-uhd-2">
          <p id="Strapline">
            Powering the internet, gently.
          </p>
        </div>
      </nav>
    </header>

##### Taking full width on all breakpoints
If you apply this class then it will take 16 points (full width of parent) in all breakpoints.

    class="full-16"

##### Three-Way Split
With great things comes a slight downside - and it is slight - 16 does not split equally three ways into integers. The knock-on effect of this is that you cannot have three identically width columns with the standard classes (as you would do with Bootstrap), so to achieve this three-way split we've added special classes to each breakpoint; where "medium" is replaced with the desired breakpoint and then "third" defines one-third of the screen:

    <div class="column medium-third">
        Column 1
    </div>
    <div class="column medium-third">
        Column 2
    </div>
    <div class="column medium-third">
        Column 3
    </div>

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

    <div class="show-only-medium show-only-large">
        Hello World!
    </div>

### Pre-Set Colour Classes
You can easily and consistently colour speciality/focus elements with standardised colours using selectors from the below table.

    NOTE: HEX has been deprecated - now RGBa standardised - docs need to be updated.

Pre-Set colour table:

    CLASS           COLOUR      HEX CODE
    normal          Black       000000
    inactive        Grey        9d9d9d
    information     Blue        1a75ae
    success         Green       5eae45
    alert           Red         d93f3f
    regal           Purple      774a79

### Tables, Rows, and Cells
Using .table, .row, and .cell you can create a responsive spreadsheet-style table for tabulated content.  If you use the status classes (alert, infomration, regal, etc) with the first three cells then you can create a header for the table.

    <div class="table">
        <ul class="row">
            <li class="cell information third">First Name</li>
            <li class="cell information third">Last Name</li>
            <li class="cell information third">Access Level</li>
        </ul>
        <ul class="row">
            <li class="cell third">John</li>
            <li class="cell third">Doe</li>
            <li class="cell third">1</li>
        </ul>
        <ul class="row">
            <li class="cell third">Jane</li>
            <li class="cell third">Doe</li>
            <li class="cell third">1</li>
        </ul>
        <ul class="row">
            <li class="cell third">John</li>
            <li class="cell third">Smith</li>
            <li class="cell third">2</li>
        </ul>
    </div>

### Grids
The grid class is like the row class, except it accepts "box" sub elements (as per below).  These are used in combination to display a responsive grid to the user - a good use case for this would be a gallery of photos.

    <ul class="grid">
        <li class="box xsmall-16 small-16 medium-7 large-5">
            Box #1
        </li>
        
        <li class="box xsmall-16 small-16 medium-7 large-5">
            Box #2
        </li>
        
        <li class="box xsmall-16 small-16 medium-7 large-5">
            Box #3
        </li>
    </ul>

### Buttons
The button classes provide a beautiful way to display a button to the user.  

    <a href="/login" class="button">Login</a>
    <a href="/login" class="button">Register</a>
    <a href="/login" class="button">Contact</a>

##### Buttons with Colour Selectors
If you combine the button class with other classes such as "information" (blue colour), "alert" (red), and "success" (green) you can display the right button for the action.

    <a href="/login" class="button normal">Login</a>
    <a href="/login" class="button inactive">Register</a>
    <a href="/login" class="button alert">Contact</a>

##### Button Sets
When you wrap your buttons in a "button set" it draws them closer together, making them a grouped set of CTAs (call to actions) - this is ideal for form completions.

    <div class="row button-set">
        <a href="" class="button information">One</a>
        <a href="" class="button information">Two</a>
        <a href="" class="button information">Three</a>
    </div>

### Info Wheels
Info Wheels are round dots that can contain 1, 2, or 3 characters - these can signify a version number, or an alert (such as the amount of unread notifications you have).

    <span class="info-wheel success">12</span>

### Labels
Labels are small blocks that look like miniture buttons - in style - but cannot be clicked or edited through the browser.  Labels are a good way to signify versions, or small snippets of information.

    <span class="label success">
        Version 1.1.4
    </span>

### Progress Bars
You can visually represent the state of loading AJAX or other assets by using the progress bar classes.

    <div class="progress-bar" style="width:500px;">
        <div class="progress-bar-filler information" style="width:75%;">75%</div>
    </div>

##### Divisions with Colour Selectors
You can also apply colour sleectors to other elements such as divisions...

    <div class="alert">
        There was an error saving your password!
    </div>

or...

    <aside class="success">
        You are logged in! (<a href="#logout">Logout</a>)
    </aside>

### Forms & Inputs

    <form action="post" method="/auth">
        <label>
            Username
        </label>
        <input type="text" placeholder="Enter your username" />
        
        <label>
            Password
        </label>
        <input type="password" placeholder="Enter your password" />
        
        <label>
            Pin No.
        </label>
        <input type="password" placeholder="1234" />
        
        <input type="submit" class="button information" value="Login" />
    </form>

As simple as that!  You should also check out the button functionality.

### A word on Internet Explorer 8 and Below
This framework has limited support for IE8 and below. The web has moved on since those early days, and we cannot support old browsers forever.  Now that Windows XP is out of support we welcome the deprecation of IE7 & 8, and look forward to a truely responsive internet.

If you require IE8 support then you can use the HTML5Shiv and Respond.js polyfills provided by third party, to give basic StringBean support.

# Project Release Information

### Master Branch
The master branch contains the latest stable version of StringBean, merged from the latest version branch periodically.

### Version Branches
StringBean is released in major+minor version.  By this it is meant 1.3, or 1.4, etc, not 1.3.2, for example.

# Support Information
Support can be delivered via the Github wiki and issue tabs - ask a question and I will endevour to answer.

# Want to contribute?
If you want to contribute to this project then feel free to look at the CONTRIBUTING.md file.
