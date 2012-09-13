---
title: Javascript Carousel Samples
description: Sample Javascript Carousel
---

<section id="carousel">
    <h2>Example carousel</h2>
    <p>The slideshow below shows a generic plugin and component for cycling through elements like a carousel.</p>
    <div class="bs-docs-example">
      <div id="myCarousel" class="carousel slide">
        <div class="carousel-inner">
          <div class="item active">
            <img src="{{urls.theme_media}}/bootstrap-mdo-sfmoma-01.jpg" alt="">
            <div class="carousel-caption">
              <h4>First Thumbnail label</h4>
              <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            </div>
          </div>
          <div class="item">
            <img src="{{urls.theme_media}}/bootstrap-mdo-sfmoma-02.jpg" alt="">
            <div class="carousel-caption">
              <h4>Second Thumbnail label</h4>
              <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            </div>
          </div>
          <div class="item">
            <img src="{{urls.theme_media}}/bootstrap-mdo-sfmoma-03.jpg" alt="">
            <div class="carousel-caption">
              <h4>Third Thumbnail label</h4>
              <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            </div>
          </div>
        </div>
        <a class="left carousel-control" href="#myCarousel" data-slide="prev">&lsaquo;</a>
        <a class="right carousel-control" href="#myCarousel" data-slide="next">&rsaquo;</a>
      </div>
    </div>
<pre class="prettyprint linenums">
&lt;div id="myCarousel" class="carousel slide"&gt;
  &lt;!-- Carousel items --&gt;
  &lt;div class="carousel-inner"&gt;
    &lt;div class="active item"&gt;…&lt;/div&gt;
    &lt;div class="item"&gt;…&lt;/div&gt;
    &lt;div class="item"&gt;…&lt;/div&gt;
  &lt;/div&gt;
  &lt;!-- Carousel nav --&gt;
  &lt;a class="carousel-control left" href="#myCarousel" data-slide="prev"&gt;&amp;lsaquo;&lt;/a&gt;
  &lt;a class="carousel-control right" href="#myCarousel" data-slide="next"&gt;&amp;rsaquo;&lt;/a&gt;
&lt;/div&gt;
</pre>
<div class="alert alert-warning">
  <strong>Heads up!</strong>
  When implementing this carousel, remove the images we have provided and replace them with your own.
</div>
<hr class="bs-docs-separator">
<h2>Usage</h2>
<h3>Via data attributes</h3>
<p>...</p>
<h3>Via JavaScript</h3>
<p>Call carousel manually with:</p>
<pre class="prettyprint linenums">$('.carousel').carousel()</pre>
<h3>Options</h3>
<p>Options can be passed via data attributes or JavaScript. For data attributes, append the option name to <code>data-</code>, as in <code>data-interval=""</code>.</p>
<table class="table table-bordered table-striped">
  <thead>
   <tr>
     <th style="width: 100px;">Name</th>
     <th style="width: 50px;">type</th>
     <th style="width: 50px;">default</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   <tr>
     <td>interval</td>
     <td>number</td>
     <td>5000</td>
     <td>The amount of time to delay between automatically cycling an item. If false, carousel will not automatically cycle.</td>
   </tr>
   <tr>
     <td>pause</td>
     <td>string</td>
     <td>"hover"</td>
     <td>Pauses the cycling of the carousel on mouseenter and resumes the cycling of the carousel on mouseleave.</td>
   </tr>
  </tbody>
</table>
<h3>Methods</h3>
<h4>.carousel(options)</h4>
<p>Initializes the carousel with an optional options <code>object</code> and starts cycling through items.</p>
<pre class="prettyprint linenums">
$('.carousel').carousel({
  interval: 2000
})
</pre>
    <h4>.carousel('cycle')</h4>
    <p>Cycles through the carousel items from left to right.</p>
    <h4>.carousel('pause')</h4>
    <p>Stops the carousel from cycling through items.</p>
    <h4>.carousel(number)</h4>
    <p>Cycles the carousel to a particular frame (0 based, similar to an array).</p>
    <h4>.carousel('prev')</h4>
    <p>Cycles to the previous item.</p>
    <h4>.carousel('next')</h4>
    <p>Cycles to the next item.</p>
    <h3>Events</h3>
    <p>Bootstrap's carousel class exposes two events for hooking into carousel functionality.</p>
    <table class="table table-bordered table-striped">
      <thead>
       <tr>
         <th style="width: 150px;">Event</th>
         <th>Description</th>
       </tr>
      </thead>
      <tbody>
       <tr>
         <td>slide</td>
         <td>This event fires immediately when the <code>slide</code> instance method is invoked.</td>
       </tr>
       <tr>
         <td>slid</td>
         <td>This event is fired when the carousel has completed its slide transition.</td>
       </tr>
      </tbody>
    </table>
</section>

