---
title: Popovers Samples
description: Popover Samples
---

<section id="popovers">
    <h2>Examples</h2>
    <p>Add small overlays of content, like those on the iPad, to any element for housing secondary information. Hover over the button to trigger the popover. <strong>Requires <a href="#tooltips">Tooltip</a> to be included.</strong></p>
    <h3>Static popover</h3>
    <p>Four options are available: top, right, bottom, and left aligned.</p>
    <div class="bs-docs-example bs-docs-example-popover">
      <div class="popover top">
        <div class="arrow"></div>
        <h3 class="popover-title">Popover top</h3>
        <div class="popover-content">
          <p>Sed posuere consectetur est at lobortis. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.</p>
        </div>
      </div>
      <div class="popover right">
        <div class="arrow"></div>
        <h3 class="popover-title">Popover right</h3>
        <div class="popover-content">
          <p>Sed posuere consectetur est at lobortis. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.</p>
        </div>
      </div>    
      <div class="popover bottom">
        <div class="arrow"></div>
        <h3 class="popover-title">Popover bottom</h3>
        <div class="popover-content">
          <p>Sed posuere consectetur est at lobortis. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.</p>
        </div>
      </div>
      <div class="popover left">
        <div class="arrow"></div>
        <h3 class="popover-title">Popover left</h3>
        <div class="popover-content">
          <p>Sed posuere consectetur est at lobortis. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.</p>
        </div>
      </div>   
      <div class="clearfix"></div>
    </div>
    <p>No markup shown as popovers are generated from JavaScript and content within a <code>data</code> attribute.</p>    
    <h3>Live demo</h3>
    <div class="bs-docs-example" style="padding-bottom: 24px;">
      <a href="#" class="btn btn-large btn-danger" rel="popover" title="A Title" data-content="And here's some amazing content. It's very engaging. right?">Click to toggle popover</a>
    </div>
    <hr class="bs-docs-separator">        
    <h2>Usage</h2>
    <p>Enable popovers via JavaScript:</p>
    <pre class="prettyprint linenums">$('#example').popover(options)</pre>    
    <h3>Options</h3>
    <p>Options can be passed via data attributes or JavaScript. For data attributes, append the option name to <code>data-</code>, as in <code>data-animation=""</code>.</p>
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
         <td>animation</td>
         <td>boolean</td>
         <td>true</td>
         <td>apply a css fade transition to the tooltip</td>
       </tr>
       <tr>
         <td>html</td>
         <td>boolean</td>
         <td>true</td>
         <td>Insert html into the popover. If false, jquery's <code>text</code> method will be used to insert content into the dom. Use text if you're worried about XSS attacks.</td>
       </tr>
       <tr>
         <td>placement</td>
         <td>string|function</td>
         <td>'right'</td>
         <td>how to position the popover - top | bottom | left | right</td>
       </tr>
       <tr>
         <td>selector</td>
         <td>string</td>
         <td>false</td>
         <td>if a selector is provided, tooltip objects will be delegated to the specified targets</td>
       </tr>
       <tr>
         <td>trigger</td>
         <td>string</td>
         <td>'click'</td>
         <td>how popover is triggered - click | hover | focus | manual</td>
       </tr>
       <tr>
         <td>title</td>
         <td>string | function</td>
         <td>''</td>
         <td>default title value if `title` attribute isn't present</td>
       </tr>
       <tr>
         <td>content</td>
         <td>string | function</td>
         <td>''</td>
         <td>default content value if `data-content` attribute isn't present</td>
       </tr>
       <tr>
         <td>delay</td>
         <td>number | object</td>
         <td>0</td>
         <td>
          <p>delay showing and hiding the popover (ms) - does not apply to manual trigger type</p>
          <p>If a number is supplied, delay is applied to both hide/show</p>
          <p>Object structure is: <code>delay: { show: 500, hide: 100 }</code></p>
         </td>
       </tr>
      </tbody>
    </table>
    <div class="alert alert-info">
      <strong>Heads up!</strong>
      Options for individual popovers can alternatively be specified through the use of data attributes.
    </div>   
    <h3>Markup</h3>
    <p>For performance reasons, the Tooltip and Popover data-apis are opt in. If you would like to use them just specify a selector option.</p>   
    <h3>Methods</h3>
    <h4>$().popover(options)</h4>
    <p>Initializes popovers for an element collection.</p>
    <h4>.popover('show')</h4>
    <p>Reveals an elements popover.</p>
    <pre class="prettyprint linenums">$('#element').popover('show')</pre>
    <h4>.popover('hide')</h4>
    <p>Hides an elements popover.</p>
    <pre class="prettyprint linenums">$('#element').popover('hide')</pre>
    <h4>.popover('toggle')</h4>
    <p>Toggles an elements popover.</p>
    <pre class="prettyprint linenums">$('#element').popover('toggle')</pre>
    <h4>.popover('destroy')</h4>
    <p>Hides and destroys an element's popover.</p>
    <pre class="prettyprint linenums">$('#element').popover('destroy')</pre>
</section>

