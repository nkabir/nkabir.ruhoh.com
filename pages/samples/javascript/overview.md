---
title: Overview
description: Overview of Javascript Samples
---

<section id="overview">

  <h3>Individual or compiled</h3>
  <p>If you have downloaded the latest version of Bootstrap, both <strong>bootstrap.js</strong> and <strong>bootstrap.min.js</strong> contain all of the plugins listed on this page.</p>

  <h3>Data attributes</h3>
  <p>You can use all Bootstrap plugins purely through the markup API without writing a single line of JavaScript. This is Bootstrap's first class API and should be your first consideration when using a plugin.</p>

  <p>That said, in some situations it may be desirable to turn this functionality off. Therefore, we also provide the ability to disable the data attribute API by unbinding all events on the body namespaced with `'data-api'`. This looks like this:
  <pre class="prettyprint linenums">$('body').off('.data-api')</pre>

  <p>Alternatively, to target a specific plugin, just include the plugins name as a namespace along with the data-api namespace like this:</p>
  <pre class="prettyprint linenums">$('body').off('.alert.data-api')</pre>

  <h3>Programmatic API</h3>
  <p>We also believe you should be able to use all Bootstrap plugins purely through the JavaScript API. All public APIs are single, chainable methods, and return the collection acted upon.</p>
  <pre class="prettyprint linenums">$(".btn.danger").button("toggle").addClass("fat")</pre>
  <p>All methods should accept an optional options object, a string which targets a particular method, or nothing (which initiates a plugin with default behavior):</p>
  
<pre class="prettyprint linenums">
    $("#myModal").modal()                       // initialized with defaults
    $("#myModal").modal({ keyboard: false })   // initialized with no keyboard
    $("#myModal").modal('show')                // initializes and invokes show immediately</p>
</pre>

  <p>Each plugin also exposes it's raw constructor on a `Constructor` property: <code>$.fn.popover.Constructor</code>. If you'd like to get a particular plugin instance, retrieve it directly from an element: <code>$('[rel=popover]').data('popover')</code>.</p>

  <h3>Events</h3>
  <p>Bootstrap provides custom events for most plugin's unique actions. Generally, these come in an infinitive and past participle form - where the infinitive (ex. <code>show</code>) is triggered at the start of an event, and it's past participle form (ex. <code>shown</code>) is trigger on the completion of an action.</p>
  <p>All infinitive events provide preventDefault functionality. This provides the abililty to stop the execution of an action before it starts.</p>
  
<pre class="prettyprint linenums">
    $('#myModal').on('show', function (e) {
        if (!data) return e.preventDefault() // stops modal from being shown
    })
</pre>

</section>
