---
title: Thumbnails Samples
description: Samples of Thumbnails
---

<section id="thumbnails">

  <h2>Default thumbnails</h2>
  <p>By default, Bootstrap's thumbnails are designed to showcase linked images with minimal required markup.</p>
  <div class="row-fluid">
    <ul class="thumbnails">
      <li class="span3">
        <a href="#" class="thumbnail">
          <img src="http://placehold.it/260x180" alt="">
        </a>
      </li>
      <li class="span3">
        <a href="#" class="thumbnail">
          <img src="http://placehold.it/260x180" alt="">
        </a>
      </li>
      <li class="span3">
        <a href="#" class="thumbnail">
          <img src="http://placehold.it/260x180" alt="">
        </a>
      </li>
      <li class="span3">
        <a href="#" class="thumbnail">
          <img src="http://placehold.it/260x180" alt="">
        </a>
      </li>
    </ul>
  </div>

  <h2>Highly customizable</h2>
  <p>With a bit of extra markup, it's possible to add any kind of HTML content like headings, paragraphs, or buttons into thumbnails.</p>
  <div class="row-fluid">
    <ul class="thumbnails">
      <li class="span4">
        <div class="thumbnail">
          <img src="http://placehold.it/300x200" alt="">
          <div class="caption">
            <h3>Thumbnail label</h3>
            <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            <p><a href="#" class="btn btn-primary">Action</a> <a href="#" class="btn">Action</a></p>
          </div>
        </div>
      </li>
      <li class="span4">
        <div class="thumbnail">
          <img src="http://placehold.it/300x200" alt="">
          <div class="caption">
            <h3>Thumbnail label</h3>
            <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            <p><a href="#" class="btn btn-primary">Action</a> <a href="#" class="btn">Action</a></p>
          </div>
        </div>
      </li>
      <li class="span4">
        <div class="thumbnail">
          <img src="http://placehold.it/300x200" alt="">
          <div class="caption">
            <h3>Thumbnail label</h3>
            <p>Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
            <p><a href="#" class="btn btn-primary">Action</a> <a href="#" class="btn">Action</a></p>
          </div>
        </div>
      </li>
    </ul>
  </div>

  <h3>Why use thumbnails</h3>
  <p>Thumbnails (previously <code>.media-grid</code> up until v1.4) are great for grids of photos or videos, image search results, retail products, portfolios, and much more. They can be links or static content.</p>

  <h3>Simple, flexible markup</h3>
  <p>Thumbnail markup is simple&mdash;a <code>ul</code> with any number of <code>li</code> elements is all that is required. It's also super flexible, allowing for any type of content with just a bit more markup to wrap your contents.</p>

  <h3>Uses grid column sizes</h3>
  <p>Lastly, the thumbnails component uses existing grid system classes&mdash;like <code>.span2</code> or <code>.span3</code>&mdash;for control of thumbnail dimensions.</p>

  <h2>Markup</h2>
  <p>As mentioned previously, the required markup for thumbnails is light and straightforward. Here's a look at the default setup <strong>for linked images</strong>:</p>
  
<pre class="prettyprint linenums">
    &lt;ul class="thumbnails"&gt;
      &lt;li class="span4"&gt;
        &lt;a href="#" class="thumbnail"&gt;
          &lt;img src="http://placehold.it/300x200" alt=""&gt;
        &lt;/a&gt;
      &lt;/li&gt;
      ...
    &lt;/ul&gt;
</pre>

  <p>For custom HTML content in thumbnails, the markup changes slightly. To allow block level content anywhere, we swap the <code>&lt;a&gt;</code> for a <code>&lt;div&gt;</code> like so:</p>
          
<pre class="prettyprint linenums">
    &lt;ul class="thumbnails"&gt;
      &lt;li class="span4"&gt;
        &lt;div class="thumbnail"&gt;
          &lt;img src="http://placehold.it/300x200" alt=""&gt;
          &lt;h3&gt;Thumbnail label&lt;/h3&gt;
          &lt;p&gt;Thumbnail caption...&lt;/p&gt;
        &lt;/div&gt;
      &lt;/li&gt;
      ...
    &lt;/ul&gt;
</pre>

  <h2>More examples</h2>
  <p>Explore all your options with the various grid classes available to you. You can also mix and match different sizes.</p>
  <ul class="thumbnails">
    <li class="span4">
      <a href="#" class="thumbnail">
        <img src="http://placehold.it/360x270" alt="">
      </a>
    </li>
    <li class="span3">
      <a href="#" class="thumbnail">
        <img src="http://placehold.it/260x120" alt="">
      </a>
    </li>
    <li class="span2">
      <a href="#" class="thumbnail">
        <img src="http://placehold.it/160x120" alt="">
      </a>
    </li>
    <li class="span3">
      <a href="#" class="thumbnail">
        <img src="http://placehold.it/260x120" alt="">
      </a>
    </li>
    <li class="span2">
      <a href="#" class="thumbnail">
        <img src="http://placehold.it/160x120" alt="">
      </a>
    </li>
  </ul>

</section>