---
title: Javascript Typeahead
description: Sample Javascript Typeahead

---

<section id="typeahead">
    <h2>Example</h2>
    <p>A basic, easily extended plugin for quickly creating elegant typeaheads with any form text input.</p>
    <div class="bs-docs-example" style="background-color: #f5f5f5;">
      <input type="text" class="span3" style="margin: 0 auto;" data-provide="typeahead" data-items="4" data-source='["Alabama","Alaska","Arizona","Arkansas","California","Colorado","Connecticut","Delaware","Florida","Georgia","Hawaii","Idaho","Illinois","Indiana","Iowa","Kansas","Kentucky","Louisiana","Maine","Maryland","Massachusetts","Michigan","Minnesota","Mississippi","Missouri","Montana","Nebraska","Nevada","New Hampshire","New Jersey","New Mexico","New York","North Dakota","North Carolina","Ohio","Oklahoma","Oregon","Pennsylvania","Rhode Island","South Carolina","South Dakota","Tennessee","Texas","Utah","Vermont","Virginia","Washington","West Virginia","Wisconsin","Wyoming"]'>
    </div>
    <pre class="prettyprint linenums">&lt;input type="text" data-provide="typeahead"&gt;</pre>
    <hr class="bs-docs-separator">
    <h2>Usage</h2>
    <h3>Via data attributes</h3>
    <p>Add data attributes to register an element with typeahead functionality as shown in the example above.</p>
    <h3>Via JavaScript</h3>
    <p>Call the typeahead manually with:</p>
    <pre class="prettyprint linenums">$('.typeahead').typeahead()</pre>
    <h3>Options</h3>
    <p>Options can be passed via data attributes or JavaScript. For data attributes, append the option name to <code>data-</code>, as in <code>data-source=""</code>.</p>
    <table class="table table-bordered table-striped">
      <thead>
       <tr>
         <th style="width: 100px;">Name</th>
         <th style="width: 50px;">type</th>
         <th style="width: 100px;">default</th>
         <th>description</th>
       </tr>
      </thead>
      <tbody>
        <tr>
         <td>source</td>
         <td>array, function</td>
         <td>[ ]</td>
         <td>The data source to query against. May be an array of strings or a function. The function is passed two arguments, the <code>query</code> value in the input field and the <code>process</code> callback. The function may be used synchronously by returning the data source directly or asynchronously via the <code>process</code> callback's single argument.</td>
       </tr>
       <tr>
         <td>items</td>
         <td>number</td>
         <td>8</td>
         <td>The max number of items to display in the dropdown.</td>
       </tr>
       <tr>
         <td>minLength</td>
         <td>number</td>
         <td>1</td>
         <td>The minimum character length needed before triggering autocomplete suggestions</td>
       </tr>
       <tr>
         <td>matcher</td>
         <td>function</td>
         <td>case insensitive</td>
         <td>The method used to determine if a query matches an item. Accepts a single argument, the <code>item</code> against which to test the query. Access the current query with <code>this.query</code>. Return a boolean <code>true</code> if query is a match.</td>
       </tr>
       <tr>
         <td>sorter</td>
         <td>function</td>
         <td>exact match,<br> case sensitive,<br> case insensitive</td>
         <td>Method used to sort autocomplete results. Accepts a single argument <code>items</code> and has the scope of the typeahead instance. Reference the current query with <code>this.query</code>.</td>
       </tr>
       <tr>
         <td>highlighter</td>
         <td>function</td>
         <td>highlights all default matches</td>
         <td>Method used to highlight autocomplete results. Accepts a single argument <code>item</code> and has the scope of the typeahead instance. Should return html.</td>
       </tr>
      </tbody>
    </table>
    <h3>Methods</h3>
    <h4>.typeahead(options)</h4>
    <p>Initializes an input with a typeahead.</p>
</section>
