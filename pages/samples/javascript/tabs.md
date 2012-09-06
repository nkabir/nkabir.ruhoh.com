---
title: Tabs
description: Tabs Samples

---

<section id="tabs">
  <h2>Example tabs</h2>
  <p>Add quick, dynamic tab functionality to transiton through panes of local content, even via dropdown menus.</p>
  <div class="bs-docs-example">
    <ul id="myTab" class="nav nav-tabs">
      <li class="active"><a href="#home" data-toggle="tab">Home</a></li>
      <li><a href="#profile" data-toggle="tab">Profile</a></li>
      <li class="dropdown">
        <a href="#" class="dropdown-toggle" data-toggle="dropdown">Dropdown <b class="caret"></b></a>
        <ul class="dropdown-menu">
          <li><a href="#dropdown1" data-toggle="tab">@fat</a></li>
          <li><a href="#dropdown2" data-toggle="tab">@mdo</a></li>
        </ul>
      </li>
    </ul>
    <div id="myTabContent" class="tab-content">
      <div class="tab-pane fade in active" id="home">
        <p>Raw denim you probably haven't heard of them jean shorts Austin. Nesciunt tofu stumptown aliqua, retro synth master cleanse. Mustache cliche tempor, williamsburg carles vegan helvetica. Reprehenderit butcher retro keffiyeh dreamcatcher synth. Cosby sweater eu banh mi, qui irure terry richardson ex squid. Aliquip placeat salvia cillum iphone. Seitan aliquip quis cardigan american apparel, butcher voluptate nisi qui.</p>
      </div>
      <div class="tab-pane fade" id="profile">
        <p>Food truck fixie locavore, accusamus mcsweeney's marfa nulla single-origin coffee squid. Exercitation +1 labore velit, blog sartorial PBR leggings next level wes anderson artisan four loko farm-to-table craft beer twee. Qui photo booth letterpress, commodo enim craft beer mlkshk aliquip jean shorts ullamco ad vinyl cillum PBR. Homo nostrud organic, assumenda labore aesthetic magna delectus mollit. Keytar helvetica VHS salvia yr, vero magna velit sapiente labore stumptown. Vegan fanny pack odio cillum wes anderson 8-bit, sustainable jean shorts beard ut DIY ethical culpa terry richardson biodiesel. Art party scenester stumptown, tumblr butcher vero sint qui sapiente accusamus tattooed echo park.</p>
      </div>
      <div class="tab-pane fade" id="dropdown1">
        <p>Etsy mixtape wayfarers, ethical wes anderson tofu before they sold out mcsweeney's organic lomo retro fanny pack lo-fi farm-to-table readymade. Messenger bag gentrify pitchfork tattooed craft beer, iphone skateboard locavore carles etsy salvia banksy hoodie helvetica. DIY synth PBR banksy irony. Leggings gentrify squid 8-bit cred pitchfork. Williamsburg banh mi whatever gluten-free, carles pitchfork biodiesel fixie etsy retro mlkshk vice blog. Scenester cred you probably haven't heard of them, vinyl craft beer blog stumptown. Pitchfork sustainable tofu synth chambray yr.</p>
      </div>
      <div class="tab-pane fade" id="dropdown2">
        <p>Trust fund seitan letterpress, keytar raw denim keffiyeh etsy art party before they sold out master cleanse gluten-free squid scenester freegan cosby sweater. Fanny pack portland seitan DIY, art party locavore wolf cliche high life echo park Austin. Cred vinyl keffiyeh DIY salvia PBR, banh mi before they sold out farm-to-table VHS viral locavore cosby sweater. Lomo wolf viral, mustache readymade thundercats keffiyeh craft beer marfa ethical. Wolf salvia freegan, sartorial keffiyeh echo park vegan.</p>
      </div>
    </div>
  </div>
  <hr class="bs-docs-separator">
  <h2>Usage</h2>
  <p>Enable tabbable tabs via JavaScript (each tab needs to be activated individually):</p>
  
<pre class="prettyprint linenums">
$('#myTab a').click(function (e) {
  e.preventDefault();
  $(this).tab('show');
})</pre>
  <p>You can activate individual tabs in several ways:</p>
<pre class="prettyprint linenums">
$('#myTab a[href="#profile"]').tab('show'); // Select tab by name
$('#myTab a:first').tab('show'); // Select first tab
$('#myTab a:last').tab('show'); // Select last tab
$('#myTab li:eq(2) a').tab('show'); // Select third tab (0-indexed)
</pre>
  <h3>Markup</h3>
  <p>You can activate a tab or pill navigation without writing any JavaScript by simply specifying <code>data-toggle="tab"</code> or <code>data-toggle="pill"</code> on an element. Adding the <code>nav</code> and <code>nav-tabs</code> classes to the tab <code>ul</code> will apply the Bootstrap tab styling.</p>
<pre class="prettyprint linenums">
&lt;ul class="nav nav-tabs"&gt;
  &lt;li&gt;&lt;a href="#home" data-toggle="tab"&gt;Home&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#profile" data-toggle="tab"&gt;Profile&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#messages" data-toggle="tab"&gt;Messages&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#settings" data-toggle="tab"&gt;Settings&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;</pre>
  <h3>Methods</h3>
  <h4>$().tab</h4>
  <p>
    Activates a tab element and content container. Tab should have either a <code>data-target</code> or an <code>href</code> targeting a container node in the DOM.
  </p>
<pre class="prettyprint linenums">
&lt;ul class="nav nav-tabs" id="myTab"&gt;
  &lt;li class="active"&gt;&lt;a href="#home"&gt;Home&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#profile"&gt;Profile&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#messages"&gt;Messages&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="#settings"&gt;Settings&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;

&lt;div class="tab-content"&gt;
  &lt;div class="tab-pane active" id="home"&gt;...&lt;/div&gt;
  &lt;div class="tab-pane" id="profile"&gt;...&lt;/div&gt;
  &lt;div class="tab-pane" id="messages"&gt;...&lt;/div&gt;
  &lt;div class="tab-pane" id="settings"&gt;...&lt;/div&gt;
&lt;/div&gt;

&lt;script&gt;
  $(function () {
    $('#myTab a:last').tab('show');
  })
&lt;/script&gt;
</pre>

  <h3>Events</h3>
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
       <td>This event fires on tab show, but before the new tab has been shown. Use <code>event.target</code> and <code>event.relatedTarget</code> to target the active tab and the previous active tab (if available) respectively.</td>
    </tr>
    <tr>
       <td>shown</td>
       <td>This event fires on tab show after a tab has been shown. Use <code>event.target</code> and <code>event.relatedTarget</code> to target the active tab and the previous active tab (if available) respectively.</td>
     </tr>
    </tbody>
  </table>
<pre class="prettyprint linenums">
$('a[data-toggle="tab"]').on('shown', function (e) {
  e.target // activated tab
  e.relatedTarget // previous tab
})
</pre>
</section>