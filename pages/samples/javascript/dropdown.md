---
title: Dropdown Samples
description: Dropdown Samples
---

<section id="dropdowns">
  <h2>Examples</h2>
  <p>Add dropdown menus to nearly anything with this simple plugin, including the navbar, tabs, and pills.</p>
  <h3>Within a navbar</h3>
  <div class="bs-docs-example">
    <div id="navbar-example" class="navbar navbar-static">
      <div class="navbar-inner">
        <div class="container" style="width: auto;">
          <a class="brand" href="#">Project Name</a>
          <ul class="nav" role="navigation">
            <li class="dropdown">
              <a id="drop1" href="#" role="button" class="dropdown-toggle" data-toggle="dropdown">Dropdown <b class="caret"></b></a>
              <ul class="dropdown-menu" role="menu" aria-labelledby="drop1">
                <li><a tabindex="-1" href="http://google.com">Action</a></li>
                <li><a tabindex="-1" href="#anotherAction">Another action</a></li>
                <li><a tabindex="-1" href="#">Something else here</a></li>
                <li class="divider"></li>
                <li><a tabindex="-1" href="#">Separated link</a></li>
              </ul>
            </li>
            <li class="dropdown">
              <a href="#" id="drop2" role="button" class="dropdown-toggle" data-toggle="dropdown">Dropdown 2 <b class="caret"></b></a>
              <ul class="dropdown-menu" role="menu" aria-labelledby="drop2">
                <li><a tabindex="-1" href="#">Action</a></li>
                <li><a tabindex="-1" href="#">Another action</a></li>
                <li><a tabindex="-1" href="#">Something else here</a></li>
                <li class="divider"></li>
                <li><a tabindex="-1" href="#">Separated link</a></li>
              </ul>
            </li>
          </ul>
          <ul class="nav pull-right">
            <li id="fat-menu" class="dropdown">
              <a href="#" id="drop3" role="button" class="dropdown-toggle" data-toggle="dropdown">Dropdown 3 <b class="caret"></b></a>
              <ul class="dropdown-menu" role="menu" aria-labelledby="drop3">
                <li><a tabindex="-1" href="#">Action</a></li>
                <li><a tabindex="-1" href="#">Another action</a></li>
                <li><a tabindex="-1" href="#">Something else here</a></li>
                <li class="divider"></li>
                <li><a tabindex="-1" href="#">Separated link</a></li>
              </ul>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div> 
  <h3>Within tabs</h3>
  <div class="bs-docs-example">
    <ul class="nav nav-pills">
      <li class="active"><a href="#">Regular link</a></li>
      <li class="dropdown">
        <a class="dropdown-toggle" id="drop4" role="button" data-toggle="dropdown" href="#">Dropdown <b class="caret"></b></a>
        <ul id="menu1" class="dropdown-menu" role="menu" aria-labelledby="drop4">
          <li><a tabindex="-1" href="#">Action</a></li>
          <li><a tabindex="-1" href="#">Another action</a></li>
          <li><a tabindex="-1" href="#">Something else here</a></li>
          <li class="divider"></li>
          <li><a tabindex="-1" href="#">Separated link</a></li>
        </ul>
      </li>
      <li class="dropdown">
        <a class="dropdown-toggle" id="drop5" role="button" data-toggle="dropdown" href="#">Dropdown 2 <b class="caret"></b></a>
        <ul id="menu2" class="dropdown-menu" role="menu" aria-labelledby="drop5">
          <li><a tabindex="-1" href="#">Action</a></li>
          <li><a tabindex="-1" href="#">Another action</a></li>
          <li><a tabindex="-1" href="#">Something else here</a></li>
          <li class="divider"></li>
          <li><a tabindex="-1" href="#">Separated link</a></li>
        </ul>
      </li>
      <li class="dropdown">
        <a class="dropdown-toggle" id="drop5" role="button" data-toggle="dropdown" href="#">Dropdown 3 <b class="caret"></b></a>
        <ul id="menu3" class="dropdown-menu" role="menu" aria-labelledby="drop5">
          <li><a tabindex="-1" href="#">Action</a></li>
          <li><a tabindex="-1" href="#">Another action</a></li>
          <li><a tabindex="-1" href="#">Something else here</a></li>
          <li class="divider"></li>
          <li><a tabindex="-1" href="#">Separated link</a></li>
        </ul>
      </li>
    </ul>
  </div> 
  <hr class="bs-docs-separator">
  <h2>Usage</h2>
  <h3>Via data attributes</h3>
  <p>Add <code>data-toggle="dropdown"</code> to a link or button to toggle a dropdown.</p>
          
<pre class="prettyprint linenums">
    &lt;div class="dropdown"&gt;
      &lt;a class="dropdown-toggle" href="#"&gt;Dropdown trigger&lt;/a&gt;
      &lt;ul class="dropdown-menu" role="menu" aria-labelledby="dLabel"&gt;
        ...
      &lt;/ul&gt;
    &lt;/div&gt;
</pre>
  <p>To keep URLs intact, use the <code>data-target</code> attribute instead of <code>href="#"</code>.</p>          
<pre class="prettyprint linenums">
    &lt;div class="dropdown"&gt;
      &lt;a class="dropdown-toggle" id="dLabel" role="button" data-toggle="dropdown" data-target="#" href="/page.html"&gt;
        Dropdown
        &lt;b class="caret"&gt;&lt;/b&gt;
      &lt;/a&gt;
      &lt;ul class="dropdown-menu" role="menu" aria-labelledby="dLabel"&gt;
        ...
      &lt;/ul&gt;
    &lt;/div&gt;
</pre>

  <h3>Via JavaScript</h3>
  <p>Call the dropdowns via JavaScript:</p>
  <pre class="prettyprint linenums">$('.dropdown-toggle').dropdown()</pre>
  <h3>Options</h3>
  <p><em>None</em></p>
  <h3>Methods</h3>
  <h4>$().dropdown()</h4>
  <p>A programatic api for activating menus for a given navbar or tabbed navigation.</p>
</section>