---
title: Javascript Alerts Samples
description: Alert Samples
---

<section id="alerts">
    <h2>Example alerts</h2>
    <p>Add dismiss functionality to all alerge messages with this plugin.</p>
    <div class="bs-docs-example">
      <div class="alert fade in">
        <button type="button" class="close" data-dismiss="alert">&times;</button>
        <strong>Holy guacamole!</strong> Best check yo self, you're not looking too good.
      </div>
    </div>
    <div class="bs-docs-example">
      <div class="alert alert-block alert-error fade in">
        <button type="button" class="close" data-dismiss="alert">&times;</button>
        <h4 class="alert-heading">Oh snap! You got an error!</h4>
        <p>Change this and that and try again. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Cras mattis consectetur purus sit amet fermentum.</p>
        <p>
          <a class="btn btn-danger" href="#">Take this action</a> <a class="btn" href="#">Or do this</a>
        </p>
      </div>
    </div>
    <hr class="bs-docs-separator">
    <h2>Usage</h2>
    <p>Enable dismissal of an alert via JavaScript:</p>
    <pre class="prettyprint linenums">$(".alert").alert()</pre>
    <h3>Markup</h3>
    <p>Just add <code>data-dismiss="alert"</code> to your close button to automatically give an alert close functionality.</p>
    <pre class="prettyprint linenums">&lt;a class="close" data-dismiss="alert" href="#"&gt;&amp;times;&lt;/a&gt;</pre>
    <h3>Methods</h3>
    <h4>$().alert()</h4>
    <p>Wraps all alerts with close functionality. To have your alerts animate out when closed, make sure they have the <code>.fade</code> and <code>.in</code> class already applied to them.</p>
    <h4>.alert('close')</h4>
    <p>Closes an alert.</p>
    <pre class="prettyprint linenums">$(".alert").alert('close')</pre>
    <h3>Events</h3>
    <p>Bootstrap's alert class exposes a few events for hooking into alert functionality.</p>
    <table class="table table-bordered table-striped">
      <thead>
       <tr>
         <th style="width: 150px;">Event</th>
         <th>Description</th>
       </tr>
      </thead>
      <tbody>
       <tr>
         <td>close</td>
         <td>This event fires immediately when the <code>close</code> instance method is called.</td>
       </tr>
       <tr>
         <td>closed</td>
         <td>This event is fired when the alert has been closed (will wait for css transitions to complete).</td>
       </tr>
      </tbody>
    </table>
<pre class="prettyprint linenums">
$('#my-alert').bind('closed', function () {
  // do something…
})
</pre>
</section>
