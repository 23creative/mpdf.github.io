---
layout: page
title: indexentry
parent_title: HTML control tags
permalink: /reference/html-control-tags/indexentry.html
modification_time: 2015-08-05T12:01:24+00:00
---



<p>(mPDF &gt;= 1.0)</p>
<p>indexentry – Insert an Index entry for the document</p>
<h2>Description</h2>
<p class="manual_block">&lt;<b>indexentry</b>&nbsp; <span class="parameter">content</span> [ <span class="parameter">xref</span> ] /&gt;</p>
<p>Insert an Index entry for the document Index, referencing the current writing position in the document. If <span class="parameter">xref</span> is set, it will appear as a cross-referencing entry in the index as for <a href="{{ "/reference/mpdf-functions/indexentrysee.html" | prepend: site.baseurl }}">IndexEntrySee()</a>.</p>

<div class="alert alert-info" role="alert"><strong>Note:</strong> The Index must be generated explicity at the end of the document using <a href="{{ "/reference/mpdf-functions/tocpagebreak.html" | prepend: site.baseurl }}">CreateIndex()</a> at some point before <a href="{{ "/reference/mpdf-functions/output.html" | prepend: site.baseurl }}">Output()</a> is called.</div>
<h2>Attributes</h2>
<p class="manual_param_dt"><span class="parameter">content</span></p>
<p class="manual_param_dd">This attribute sets the text as it will appear in the Index entry. Text should be UTF-8 encoded.

<span class="parameter">content</span> cannot contain any of the characters: &lt; &gt; &amp; ' <i>or</i> " and must use the appropriate HTML entities e.g. &lt;indexentry content="&amp;lt; 40" /&gt;

It is recommended that you use htmlspecialchars('Content', ENT_QUOTES) for this.

<span class="smallblock">REQUIRED</span></p>
<p class="manual_param_dt"><span class="parameter">xref</span></p>
<p class="manual_param_dd">This attribute sets the text used as a cross-reference. Text should be UTF-8 encoded.

<span class="parameter">xref</span> cannot contain any of the characters: &lt; &gt; &amp; ' <i>or</i> " and must use the appropriate HTML entities e.g. &lt;indexentry xref="&amp;lt; 40" /&gt;

It is recommended that you use e.g. htmlspecialchars($xref, ENT_QUOTES) for this.

Text entries passed in the form "Subject:Subcategory" will appear in the Index as "Subject, Subcategory"

<span class="smallblock">OPTIONAL</span></p>
<h2>Changelog</h2>
<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>3.0</td>
<td><span class="parameter">xref</span> attribute added.</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF();

$mpdf->WriteHTML('<p>Beginning bit of document...</p>');

$mpdf->WriteHTML('<p>Your text which refers to a buffalo,<indexentry content="Buffalo" /> which you would like to see in the Index</p>');

$mpdf->AddPage();    

$mpdf->WriteHTML('<h2>Index</h2>',2);

$mpdf->CreateIndex(2, '', '', 3, 1, '', 5, 'serif','sans-serif');

$mpdf=Output();

?>
{% endhighlight %}

{% highlight php %}
Example #2
{% endhighlight %}

{% highlight php %}
<?php

$mpdf->WriteHTML('<p><indexentry content="Dromedary" xref="Camel:types" />The dromedary is atype of camel</p>');

// This will produce an entry in the Index under 'Dromedary' appearing as:

Dromedary - see Camel, types
{% endhighlight %}

<h2>Notes</h2>

<div class="alert alert-info" role="alert"><strong>Note:</strong> &lt;<a href="{{ "/reference/html-control-tags/tocentry.html" | prepend: site.baseurl }}">indexentry</a>&gt; may be a preferred form to <a href="{{ "/reference/mpdf-functions/indexentry.html" | prepend: site.baseurl }}">IndexEntry()</a>, as it will allow more precise identification of the position and page - the &lt;indexentry&gt; can be placed just next to the appropriate word.</div>
<h3>Recommended placement</h3>
<p>Recommended placement of Index Entries is just after the first word following the opening tag of the block element:</p>

{% highlight php %}
<h2>First<indexentry... /> word of a heading or block</h2>
{% endhighlight %}

<p>or alternatively just after the opening tag of the block element:</p>

{% highlight php %}
<h2><indexentry... />Heading or block</h2>
{% endhighlight %}

<p>or just after a word to be marked:</p>

{% highlight php %}
... this is a word<indexentry... /> in the middle of text to be marked ...
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/indexentry.html" | prepend: site.baseurl }}">IndexEntry()</a> - Mark an Index entry in the document </li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/tocpagebreak.html" | prepend: site.baseurl }}">CreateIndex()</a> - Generate a document Index</li>
</ul>
