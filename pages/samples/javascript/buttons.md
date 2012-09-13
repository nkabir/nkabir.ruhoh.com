---
title: Javascript Buttons Samples
description: Samples Javascript Buttons
---

<section id="buttons">
    <h2>Example uses</h2>
    <p>Do more with buttons. Control button states or create groups of buttons for more components like toolbars.</p>
    <h4>Stateful</h4>
    <p>Add data-loading-text="Loading..." to use a loading state on a button.</p>
    <div class="bs-docs-example" style="padding-bottom: 24px;">
      <button type="button" id="fat-btn" data-loading-text="loading..." class="btn btn-primary">
        Loading state
      </button>
    </div>
    <pre class="prettyprint linenums">&lt;button type="button" class="btn btn-primary" data-loading-text="Loading..."&gt;Loading state&lt;/button&gt;</pre>
    <h4>Single toggle</h4>
    <p>Add data-toggle="button" to activate toggling on a single button.</p>
    <div class="bs-docs-example" style="padding-bottom: 24px;">
      <button type="button" class="btn btn-primary" data-toggle="button">Single Toggle</button>
    </div>
    <pre class="prettyprint linenums">&lt;button type="button" class="btn" data-toggle="button"&gt;Single Toggle&lt;/button&gt;</pre>
    <h4>Checkbox</h4>
    <p>Add data-toggle="buttons-checkbox" for checkbox style toggling on btn-group.</p>
    <div class="bs-docs-example" style="padding-bottom: 24px;">
      <div class="btn-group" data-toggle="buttons-checkbox">
        <button type="button" class="btn btn-primary">Left</button>
        <button type="button" class="btn btn-primary">Middle</button>
        <button type="button" class="btn btn-primary">Right</button>
      </div>
    </div>
<pre class="prettyprint linenums">
&lt;div class="btn-group" data-toggle="buttons-checkbox"&gt;
  &lt;button type="button" class="btn"&gt;Left&lt;/button&gt;
  &lt;button type="button" class="btn"&gt;Middle&lt;/button&gt;
  &lt;button type="button" class="btn"&gt;Right&lt;/button&gt;
&lt;/div&gt;
</pre>
    <h4>Radio</h4>
    <p>Add data-toggle="buttons-radio" for radio style toggling on btn-group.</p>
    <div class="bs-docs-example" style="padding-bottom: 24px;">
      <div class="btn-group" data-toggle="buttons-radio">
        <button type="button" class="btn btn-primary">Left</button>
        <button type="button" class="btn btn-primary">Middle</button>
        <button type="button" class="btn btn-primary">Right</button>
      </div>
    </div>
<pre class="prettyprint linenums">
&lt;div class="btn-group" data-toggle="buttons-radio"&gt;
  &lt;button type="button" class="btn"&gt;Left&lt;/button&gt;
  &lt;button type="button" class="btn"&gt;Middle&lt;/button&gt;
  &lt;button type="button" class="btn"&gt;Right&lt;/button&gt;
&lt;/div&gt;
</pre>
    <hr class="bs-docs-separator">
    <h2>Usage</h2>
    <p>Enable buttons via JavaScript:</p>
    <pre class="prettyprint linenums">$('.nav-tabs').button()</pre>
    <h3>Markup</h3>
    <p>Data attributes are integral to the button plugin. Check out the example code below for the various markup types.</p>
    <h3>Options</h3>
    <p><em>None</em></p>
    <h3>Methods</h3>
    <h4>$().button('toggle')</h4>
    <p>Toggles push state. Gives the button the appearance that it has been activated.</p>
    <div class="alert alert-info">
      <strong>Heads up!</strong>
      You can enable auto toggling of a button by using the <code>data-toggle</code> attribute.
    </div>
    <pre class="prettyprint linenums">&lt;button type="button" class="btn" data-toggle="button" &gt;…&lt;/button&gt;</pre>
    <h4>$().button('loading')</h4>
    <p>Sets button state to loading - disables button and swaps text to loading text. Loading text should be defined on the button element using the data attribute <code>data-loading-text</code>.
    </p>
    <pre class="prettyprint linenums">&lt;button type="button" class="btn" data-loading-text="loading stuff..." &gt;...&lt;/button&gt;</pre>
    <div class="alert alert-info">
      <strong>Heads up!</strong>
      <a href="https://github.com/twitter/bootstrap/issues/793">Firefox persists the disabled state across page loads</a>. A workaround for this is to use <code>autocomplete="off"</code>.
    </div>
    <h4>$().button('reset')</h4>
    <p>Resets button state - swaps text to original text.</p>
    <h4>$().button(string)</h4>
    <p>Resets button state - swaps text to any data defined text state.</p>
<pre class="prettyprint linenums">&lt;button type="button" class="btn" data-complete-text="finished!" &gt;...&lt;/button&gt;
&lt;script&gt;
  $('.btn').button('complete')
&lt;/script&gt;
</pre>
</section>
