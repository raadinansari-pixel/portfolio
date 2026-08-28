---
layout: post
title: About
permalink: /about/
comments: true
---

## As a conversation Starter

Here are some places I have lived in my life.

<comment>
Flags are made using Wikipedia images
</comment>

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    s*/
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "https://commons.wikimedia.org/wiki/Special:FilePath/Lion_and_Sun_flag.svg", "description": "Iran - Salam"},
        {"flag": "0/01/Flag_of_California.svg", "description": "California - Hi"},
    ];

    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = location.flag.startsWith("http") ? location.flag : http_source + location.flag;
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

### Journey through Life

Here is what I did at those places

- 🏫 Monterrey Ridge Elementary School San Diego, CA United States
- 🏫 Oak Valley Middle School San Diego, CA
- 🏫 Del Norte High School Class of 2029 San Diego, CA

### Culture, Family, and Fun

Everything for me, as for many others, revolves around family.

- My parents are originally from Shiraz and Tehran in Iran.
- My family consists of me, my 2 younger brothers who are 11 and 8 with my mom and dad.
- I play soccer and have been playing for around 10 years and my favorite soccer team is FC Barcelona.
- The gallery of photos has some of my family, fun, sports and culture. 

<comment>
Gallery of Pics, scroll to the right for more ...
</comment>
<div class="image-gallery">
    <img src="{{site.baseurl}}/images/about/3711B7D0-37D3-4DB9-913A-39803178A702.jpeg" alt="Child at In-N-Out">
    <img src="{{site.baseurl}}/images/about/58D793CC-856D-44BD-98AD-F3647628C687_1_105_c.jpeg" alt="Soccer player on the field">
    <img src="{{site.baseurl}}/images/about/9C1D434F-4CC5-4805-9CEA-6D9C92584153_1_105_c.jpeg" alt="Child wearing a Barcelona shirt at a trophy display">
    <img src="{{site.baseurl}}/images/about/A291BD39-2295-4617-9677-1B508CE2645E_1_102_o.jpeg" alt="Family in matching pajamas">
</div>
