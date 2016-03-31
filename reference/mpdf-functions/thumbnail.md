---
layout: page
title: Thumbnail()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/thumbnail.html
---

<div id="bpmbook" class="bpmbook" style="direction:ltr;">
<div class="topic_user_field">
<div id="U0">
<p>(mPDFI &gt;= 2.3)</p>
<p>Thumbnail – Create thumbnails of an external PDF file and insert in current document</p>
<h2>Description</h2>

<div class="alert alert-info" role="alert">void <b>Thumbnail</b> ( string <span class="parameter">$file</span> [, integer <span class="parameter">$numberperrow</span> [, float <span class="parameter">$spacing</span> ]])</div>
<p>Create thumbnails of an external PDF file and insert in current document.</p>
<h2>Parameters</h2>
<p class="manual_param_dt"><span class="parameter">file</span></p>
<p class="manual_param_dd">This parameter specifies the source PDF file to import.&nbsp; <span class="parameter">file</span> should be a relative path to a local file.</p>
<p class="manual_param_dt"><span class="parameter">numberperrow</span></p>
<p class="manual_param_dd"><span class="parameter">number</span> specifies the number of thumbnails to print in each <b>row</b>. 

<span class="smallblock">DEFAULT</span>: 3</p>
<p class="manual_param_dt"><span class="parameter">spacing</span></p>
<p class="manual_param_dd"><span class="parameter">S</span>pecifies the spacing (vertical and horizontal) between thumbnails in millimetres.

<span class="smallblock">DEFAULT</span>: 10</p>
<h2>Changelog</h2>
<table class="bpmTopic"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.3</td>
<td>Function was added.</td>
</tr>
</tbody> </table>
<h2>Examples</h2>

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

include("../mpdf.php");

$mpdf=new mPDF(); 

$mpdf->SetImportUse(); 

$mpdf->Thumbnail('testfile.pdf', 4);

$mpdf->Output();

?>
{% endhighlight %}

<h2>See Also</h2>
<ul>
<li><a href="/reference/mpdf-functions/setimportuse.html">SetImportUse()</a> - Enable the use of imported PDF files or templates</li>
<li><a href="/reference/mpdf-functions/setsourcefile.html">SetSourceFile()</a> - Specify the source PDF file used to import pages into the document

</li>
<li><a href="/reference/mpdf-functions/importpage.html">ImportPage()</a> - Import a page from an external PDF file

</li>
<li><a href="/reference/mpdf-functions/usetemplate.html">UseTemplate()</a> - Insert an imported page from an external PDF file

</li>
<li><a href="/reference/mpdf-functions/setpagetemplate.html">SetPageTemplate()</a> - Specify a page from an external PDF file to use as a template

</li>
<li><a href="/reference/mpdf-functions/setdoctemplate.html">SetDocTemplate()</a> - Specify an external PDF file to use as a template</li>
<li><a href="/reference/mpdf-functions/restartdoctemplate.html">RestartDocTemplate()</a> - Re-start the use of a Document template from the next page</li>
</ul>
<p>&nbsp;</p>
</div>
</div>

