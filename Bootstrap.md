Hackbright Afternoon Lecture 9/23/21

Lecture: https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/

Demo: http://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap.zip

Bootstrap


Intro
### Goals ###
   - Introduce CSS Frameworks and how they’re used in the industry
   - Learn how to use Bootstrap


### CSS Frameworks ###
Bootstrap is the first major, open-source CSS framework
Bootstrap was created by developers at Twitter, development continues as an open source project
Many CSS frameworks and libraries are inspired by Bootstrap

They’ll usually provide
   - A grid system for laying out responsive pages of content
   - CSS for UI components like buttons, navbars
   - CSS for accessibility like screen-reader-only styles
   - Sometimes they even have JavaScript plugins


Why Use a CSS Framework?
Writing CSS to make responsive pages that are compatible for all devices and browsers is hard!
Why rebuild the wheel when the work has already been done for you?


### Bootstrap Myths ###
Myth: All Bootstrap Sites Look the Same
Here’s an example of a “Bootstrappy” site: https://getbootstrap.com/  [LINK]
Reality: it’s easy to make your site look different by adding custom CSS

[NOTEBOX-START]
More sites built with Bootstrap

For more examples of sites built with Bootstrap, check out this blog post from Bootstrap Bay
[LINK] https://bootstrapbay.com/blog/built-with-bootstrap/
[NOTEDBOX-END]


Myth: Real Developers Don’t Use Bootstrap
Reality: Many companies use Bootstrap (or a CSS framework that was inspired by Bootstrap)


### Getting Started ###

### Installing Bootstrap ###

**1 Go to the Bootstrap homepage: https://getbootstrap.com/ [LINK]

**2 Find links to Bootstrap where bootstrap is located on a CDN (Scroll to the bottom of the page → Bootstrap CDN → CSS Only)


[NOTEBOX-START]
What is a CDN?
CDN stands for content distribution network. They are highly optimized networks of servers that are designed primarily to serve static resources like CSS, JavaScript, and images.
[NOTEBOX-END]


**3 The CSS only tag should go in the head element of your HTML page, before your own CSS file. Add this to your base.html
    <!doctype html>
    <html>
    <head>
        <!-- Bootstrap CSS -->
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
        <!-- Your custom styles -->
        <link rel="stylesheet" href="/static/mystyles.css">
    </head>
    <body>
        <!-- content of your webpage -->
    </body>
    </html>


**4 If you want to take advantage of Bootstrap’s interactive UI components, you’ll also need to import their JavaScript files.
    <!doctype html>
    <html>
    <head>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
    </head>
    <body>
        <!-- content of your webpage -->
        <!-- Bootstrap JavaScript Bundle with Popper (a Bootstrap dependency for popovers) -->
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-gtEjrD/SeCtmISkJkNUaaKMoLD0//ElJ19smozuHV6z3Iehds+3Ulb9Bn9Plx0x4" crossorigin="anonymous"></script>
    </body>
    </html>


[NOTEBOX-START]
Why is the Bootstrap JavaScript Bundle at the bottom of the body tag?
In their documentation, Bootstrap recommends placing the script tag for their Bootstrap JavaScript Bundle near the end of your page, right before the closing body tag. We follow this recommendation in our examples.
[NOTEBOX-END]


You’re Ready to Go!
Now you can check out the Bootstrap docs: https://getbootstrap.com/docs/5.0/getting-started/introduction/ 

   - Pick components that you want to implement in your project
   - Check out the example code
   - Use Bootstrap’s CSS classes in your HTML


### The Grid System ###

Good Things Come in 12’s
Bootstrap uses a 12-unit grid system for laying out responsive webpages
[IMG]https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/#good-things-come-in-12-s



### Containers ###
Bootstrap requires all site content to be inside a container.

Fixed-width Containers
    <body>
    <div class="container">
    <!-- Use "container" for a responsive fixed width page. -->
    <!-- REST OF PAGE CONTENT -->
    </div>
    </body>
By default, containers have whitespace on left and right side to center page content
[IMG] https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/#fixed-width-containers


Full-width Containers
To get rid of whitespace and have content take up full width, add class container-fluid.
    <body>
    <div class="container-fluid">
        <!-- Add class "container-fluid" for a full width page. -->
        <!-- CONTENT TAKES UP FULL WIDTH -->
    </div>
    </body>


Rows
Rows are placed inside the container to create horizontal groups of columns.
    <body>
    <div class="container">
        <div class="row">
        <!--Columns go here-->
        </div>
        <div class="row">
        <!--You can have as many rows as you need.-->
        </div>
    </div>
    </body>


Columns
Columns go inside of rows.
Content goes inside the columns.
You have 12 columns to work with.

Two Columns of Equal Width
    <body>
    <div class="container">
        <div class="row">
        <div class="col">
            <!-- COLUMN ONE -->
        </div>
        <div class="col">
            <!-- COLUMN TWO -->
        </div>
        </div>
    </div>
    </body>


Differently-Sized Columns
    <body>
    <div class="container">
        <div class="row">
        <div class="col-3">
            <!-- SMALL COLUMN -->
        </div>
        <div class="col-9">
            <!-- LARGER COLUMN -->
        </div>
        </div>
    </div>
    </body>


Multiple Rows and Columns
    <body>
    <div class="container">
        <div class="row">
        <div class="col-3">
            <!-- SMALL COLUMN -->
        </div>
        <div class="col-9">
            <!-- LARGER COLUMN -->
        </div>
        </div>
        <div class="row">
        <div class="col-7">
            <!-- LARGER COLUMN -->
        </div>
        <div class="col-5">
            <!-- SMALL COLUMN -->
        </div>
        </div>
    </div>
    </body>


Also, you can nest columns inside of columns if you need to but they must have a row around them. It’s usually something that can be solved with normal implementation of columns but if you have to do this, your code would look something like:
    <div class="row">
    <div class="col-8">
        <div class="row">
        <div class="col-6"></div>
        <div class="col-6"></div>
        </div>
    </div>
    <div class="col-4">Sidebar </div>
    </div>


### Responsive Design ###
Bootstrap’s grid system includes classes that allow you to change your site’s layout based on a user’s screen size
Out of the box, Bootstrap handles six display sizes

        Size                  Screen width (px)               Example

.col-xxl- (xx-large)            ≥ 1200 px              larger desktops/laptops

.col-xl- (x-large)              ≥ 1200 px               large desktops/laptops

.col-lg- (large)              992 ≤ px < 1200               desktops/laptops

.col-md- (medium)              768 ≤ px < 992                 tablets

.col-sm- (small)               576 ≤ px < 768          phones in landscape mode

.col- (x-small)                  px < 576               phones in portrait mode



### How Responsive Columns Work ###
If you don’t indicate a screen-size, Bootstrap will use that column size for all screens    
    <div class="row">
    <div class="col-12">
        Sidebar
    </div>
.
    <div class="col-12">
        Main Content
    </div>
    </div>

This layout is great for mobile devices, but doesn’t use space effectively for larger screens

Let’s add col-md-6 so both columns will take up half the screen for tablets:
    <div class="row">
    <div class="col-12 col-md-6">
        Sidebar
    </div>
.
    <div class="col-12 col-md-6">
        Main Content
    </div>
    </div>
Now, columns will be size 12 until the browser detects a screen that’s at least 768px wide

Now we can lay out the page for large screens:
    <div class="row">
    <div class="col-12 col-md-6 col-lg-3">
        Sidebar
    </div>
.
    <div class="col-12 col-md-6 col-lg-9">
        Main Content
    </div>
    </div>
    Both columns will be 12 until a medium screen

Then, columns will be 6 until a large screen — for large screens and above, the sidebar will be 



### Offset ###
Offset is a way to move columns to the right by x columns.
[IMG] https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/#offset
<body>
  <div class="container">
.
    <div class="row">
      <div class="col-4 offset-8">
        <img src="puppy.png">
      </div>
    </div>
.
    <div class="row">
      <div class="col-12">
        <h1>Offset Puppy</h1>
        Puppy ipsum dolor sit good dog window paws...
      </div>
    </div>

  </div>
</body>


### Customizing Order ###
[ALL_IMGS]https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/#customizing-order

Normally, sections that are one on top of the other on a small screen:

[SECTION 1 (width 12 columns)]
[SECTION 2 (width 12 columns)]


Will move to a left-to-right order on a larger screen:

[SECTION 1 (width 6 columns)][SECTION 2 (width 6 columns)]


But what if we want this on a phone:

[SECTION 1 (width 12 columns)]
[SECTION 2 (width 12 columns)]


and this on a monitor:

[SECTION 1 (width 6 columns)][SECTION 2 (width 6 columns)]

Use the class order-x to rearrange the order, where x is any number from 1 to 12, specifying the actual order from left to right.


As an example, with uneven columns on a large screen:

<div class="container">
  <div class="row">
    <div class="col-12 col-md-3 order-md-2">
      <h1>Table of Contents</h1>
      <!-- APPEARS LAST (FARTHEST TO RIGHT) ON MEDIUM SCREENS -->
    </div>
    <div class="col-12 col-md-9 order-md-1">
      <h1>Article</h1>
      <!-- APPEARS FIRST ON MEDIUM SCREENS -->
    </div>
  </div>
</div>


### Planning for Bootstrap ###
Early step in planning a project:

Create wireframes to get a feel for features and user flow.
(Very helpful for planning how you will implement Bootstrap)
Here are some common wireframe symbols to help you get started.
Keep it simple. Stick to paper and pencil.


[IMG]https://fellowship.hackbrightacademy.com/materials/t3/lectures/bootstrap/#planning-for-bootstrap


### The Nav Bar ###
Nav and Navbar Classes
Bootstrap has a very powerful set of classes for navigation.
You can put images, buttons, forms, links, and non-nav text in the navbar.
You can also fix the navbar to the top or allow it to scroll away.
There are also classes for managing alignment within the navbar.
The docs are pretty thorough and the example code is very helpful.

Navbar https://getbootstrap.com/docs/5.0/components/navbar/



### Customizing Bootstrap ###
Adding Your Own Style
    <head>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
.
    <!-- Your custom styles -->
    <link href="/static/project.css" rel="stylesheet">
    </head>



### Inspect Element ###
A.K.A. Your Best Friend

Other Things to Know and Use
A Few Bootstrap Components

Forms https://getbootstrap.com/docs/5.0/forms/overview/
   - Default HTML forms don’t look great. Bootstrap class form-control provides styling and the grid system can be used to adjust alignment and layout of forms

Tables https://getbootstrap.com/docs/5.0/content/tables/
   - Default HTML tables leave a lot to be desired. Bootstrap table classes like table-striped and table-hover table variant classes provide styling. The table-sm and table-responsive classes are also helpful for layout.

Modal Windows https://getbootstrap.com/docs/5.0/components/modal/
   - Modal windows are a clean, design-friendly way to include more information without cluttering the interface. Common uses include log-in/log-out windows, forms, extra information, and anything else that you want to show a user without navigating them to a new page.

Dropdowns https://getbootstrap.com/docs/5.0/components/dropdowns/
   - Dropdowns are useful for forms and navbars.

Tooltips and Popovers https://getbootstrap.com/docs/5.0/components/popovers/
   - Tooltips and popovers are a great way to include small additional piece of information. Common uses include showing instructional elements on forms and displaying a piece of media over a link.

Alerts https://getbootstrap.com/docs/5.0/components/alerts/
   - Alerts are a useful way to style user feedback elements like login success messages or form submit failure messages.

Utilities https://getbootstrap.com/docs/5.0/utilities/api/
   - Utilities are a treasure trove of small things that can be very helpful. Contextual colors and backgrounds add visual cues to reinforce the text (such as a red background for a failure notice). Utilities can also supply things like close icons for modal windows.

Visibility https://getbootstrap.com/docs/5.0/utilities/visibility/
   - Visibility classes are a useful way to account for accessibility compliance and better responsive design. You can opt to show or hide certain elements whether for the use of screen readers or for hiding or adding things to different device layouts.



### Bootstrap Icons ###
Bootstrap Icons have 1000+ free and high quality icons
   - Go to https://icons.getbootstrap.com/#install to find the link to include the icons stylesheet
   - Add it in a link tag to the head of your HTML (just like we did with Bootstrap)
    <head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.5.0/font/bootstrap-icons.css">
    </head>

Now you can go to Bootstrap Icons https://icons.getbootstrap.com/
   - Find the icon you want to use
   - Copy the <i> tag to use the web font paste to your HTML (or use the SVG version if you prefer)
    <div class="container">
    This is a star: <i class="bi bi-star"></i>
    </div>


For a more detailed explanation on how this works, check out the documentation https://icons.getbootstrap.com/#usage



Resources!
Bootstrap Docs http://getbootstrap.com/

Bootstrap Resources http://bootsnipp.com/resources