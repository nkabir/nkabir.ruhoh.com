---
title: Bootstrap Samples
description: Demonstration of Bootstrap functionality
---

<!-- Typography
================================================== -->
<section id="typography">
  <h1>Typography</h1> 
  <h2 id="headings">Headings</h2>
  <p>All HTML headings, <code>&lt;h1&gt;</code> through <code>&lt;h6&gt;</code> are available.</p>
  <div class="bs-docs-example">
    <h1>h1. Heading 1</h1>
    <h2>h2. Heading 2</h2>
    <h3>h3. Heading 3</h3>
    <h4>h4. Heading 4</h4>
    <h5>h5. Heading 5</h5>
    <h6>h6. Heading 6</h6>
  </div>  
  
<h2 id="body-copy">Body copy</h2>
<p>Bootstrap's global default <code>font-size</code> is <strong>14px</strong>, with a <code>line-height</code> of <strong>20px</strong>. This is applied to the <code>&lt;body&gt;</code> and all paragraphs. In addition, <code>&lt;p&gt;</code> (paragraphs) receive a bottom margin of half their line-height (9px by default).</p>

<div class="bs-docs-example">
  <p>Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nullam id dolor id nibh ultricies vehicula.</p>
  <p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec ullamcorper nulla non metus auctor fringilla. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Donec ullamcorper nulla non metus auctor fringilla.</p>
  <p>Maecenas sed diam eget risus varius blandit sit amet non magna. Donec id elit non mi porta gravida at eget metus. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit.</p>
</div>

<pre class="prettyprint">&lt;p&gt;...&lt;/p&gt;</pre>

<h3>Lead body copy</h3>
<p>Make a paragraph stand out by adding <code>.lead</code>.</p>
<div class="bs-docs-example">
  <p class="lead">Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus.</p>
</div>
<pre class="prettyprint">&lt;p class="lead"&gt;...&lt;/p&gt;</pre>



<h3>Built with Less</h3>
<p>The typographic scale is based on two LESS variables in <strong>variables.less</strong>: <code>@baseFontSize</code> and <code>@baseLineHeight</code>. The first is the base font-size used throughout and the second is the base line-height. We use those variables and some simple math to create the margins, paddings, and line-heights of all our type and more. Customize them and Bootstrap adapts.</p>


<hr class="bs-docs-separator">
  
</section>