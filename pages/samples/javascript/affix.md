---
title: Javascript Affix
description: Sample Javascript Affix
---

<section id="affix">
    <h2>Example</h2>
    <p>The subnavigation on the left is a live demo of the affix plugin.</p>
    <hr class="bs-docs-separator">
    <h2>Usage</h2>
    <h3>Via data attributes</h3>
    <p>To easily add affix behavior to any element, just add <code>data-spy="affix"</code> to the element you want to spy on. Then use offsets to define when to toggle the pinning of an element on and off.</p>
    <pre class="prettyprint linenums">&lt;div data-spy="affix" data-offset-top="200"&gt;...&lt;/body&gt;</pre>
    <div class="alert alert-info">
      <strong>Heads up!</strong>
      It's up to you to manage the position of a pinned element. This is done by styling <code>affix</code>, <code>affix-top</code>, and <code>affix-bottom</code>.
    </div>
    <h3>Via JavaScript</h3>
    <p>Call the affix plugin via JavaScript:</p>
    <pre class="prettyprint linenums">$('#navbar').affix()</pre>
    <h3>Methods</h3>
    <h4>.affix('refresh')</h4>
    <p>When using affix in conjunction with adding or removing of elements from the DOM, you'll want to call the refresh method:</p>
<pre class="prettyprint linenums">
$('[data-spy="affix"]').each(function () {
  $(this).affix('refresh')
});
</pre>
  <h3>Options</h3>
  <p>Options can be passed via data attributes or JavaScript. For data attributes, append the option name to <code>data-</code>, as in <code>data-offset-top="200"</code>.</p>
  <table class="table table-bordered table-striped">
    <thead>
     <tr>
       <th style="width: 100px;">Name</th>
       <th style="width: 100px;">type</th>
       <th style="width: 50px;">default</th>
       <th>description</th>
     </tr>
    </thead>
    <tbody>
     <tr>
       <td>offset</td>
       <td>number | function | object</td>
       <td>10</td>
       <td>Pixels to offset from screen when calculating position of scroll. If a single number is provide, the offset will be applied in both top and left directions. To listen for a single direction, or multiple unique offsets, just provided an object <code>offset: { x: 10 }</code>. Use a function when you need to dynamically provide an offset (useful for some responsive designs).</td>
     </tr>
    </tbody>
  </table>
</section>
