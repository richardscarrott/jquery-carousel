This is the basic HTML structure required:
------------------------------------------
    <div id="my-carousel">
        <ul>
            <li>
                <!-- item 1 content -->
            </li>
            <li>
                <!-- item 2 content -->
            </li>
            <li>
                <!-- item 3 content -->
            </li>
            <li>
                <!-- item 4 content -->
            </li>
            <li>
                <!-- item 5 content etc. -->
            </li>
        </ul>
    </div>

Here's some CSS to get you going (I've flagged which declarations are required):
--------------------------------------------------------------------------------
    #my-carousel ul {
        position:absolute; /* required */
        overflow:hidden; /* required */
        margin:0;
        padding:0;
        list-style:none;
    }
     
    #my-carousel ul li {
        float:left; /* required */
        width:100px;
        height:200px;
        margin:0 10px 0 0;
    }
     
    #my-carousel .mask {
        position:relative; /* required */
        overflow:hidden; /* required */
        width:540px; /* required */
    }
     
    #my-carousel .pagination-links {
        list-style:none;
        margin:0;
        padding:0;
    }
     
    #my-carousel .pagination-links li {
        display:inline;
    }
     
    #my-carousel .pagination-links li.current {
        background:grey;
    }
     
    #my-carousel .disabled {
        color:grey;
    }

And here's the JavaScript:
--------------------------
    $(document).ready(function() {
        $('#my-carousel').carousel();
    });

You can pass in any number of options from the following defaults:
------------------------------------------------------------------
    {
        itemsPerPage: 1, // number of items to show on each page
        itemsPerTransition: 1, // number of items moved with each transition
        noOfRows: 1, // number of rows (see demo)
        nextPrevLinks: true, // whether next and prev links will be included
        pagination: true, // whether pagination links will be included
        speed: 'normal', // animation speed
        easing: 'swing' // supports the jQuery easing plugin
    }

The plugin supports multiple carousels on a single page and maintains jQuery's chainability so usage should feel pretty familiar but if you do become stuck see the demo or leave me a message.

For more information see: http://richardscarrott.co.uk/posts/view/jquery-carousel-plugin