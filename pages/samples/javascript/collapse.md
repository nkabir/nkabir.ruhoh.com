---
title: Javascript Collapse Samples
description: Sample Javascript Collapse
---

<section id="collapse">
    <h3>About</h3>
    <p>Get base styles and flexible support for collapsible components like accordions and navigation.</p>
    <p class="muted"><strong>*</strong> Requires the Transitions plugin to be included.</p>
    <h2>Example accordion</h2>
    <p>Using the collapse plugin, we built a simple accordion style widget:</p>
    <div class="bs-docs-example">
      <div class="accordion" id="accordion2">
        <div class="accordion-group">
          <div class="accordion-heading">
            <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseOne">
              Collapsible Group Item #1
            </a>
          </div>
          <div id="collapseOne" class="accordion-body collapse in">
            <div class="accordion-inner">
              Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
            </div>
          </div>
        </div>
        <div class="accordion-group">
          <div class="accordion-heading">
            <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseTwo">
              Collapsible Group Item #2
            </a>
          </div>
          <div id="collapseTwo" class="accordion-body collapse">
            <div class="accordion-inner">
              Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
            </div>
          </div>
        </div>
        <div class="accordion-group">
          <div class="accordion-heading">
            <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseThree">
              Collapsible Group Item #3
            </a>
          </div>
          <div id="collapseThree" class="accordion-body collapse">
            <div class="accordion-inner">
              Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
            </div>
          </div>
        </div>
      </div>
    </div>
<pre class="prettyprint linenums">
&lt;button type="button" class="btn btn-danger" data-toggle="collapse" data-target="#demo"&gt;
  simple collapsible
&lt;/button&gt;

&lt;div id="demo" class="collapse in"&gt; … &lt;/div&gt;
</pre>
    <hr class="bs-docs-separator">   
    <h2>Usage</h2>    
    <h3>Via data attributes</h3>
    <p>Just add <code>data-toggle="collapse"</code> and a <code>data-target</code> to element to automatically assign control of a collapsible element. The <code>data-target</code> attribute accepts a css selector to apply the collapse to. Be sure to add the class <code>collapse</code> to the collapsible element. If you'd like it to default open, add the additional class <code>in</code>.</p>
    <p>To add accordion-like group management to a collapsible control, add the data attribute <code>data-parent="#selector"</code>. Refer to the demo to see this in action.</p>    
    <h3>Via JavaScript</h3>
    <p>Enable manually with:</p>
    <pre class="prettyprint linenums">$(".collapse").collapse()</pre>    
    <h3>Options</h3>
    <p>Options can be passed via data attributes or JavaScript. For data attributes, append the option name to <code>data-</code>, as in <code>data-parent=""</code>.</p>
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
         <td>parent</td>
         <td>selector</td>
         <td>false</td>
         <td>If selector then all collapsible elements under the specified parent will be closed when this collapsible item is shown. (similar to traditional accordion behavior)</td>
       </tr>
       <tr>
         <td>toggle</td>
         <td>boolean</td>
         <td>true</td>
         <td>Toggles the collapsible element on invocation</td>
       </tr>
      </tbody>
    </table>  
    <h3>Methods</h3>
    <h4>.collapse(options)</h4>
    <p>Activates your content as a collapsible element. Accepts an optional options <code>object</code>.
<pre class="prettyprint linenums">
$('#myCollapsible').collapse({
  toggle: false
})
</pre>
    <h4>.collapse('toggle')</h4>
    <p>Toggles a collapsible element to shown or hidden.</p>
    <h4>.collapse('show')</h4>
    <p>Shows a collapsible element.</p>
    <h4>.collapse('hide')</h4>
    <p>Hides a collapsible element.</p>    
    <h3>Events</h3>
    <p>Bootstrap's collapse class exposes a few events for hooking into collapse functionality.</p>
    <table class="table table-bordered table-striped">
      <thead>
       <tr>
         <th style="width: 150px;">Event</th>
         <th>Description</th>
       </tr>
      </thead>
      <tbody>
       <tr>
         <td>show</td>
         <td>This event fires immediately when the <code>show</code> instance method is called.</td>
       </tr>
       <tr>
         <td>shown</td>
         <td>This event is fired when a collapse element has been made visible to the user (will wait for css transitions to complete).</td>
       </tr>
       <tr>
         <td>hide</td>
         <td>
          This event is fired immediately when the <code>hide</code> method has been called.
         </td>
       </tr>
       <tr>
         <td>hidden</td>
         <td>This event is fired when a collapse element has been hidden from the user (will wait for css transitions to complete).</td>
       </tr>
      </tbody>
    </table>
<pre class="prettyprint linenums">
$('#myCollapsible').on('hidden', function () {
  // do something…
})</pre>
</section>
