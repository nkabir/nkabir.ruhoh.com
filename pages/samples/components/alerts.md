---
title: Alerts Samples
description: Samples of Alerts
---

<section id="alerts">

  <h2>Default alert</h2>
  <p>Wrap any text and an optional dismiss button in <code>.alert</code> for a basic warning alert message.</p>
  <div class="bs-docs-example">
    <div class="alert">
      <button type="button" class="close" data-dismiss="alert">&times;</button>
      <strong>Warning!</strong> Best check yo self, you're not looking too good.
    </div>
  </div>
          
<pre class="prettyprint linenums">
    &lt;div class="alert"&gt;
      &lt;button type="button" class="close" data-dismiss="alert"&gt;&times;&lt;/button&gt;
      &lt;strong&gt;Warning!&lt;/strong&gt; Best check yo self, you're not looking too good.
    &lt;/div&gt;
</pre>

  <h3>Dismiss buttons</h3>
  <p>Mobile Safari and Mobile Opera browsers, in addition to the <code>data-dismiss="alert"</code> attribute, require an <code>href="#"</code> for the dismissal of alerts when using an <code>&lt;a&gt;</code> tag.</p>
  <pre class="prettyprint linenums">&lt;a href="#" class="close" data-dismiss="alert"&gt;&times;&lt;/button&gt;</pre>
  <p>Alternatively, you may use a <code>&lt;button&gt;</code> element with the data attribute, which we have opted to do for our docs. When using <code>&lt;button&gt;</code>, you must include <code>type="button"</code> or your forms may not submit.</p>
  <pre class="prettyprint linenums">&lt;button type="button" class="close" data-dismiss="alert"&gt;&times;&lt;/button&gt;</pre>

  <h3>Dismiss alerts via javascript</h3>
  <p>Use the <a href="./javascript.html#alerts">alerts jQuery plugin</a> for quick and easy dismissal of alerts.</p>


  <hr class="bs-docs-separator">


  <h2>Options</h2>
  <p>For longer messages, increase the padding on the top and bottom of the alert wrapper by adding <code>.alert-block</code>.</p>
  <div class="bs-docs-example">
    <div class="alert alert-block">
      <button type="button" class="close" data-dismiss="alert">&times;</button>
      <h4>Warning!</h4>
      <p>Best check yo self, you're not looking too good. Nulla vitae elit libero, a pharetra augue. Praesent commodo cursus magna, vel scelerisque nisl consectetur et.</p>
    </div>
  </div>
  
<pre class="prettyprint linenums">
    &lt;div class="alert alert-block"&gt;
      &lt;button type="button" class="close" data-dismiss="alert"&gt;&times;&lt;/button&gt;
      &lt;h4&gt;Warning!&lt;/h4&gt;
      Best check yo self, you're not...
    &lt;/div&gt;
</pre>


  <hr class="bs-docs-separator">


  <h2>Contextual alternatives</h2>
  <p>Add optional classes to change an alert's connotation.</p>

  <h3>Error or danger</h3>
  <div class="bs-docs-example">
    <div class="alert alert-error">
      <button type="button" class="close" data-dismiss="alert">&times;</button>
      <strong>Oh snap!</strong> Change a few things up and try submitting again.
    </div>
  </div>
          
<pre class="prettyprint linenums">
    &lt;div class="alert alert-error"&gt;
      ...
    &lt;/div&gt;
</pre>

  <h3>Success</h3>
  <div class="bs-docs-example">
    <div class="alert alert-success">
      <button type="button" class="close" data-dismiss="alert">&times;</button>
      <strong>Well done!</strong> You successfully read this important alert message.
    </div>
  </div>
  
<pre class="prettyprint linenums">
    &lt;div class="alert alert-success"&gt;
      ...
    &lt;/div&gt;
</pre>

  <h3>Information</h3>
  <div class="bs-docs-example">
    <div class="alert alert-info">
      <button type="button" class="close" data-dismiss="alert">&times;</button>
      <strong>Heads up!</strong> This alert needs your attention, but it's not super important.
    </div>
  </div>
  
<pre class="prettyprint linenums">
    &lt;div class="alert alert-info"&gt;
      ...
    &lt;/div&gt;
</pre>

</section>

