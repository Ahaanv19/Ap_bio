---
layout: base
title: Homepage
search_exclude: true
nav: true
hide: true
menu: nav/home.html
---


<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AP Biology Prep</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .navbar {
      display: flex;
      align-items: center;
      background-color: #004d40;
      padding: 10px 20px;
      border-radius: 8px;
    }

    .navbar img {
      height: 50px;
      margin-right: 20px;
    }

    .dropdown {
      position: relative;
      display: inline-block;
    }

    .dropbtn {
      background-color: #00796b;
      color: white;
      padding: 10px 15px;
      font-size: 16px;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    .dropdown-content {
      display: none;
      position: absolute;
      background-color: white;
      min-width: 180px;
      box-shadow: 0px 8px 16px rgba(0,0,0,0.2);
      z-index: 1;
      border-radius: 4px;
      overflow: hidden;
    }

    .dropdown-content a {
      color: #004d40;
      padding: 10px 14px;
      text-decoration: none;
      display: block;
      border-bottom: 1px solid #eee;
    }

    .dropdown-content a:hover {
      background-color: #f1f1f1;
    }

    .dropdown:hover .dropdown-content {
      display: block;
    }

    .dropdown:hover .dropbtn {
      background-color: #00695c;
    }
  </style>
</head>
<body>

  <h1>Welcome to AP Biology Prep</h1>
  <p>An interactive website with interactive lesson activites for students.</p>

  <div class="navbar">
  

    <div class="dropdown">
      <button class="dropbtn">Units</button>
      <div class="dropdown-content">
        <a href="{{site.baseurl}}/unitone/">Unit 1</a>
        <a href="{{site.baseurl}}/unittwo/">Unit 2</a>
        <a href="{{site.baseurl}}/unitthree/">Unit 3</a>
        <a href="{{site.baseurl}}/unitfour/">Unit 4</a>
        <a href="{{site.baseurl}}/unitfive/">Unit 5</a>
        <a href="{{site.baseurl}}/unitsix/">Unit 6</a>
        <a href="{{site.baseurl}}/unitseven/">Unit 7</a>
        <a href="{{site.baseurl}}/uniteight/">Unit 8</a>
        <a href="{{site.baseurl}}/examreview/">Exam Review</a>
      </div>
    </div>
  </div>

</body>
</html>
