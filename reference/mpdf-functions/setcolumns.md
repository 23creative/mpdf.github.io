---
layout: page
title: SetColumns()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/setcolumns.html
modification_time: 2015-08-05T12:00:56+00:00
---



<p>(mPDF &gt;= 1.0)</p>
<p>SetColumns – Control use of Columns on the page</p>
<h2>Description</h2>
<p class="manual_block">void <b>SetColumns</b> ( int <span class="parameter">$nCols</span> [, string <span class="parameter">$vAlign</span> [, float <span class="parameter">$gap</span> ]])</p>
<p>Define, start or stop Columns in the document.</p>

<div class="alert alert-info" role="alert"><strong>Note:</strong> The maximum ratio to adjust column height when justifying is set by <a href="{{ "/reference/mpdf-variables/max-colh-correction.html" | prepend: site.baseurl }}">$max_colH_correction</a> - too large a value can give ugly results</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> If you are setting HTMLHeaders or HTMLFooters, this will cancel any columns you have set; you need to call SetColumns() after commands like <a href="{{ "/reference/mpdf-functions/sethtmlheader.html" | prepend: site.baseurl }}">SetHTMLHeader()</a> etc.</div>
<h2>Parameters</h2>
<p class="manual_param_dt"><span class="parameter">nCols</span></p>
<p class="manual_param_dd">Set the number of (vertical) columns to use on a page

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 or 1 turns Columns OFF i.e. the whole page is used as one column.

<span class="smallblock">DEFAULT</span>: 1</p>
<p class="manual_param_dt"><span class="parameter">vAlign</span></p>
<p class="manual_param_dd">Automatically adjusts height of columns to be equal if set to J or justify.

<span class="smallblock">BLANK</span>&nbsp;or omitted turns vertical-alignment OFF</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

J or justify

<span class="smallblock">DEFAULT</span>: ""</p>
<p class="manual_param_dt"><span class="parameter">gap</span></p>
<p class="manual_param_dd">Set the gap between columns in millimeters

<span class="smallblock">BLANK</span>&nbsp;or omitted uses default value.

<span class="smallblock">DEFAULT</span>: 5 (mm)</p>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF();

$mPDF->SetColumns(2, 'J', 3);

$mpdf->WriteHTML('<p>Some text...</p>');

$mpdf->AddColumn();

$mpdf->WriteHTML('<p>Next column...</p>');

$mpdf=Output();

?>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/addcolumn.html" | prepend: site.baseurl }}">AddColumn()</a> - Start a new Column</li>
<li class="manual_boxlist">&lt;<a href="{{ "/reference/html-control-tags/columnbreak.html" | prepend: site.baseurl }}">columnbreak</a>&gt; - Start a new Column</li>
<li class="manual_boxlist">&lt;<a href="{{ "/reference/html-control-tags/columns.html" | prepend: site.baseurl }}">columns</a>&gt; - Control the use of multiple columns on the page - HTML equivalent of SetColumns()

</li>
</ul>
