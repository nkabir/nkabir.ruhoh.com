---
title: Table Samples
description: Demonstrations of Table Formatting
categories: [ 'samples/base' ]

---
<section id="tables">
  <h2>Default styles</h2>
  <p>For basic styling&mdash;light padding and only horizontal dividers&mdash;add the base class <code>.table</code> to any <code>&lt;table&gt;</code>.</p>
  <div class="bs-docs-example">
    <table class="table">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <td>3</td>
          <td>Larry</td>
          <td>the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
  
<pre class="prettyprint linenums">
    &lt;table class="table"&gt;
      …
    &lt;/table&gt;
</pre>


<hr class="bs-docs-separator">


  <h2>Optional classes</h2>
  <p>Add any of the follow classes to the <code>.table</code> base class.</p>

  <h3><code>.table-striped</code></h3>
  <p>Adds zebra-striping to any table row within the <code>&lt;tbody&gt;</code> via the <code>:nth-child</code> CSS selector (not available in IE7-IE8).</p>
  <div class="bs-docs-example">
    <table class="table table-striped">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <td>3</td>
          <td>Larry</td>
          <td>the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
          
<pre class="prettyprint linenums" style="margin-bottom: 18px;">
    &lt;table class="table table-striped"&gt;
      …
    &lt;/table&gt;
</pre>

  <h3><code>.table-bordered</code></h3>
  <p>Add borders and rounded corners to the table.</p>
  <div class="bs-docs-example">
    <table class="table table-bordered">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td rowspan="2">1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <td>Mark</td>
          <td>Otto</td>
          <td>@TwBootstrap</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <td>3</td>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
  
<pre class="prettyprint linenums">
    &lt;table class="table table-bordered"&gt;
      …
    &lt;/table&gt;
</pre>

  <h3><code>.table-hover</code></h3>
  <p>Enable a hover state on table rows within a <code>&lt;tbody&gt;</code>.</p>
  <div class="bs-docs-example">
    <table class="table table-hover">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <td>3</td>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
          
<pre class="prettyprint linenums" style="margin-bottom: 18px;">
    &lt;table class="table table-hover"&gt;
      …
    &lt;/table&gt;
</pre>

  <h3><code>.table-condensed</code></h3>
  <p>Makes tables more compact by cutting cell padding in half.</p>
  <div class="bs-docs-example">
    <table class="table table-condensed">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <td>3</td>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
          
<pre class="prettyprint linenums" style="margin-bottom: 18px;">
    &lt;table class="table table-condensed"&gt;
      …
    &lt;/table&gt;
</pre>


<hr class="bs-docs-separator">


  <h2>Optional row classes</h2>
  <p>Use contextual classes to color table rows.</p>
  <table class="table table-bordered table-striped">
    <colgroup>
      <col class="span1">
      <col class="span7">
    </colgroup>
    <thead>
      <tr>
        <th>Class</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>.success</code>
        </td>
        <td>Indicates a successful or positive action.</td>
      </tr>
      <tr>
        <td>
          <code>.error</code>
        </td>
        <td>Indicates a dangerous or potentially negative action.</td>
      </tr>
      <tr>
        <td>
          <code>.info</code>
        </td>
        <td>Used as an alternative to the default styles.</td>
      </tr>
    </tbody>
  </table>
  <div class="bs-docs-example">
    <table class="table">
      <thead>
        <tr>
          <th>#</th>
          <th>Product</th>
          <th>Payment Taken</th>
          <th>Status</th>
        </tr>
      </thead>
      <tbody>
        <tr class="success">
          <td>1</td>
          <td>TB - Monthly</td>
          <td>01/04/2012</td>
          <td>Approved</td>
        </tr>
        <tr class="error">
          <td>2</td>
          <td>TB - Monthly</td>
          <td>02/04/2012</td>
          <td>Declined</td>
        </tr>
        <tr class="info">
          <td>3</td>
          <td>TB - Monthly</td>
          <td>03/04/2012</td>
          <td>Pending</td>
        </tr>
      </tbody>
    </table>
  </div>
  
<pre class="prettyprint linenums">
    ...
      &lt;tr class="success"&gt;
        &lt;td&gt;1&lt;/td&gt;
        &lt;td&gt;TB - Monthly&lt;/td&gt;
        &lt;td&gt;01/04/2012&lt;/td&gt;
        &lt;td&gt;Approved&lt;/td&gt;
      &lt;/tr&gt;
    ...
</pre>


<hr class="bs-docs-separator">


  <h2>Supported table markup</h2>
  <p>List of supported table HTML elements and how they should be used.</p>
  <table class="table table-bordered table-striped">
    <colgroup>
      <col class="span1">
      <col class="span7">
    </colgroup>
    <thead>
      <tr>
        <th>Tag</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <code>&lt;table&gt;</code>
        </td>
        <td>
          Wrapping element for displaying data in a tabular format
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;thead&gt;</code>
        </td>
        <td>
          Container element for table header rows (<code>&lt;tr&gt;</code>) to label table columns
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;tbody&gt;</code>
        </td>
        <td>
          Container element for table rows (<code>&lt;tr&gt;</code>) in the body of the table
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;tr&gt;</code>
        </td>
        <td>
          Container element for a set of table cells (<code>&lt;td&gt;</code> or <code>&lt;th&gt;</code>) that appears on a single row
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;td&gt;</code>
        </td>
        <td>
          Default table cell
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;th&gt;</code>
        </td>
        <td>
          Special table cell for column (or row, depending on scope and placement) labels<br>
          Must be used within a <code>&lt;thead&gt;</code>
        </td>
      </tr>
      <tr>
        <td>
          <code>&lt;caption&gt;</code>
        </td>
        <td>
          Description or summary of what the table holds, especially useful for screen readers
        </td>
      </tr>
    </tbody>
  </table>
  
<pre class="prettyprint linenums">
    &lt;table&gt;
      &lt;caption&gt;...&lt;/caption&gt;
      &lt;thead&gt;
        &lt;tr&gt;
          &lt;th&gt;...&lt;/th&gt;
          &lt;th&gt;...&lt;/th&gt;
        &lt;/tr&gt;
      &lt;/thead&gt;
      &lt;tbody&gt;
        &lt;tr&gt;
          &lt;td&gt;...&lt;/td&gt;
          &lt;td&gt;...&lt;/td&gt;
        &lt;/tr&gt;
      &lt;/tbody&gt;
    &lt;/table&gt;
</pre>

</section>
