# css_table_with_frozen_headers_and_cols
This repo contains instructions on how to make an HTML table where the header row and leftmost columns are frozen using CSS and JavaScript.

Web Design: Freezing the Top Row and Left Column of a Table
Author: Matt Nutsch
Date: 1-12-2018

In Microsoft Excel, there is a feature where the user can freeze the top row and leftmost columns of a table. 
It turns out that this is somewhat hard to do in HTML and CSS. 
Luckily this feature is still possible with a little bit of JavaScript programming.

***

Step 1. Start with a basic HTML table. 

<html>
  <head>
    <title>Frozen Column Test</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
  </head>
  
  <body>
    <table>
    </table>
  </body>
  
</html>

***

Step 2. Add in some content.

<html>
  <head>
    <title>Frozen Column Test</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  </head>
  
  <body>
    <table>
      <tr><th><input type="checkbox"></th><th>#</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th><th>Lorem Ipsum</th></tr>
      <tr><td><input type="checkbox"></td><td>1</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>2</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>3</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>4</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>5</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>6</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>2</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>7</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>8</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>9</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>10</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>11</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>12</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>13</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>14</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
      <tr><td><input type="checkbox"></td><td>15</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td><td>Lorem Ipsum</td></tr>
    </table>
  </body>
  
</html>

***

Step 3. Add CSS classes to the cells so that we can style them appropriately.
We want to freeze the two leftmost columns, so I created two classes "leftCol1" and "leftCol2".
We also want to freeze the topmost row, so I created a class called headContent.
The two leftmost columns of the header are kind of unique, so I created the classes "leftHead1" and "leftHead2" to style them.
I created a class called "bodyContent" to style all of the remaining cells in the table.
Finally, I created a number of secondary classes which were used to position the header row cells. These are labelled "col0" through "col8"
See the comments in the CSS below for details on what each item does.

<html>
  <head>
    <title>Frozen Column Test</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  </head>
  
  <body>
    <table>
      <tr><th class="leftHead1"><input type="checkbox"></th><th class="leftHead2">#</th><th class="headContent col0">Lorem Ipsum</th><th class="headContent col1">Lorem Ipsum</th><th class="headContent col2">Lorem Ipsum</th><th class="headContent col3">Lorem Ipsum</th><th class="headContent col4">Lorem Ipsum</th><th class="headContent col5">Lorem Ipsum</th><th class="headContent col6">Lorem Ipsum</th><th class="headContent col7">Lorem Ipsum</th><th class="headContent col8">Lorem Ipsum</th></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">1</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">2</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">3</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">4</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">5</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">6</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">7</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">8</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">9</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">10</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">11</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">12</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">13</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">14</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">15</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
    </table>
  </body>
  
</html>

/* CSS */

/* basic table styling */
table {
  border-collapse: separate;
  border-spacing: 0;
  border-top: 1px solid grey;
}

/* basic table cell styling */
td {
  margin: 0;
  margin-top: 19px; /* adjust this based on the height of the table header row + border */
  border: 1px solid grey;
  white-space: nowrap;
  border-top-width: 0px;
}

/* table header cell styling */
th {
  position: fixed;
  margin: 0; 
  margin-top: 0px;
  border: 1px solid grey;
  height: 18px; /* adjust this to resize the header row */
  white-space: nowrap;
  border-top-width: 0px;
}

/* This is the leftmost column other than the header */
.leftCol1 {
  position: fixed;
  width: 19px; /* set to the desired width */
  left: 30px; /* adjust this as appropriate */
  top: auto;
  border-top-width: 1px; /* only relevant for first row */  
  margin-top: 20px; /* this is off by 1 px to compensate for top border*/  
  height: 18px; /* This should match the height of leftCol2 */
  
  background-color: white; /* This is needed so that we don't see the other cells as they slide behind it */
  z-index: 2; /* This is needed so that we don't see the other cells as they slide behind it */
}

/* This is the second from left column other than the header */
.leftCol2 {
  position: fixed;
  width: 19px; /* set to the desired width */
  left: 52px; /* adjust this as appropriate. It should equal the value in leftCol1 + the width of leftCol1 + borders */
  top: auto;
  border-top-width: 1px; /*only relevant for first row */
  margin-top: 20px; /* this is off by 1 px to compensate for top border*/  
  height: 18px; /* This should match the height of leftCol1 */  
  background-color: white; /* This is needed so that we don't see the other cells as they slide behind it */
  z-index: 2; /* This is needed so that we don't see the other cells as they slide behind it */
}

/* This is the leftmost column inside the header row. */
.leftHead1 {
  position: fixed;
  width: 19px;
  left: 30px;
  top: auto;
  border-top-width: 1px;
  /*only relevant for first row*/
  margin-top: -1px;
  /*compensate for top border*/
  height: 18px;
  
  background-color: white; /* This is needed so that we don't see the other cells as they slide behind it */
  z-index: 2; /* This is needed so that we don't see the other cells as they slide behind it */
}

/* This is the second from left column inside the header row. */
.leftHead2 {
  position: fixed;
  width: 19px;
  left: 52px; /* set to the width of  */
  top: auto;
  border-top-width: 1px;
  /*only relevant for first row*/
  margin-top: -1px;
  /*compensate for top border*/
  height: 18px;
  
  background-color: white; /* This is needed so that we don't see the other cells as they slide behind it */
  z-index: 2; /* This is needed so that we don't see the other cells as they slide behind it */
}

/* This is for cells inside the table that are not absolutely positioned. */
.bodyContent {
  position: relative;
  background-color: yellow; /* This is here just so that the example is easy to see */
  min-width: 100px; /* This is necessary so that the browser doesn't automatically resize the cell ' */
  max-width: 100px; /* This is necessary so that the browser doesn't automatically resize the cell ' */
  overflow: hidden; /* This is so that excess content doesn't bleed over into other cells. It obiously assumes that the content won't be bigger than this. */
}

/* This is for header row cells other than the 2 leftmost columns */ 
.headContent {
  border-top-width: 1px; /* This is only relevant for first row. */  
  margin-top: -1px; /* This compensates for the top border.*/ 
  background-color: white; /* This is needed so that we don't see the other cells as they slide behind it */
  z-index: 1; /* This is needed so that we don't see the other cells as they slide behind it */
  min-width: 100px; /* This is necessary so that the browser doesn't automatically resize the cell ' */
  max-width: 100px; /* This is necessary so that the browser doesn't automatically resize the cell ' */
  overflow: hidden; /* This is so that excess content doesn't bleed over into other cells. It obiously assumes that the content won't be bigger than this. */
}

/* These are for specific columns in the header */
.col0 {
 margin-left: 0px; /* starts the first non-frozen row to the left (3rd column)  */
}

.col1 {
 margin-left: 104px; /* should be equal to n * (cell width + cell borders) */
}

.col2 {
 margin-left: 208px; /* should be equal to n * (cell width + cell borders) */
}

.col3 {
 margin-left: 312px; /* should be equal to n * (cell width + cell borders) */
}

.col4 {
 margin-left: 416px; /* should be equal to n * (cell width + cell borders) */
}

.col5 {
 margin-left: 520px; /* should be equal to n * (cell width + cell borders) */
}

.col6 {
 margin-left: 624px; /* should be equal to n * (cell width + cell borders) */
}

.col7 {
 margin-left: 728px; /* should be equal to n * (cell width + cell borders) */
}

.col8 {
 margin-left: 832px; /* should be equal to n * (cell width + cell borders) */
}

***

Step 4. Wrap the table in a div so, that the overflow can scroll. I named this div "scrollingContent". Note the id tag, so that we can get the element from JavaScript. Also, note the onscroll command which will call a JavaScript function.

<html>
  <head>
    <title>Frozen Column Test</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  </head>
  
  <body>
    <div id="scrollingContent" class="scrollingContent" onscroll="moveCols();">
      <table>
        <tr><th class="leftHead1"><input type="checkbox"></th><th class="leftHead2">#</th><th class="headContent col0">Lorem Ipsum</th><th class="headContent col1">Lorem Ipsum</th><th class="headContent col2">Lorem Ipsum</th><th class="headContent col3">Lorem Ipsum</th><th class="headContent col4">Lorem Ipsum</th><th class="headContent col5">Lorem Ipsum</th><th class="headContent col6">Lorem Ipsum</th><th class="headContent col7">Lorem Ipsum</th><th class="headContent col8">Lorem Ipsum</th></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">1</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">2</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">3</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">4</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">5</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">6</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">7</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">8</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">9</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">10</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">11</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">12</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">13</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">14</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">15</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
      </table>
    </div>
  </body>
  
</html>

/* CSS */

/* wrapper around the table */
div.scrollingContent {
  width: 500px;
  overflow-x: scroll;
  margin-left: 67px;
  margin-top: 19px;
  overflow-y: scroll;
  padding: 0;
  max-height: 150px;
}

***

Step 5. Wrap the scrolling div in another div, so that we can hide (clip) the header rows when they slide out of view.
I named this div "wrapperBox", so that we can apply CSS to it. 

<html>
  <head>
    <title>Frozen Column Test</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  </head>
  
  <body>
    <div class="wrapperBox">
      <div id="scrollingContent" class="scrollingContent" onscroll="moveCols();">
        <table>
          <tr><th class="leftHead1"><input type="checkbox"></th><th class="leftHead2">#</th><th class="headContent col0">Lorem Ipsum</th><th class="headContent col1">Lorem Ipsum</th><th class="headContent col2">Lorem Ipsum</th><th class="headContent col3">Lorem Ipsum</th><th class="headContent col4">Lorem Ipsum</th><th class="headContent col5">Lorem Ipsum</th><th class="headContent col6">Lorem Ipsum</th><th class="headContent col7">Lorem Ipsum</th><th class="headContent col8">Lorem Ipsum</th></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">1</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">2</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">3</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">4</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">5</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">6</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">7</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">8</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">9</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">10</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">11</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">12</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">13</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">14</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
          <tr><td class="leftCol1"><input type="checkbox"></td><td class="leftCol2">15</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td><td class="bodyContent">Lorem Ipsum</td></tr>
        </table>
      </div>
    </div>
  </body>
  
</html>

/* CSS */

/* wrapper around the table for clipping absolutely positioned overflow */
div.wrapperBox {
  position: absolute;
  clip: rect(19px,566px,169px,22px); /* Adjust these values so that it exactly surrounds your table. */
  
}

***

Step 6. Add in the JavaScript. 
This code gets called when the user scrolls the table. 
The code reads the position of the scroll bars and then moves the absolutely positioned table cells appropriately.

<script type="text/javascript">

function moveCols()
{
  //MOVE THE LEFT COLUMNS
  var scrollingContentElement = document.getElementById("scrollingContent");
  var scrollPosition = scrollingContentElement.scrollTop;
  var scrollMax = scrollingContentElement.scrollHeight - scrollingContentElement.clientHeight;
  var percentScroll = scrollPosition / scrollMax;

  console.log("percentScroll for height == " + percentScroll);

  var leftColCells1;
  var leftColCells2;

  //read the table cells into an array
  leftColCells1 = document.getElementsByClassName("leftCol1");
  leftColCells2 = document.getElementsByClassName("leftCol2");

  //for each cell change its position based on the scroll amount
  for (i = 0; i < leftColCells1.length; i++) 
  {
    //Depending on where the scroll bar is, move the leftmost cells appropriately. 
    if(percentScroll < 0.12) //dev note: adjust this value based on testing
    {
      //This is needed because otherwise the top row of table body gets hidden behind the header.
      leftColCells1[i].style.marginTop = ((0 - (percentScroll * scrollMax)) + 20 + "px");
      leftColCells2[i].style.marginTop = ((0 - (percentScroll * scrollMax)) + 20 + "px");
    }
    else
    {
      leftColCells1[i].style.marginTop = ((0 - (percentScroll * scrollMax)) - 1 + "px");
      leftColCells2[i].style.marginTop = ((0 - (percentScroll * scrollMax)) - 1 + "px");
    }
  }

  //MOVE THE TOP COLUMNS
  var scrollingContentElement = document.getElementById("scrollingContent");
  var scrollPosition = scrollingContentElement.scrollLeft;
  var scrollMax = scrollingContentElement.scrollWidth - scrollingContentElement.clientWidth;
  var percentScroll = scrollPosition / scrollMax;

  console.log("percentScroll for width == " + percentScroll);

  var topRowCells;
  var topLeftHead1;
  var topLeftHead1;

  //read the table cells into an array
  topRowCells = document.getElementsByClassName("headContent");

  //for each cell change its position based on the scroll amount

  for (i = 0; i < topRowCells.length; i++) 
  {
    topRowCells[i].style.marginLeft = ((0 - (percentScroll * scrollMax)) + (i * 104) + "px");          
  }

}

</script>
