# Upload Files Or Images To Server Using Node JS
## License
- MIT
## Technologies
- jQuery
- HTML5
- Node.js
## Topics
- jQuery
- Multi file upload
- Visual Studio
- HTML5
- Node.js
- nodejs
- Node JS Packages
## Updated
- 12/10/2016
## Description

<p>In this post we will see how we can upload files or images to server using&nbsp;<a href="http://sibeeshpassion.com/category/Node-JS/" target="_blank">Node JS</a>. Here we are going to use&nbsp;<a href="http://sibeeshpassion.com/category/visual-studio/" target="_blank">Visual
 Studio</a>&nbsp;for our development and preceding NPM packages for our easy development.</p>
<li>express </li><li>multer </li><li>body-parser
<p>We will briefly explain the use of these packages. As you all know Node JS is a run time environment built on Chrome&rsquo;s V8 JavaScript engine for server side and networking application. And it is an open source which supports cross platforms. Node JS
 applications are written in pure&nbsp;<a href="http://sibeeshpassion.com/category/javascript/" target="_blank">JavaScript</a>. If you are new to Node JS, I strongly recommend you to read my previous posts about Node JS&nbsp;<a href="http://sibeeshpassion.com/category/node-js/" target="_blank">here</a>.</p>
<p><br>
Background</p>
<p>Few years back if you need to upload any files or images to server, you were completely depended on server side languages like&nbsp;<a href="http://sibeeshpassion.com/category/csharp/" target="_blank">C#</a>&nbsp;and&nbsp;<a href="http://sibeeshpassion.com/category/PHP/" target="_blank">PHP</a>.
 Everything is changed after the revolution of&nbsp;<a href="http://sibeeshpassion.com/category/node-js/" target="_blank">Node JS</a>. Here I will show you how to upload the files to server using Node JS, without writing even a single line of server side code.
 I hope you will like this.</p>
<p><span>Create a Blank Node JS Web Application</span></p>
<p>Create a blank Node JS web application.</p>
<div class="wp-caption x_alignnone" id="attachment_11968"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/New_Node_JS_Web_Application.png"><img class="size-large x_wp-image-11968" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/New_Node_JS_Web_Application-1024x709.png" alt="new_node_js_web_application" width="634" height="439"></a>
<p class="wp-caption-text">new_node_js_web_application</p>
</div>
<p><span>Set Up Dependencies in package.json</span></p>
<p>To get started, we will set up our dependencies first. To do so, please open your package.json file and paste the preceding code.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_167610">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js"><span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;name&quot;</span>:&nbsp;<span class="js__string">&quot;node_js_file_upload&quot;</span>,&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;version&quot;</span>:&nbsp;<span class="js__string">&quot;0.0.1&quot;</span>,&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;description&quot;</span>:&nbsp;<span class="js__string">&quot;Node_JS_File_Upload&quot;</span>,&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;main&quot;</span>:&nbsp;<span class="js__string">&quot;server.js&quot;</span>,&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;dependencies&quot;</span>:&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__string">&quot;body-parser&quot;</span>:&nbsp;<span class="js__string">&quot;^1.15.2&quot;</span>,&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__string">&quot;express&quot;</span>:&nbsp;<span class="js__string">&quot;^4.14.0&quot;</span>,&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__string">&quot;multer&quot;</span>:&nbsp;<span class="js__string">&quot;^1.2.0&quot;</span>&nbsp;
&nbsp;&nbsp;<span class="js__brace">}</span>,&nbsp;
&nbsp;&nbsp;<span class="js__string">&quot;author&quot;</span>:&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__string">&quot;name&quot;</span>:&nbsp;<span class="js__string">&quot;Sibeesh&quot;</span>&nbsp;
&nbsp;&nbsp;<span class="js__brace">}</span>&nbsp;
<span class="js__brace">}</span></pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<br>
<table border="0" cellspacing="0" cellpadding="0">
<tbody>
</tbody>
</table>
</div>
</div>
<p>Now, run the NPM install command as follows.</p>
<div>
<div class="syntaxhighlighter csharp" id="highlighter_111562">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">npm&nbsp;install&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>Once you run the command, you can see that the dependencies are installed in the solution.</p>
<div class="wp-caption x_alignnone" id="attachment_11969"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/NPM-Packages-e1481366627834.png"><img class="size-full x_wp-image-11969" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/NPM-Packages-e1481366627834.png" alt="npm-packages" width="634" height="624"></a>
<p class="wp-caption-text">npm-packages</p>
</div>
<p>Now we can understand what are these dependencies used for.</p>
</li><li>express
<p>As per the&nbsp;<a href="https://expressjs.com/" target="_blank">Express Team</a>, Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.Express provides a thin layer of
 fundamental web application features, without obscuring Node.js features that you know and love. You can always learn more about Express Package&nbsp;<a href="https://expressjs.com/" target="_blank">here</a></p>
</li><li>multer
<p>Multer is a node.js middleware for handling multipart/form-data, which is primarily used for uploading files. It is written on top of busboy for maximum efficiency. Please read more about multer package&nbsp;<a href="https://github.com/expressjs/multer" target="_blank">here.</a></p>
<p><span>Start using our dependencies</span></p>
<p>You can create the instances of our dependencies as follows.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_498426">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js"><span class="js__statement">var</span>&nbsp;Express&nbsp;=&nbsp;require(<span class="js__string">'express'</span>);&nbsp;
<span class="js__statement">var</span>&nbsp;multer&nbsp;=&nbsp;require(<span class="js__string">'multer'</span>);&nbsp;
<span class="js__statement">var</span>&nbsp;bodyParser&nbsp;=&nbsp;require(<span class="js__string">'body-parser'</span>);&nbsp;
<span class="js__statement">var</span>&nbsp;app&nbsp;=&nbsp;Express();&nbsp;
app.use(bodyParser.json());&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>Then, it is time to create a storage which says where and how the files/images should be saved.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_559440">
<table border="0" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td class="gutter">
<div class="line number1 index0 alt2">1</div>
<div class="line number2 index1 alt1">2</div>
<div class="line number3 index2 alt2">3</div>
<div class="line number4 index3 alt1">4</div>
<div class="line number5 index4 alt2">5</div>
<div class="line number6 index5 alt1">6</div>
<div class="line number7 index6 alt2">7</div>
<div class="line number8 index7 alt1">8</div>
</td>
<td class="code">
<div class="container">
<div class="line number1 index0 alt2"><code class="jscript x_keyword">var</code>
<code class="jscript x_plain">Storage = multer.diskStorage({</code></div>
<div class="line number2 index1 alt1"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">destination:
</code><code class="jscript x_keyword">function</code> <code class="jscript x_plain">
(req, file, callback) {</code></div>
<div class="line number3 index2 alt2"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">callback(</code><code class="jscript x_keyword">null</code><code class="jscript x_plain">,
</code><code class="jscript x_string">&quot;./Images&quot;</code><code class="jscript x_plain">);</code></div>
<div class="line number4 index3 alt1"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">},</code></div>
<div class="line number5 index4 alt2"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">filename:
</code><code class="jscript x_keyword">function</code> <code class="jscript x_plain">
(req, file, callback) {</code></div>
<div class="line number6 index5 alt1"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">callback(</code><code class="jscript x_keyword">null</code><code class="jscript x_plain">,
 file.fieldname &#43; </code><code class="jscript x_string">&quot;_&quot;</code> <code class="jscript x_plain">
&#43; Date.now() &#43; </code><code class="jscript x_string">&quot;_&quot;</code> <code class="jscript x_plain">
&#43; file.originalname);</code></div>
<div class="line number7 index6 alt2"><code class="jscript x_spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="jscript x_plain">}</code></div>
<div class="line number8 index7 alt1"><code class="jscript x_plain">});</code></div>
</div>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<p>Each file contains the following information:</p>
<p><em>fieldname :</em>Field name specified in the form<br>
<em>originalname&nbsp;</em>Name of the file on the user&rsquo;s computer<br>
<em>encoding :</em>Encoding type of the file<br>
<em>mimetype :</em>Mime type of the file<br>
<em>size :</em>Size of the file in bytes<br>
<em>destination :</em>The folder to which the file has been saved<br>
<em>filename :</em>The name of the file within the destination<br>
<em>path :</em>The full path to the uploaded file<br>
<em>buffer :</em>A Buffer of the entire file</p>
<p>Now please create multer object as follows.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_439743">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js"><span class="js__statement">var</span>&nbsp;upload&nbsp;=&nbsp;multer(<span class="js__brace">{</span>&nbsp;storage:&nbsp;Storage&nbsp;<span class="js__brace">}</span>).array(<span class="js__string">&quot;imgUploader&quot;</span>,&nbsp;<span class="js__num">3</span>);&nbsp;<span class="js__sl_comment">//Field&nbsp;name&nbsp;and&nbsp;max&nbsp;count</span>&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>Here multer accepts the storage we created in our previous step as the parameter. The function</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_211031">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">array(fieldname[,&nbsp;maxCount])&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>accept an array of files, all with the name fieldname.</p>
<p>Now it is time to write our post and get action.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_459725">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">app.get(<span class="js__string">&quot;/&quot;</span>,&nbsp;<span class="js__operator">function</span>&nbsp;(req,&nbsp;res)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;res.sendFile(__dirname&nbsp;&#43;&nbsp;<span class="js__string">&quot;/index.html&quot;</span>);&nbsp;
<span class="js__brace">}</span>);&nbsp;
&nbsp;&nbsp;
app.post(<span class="js__string">&quot;/api/Upload&quot;</span>,&nbsp;<span class="js__operator">function</span>&nbsp;(req,&nbsp;res)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;upload(req,&nbsp;res,&nbsp;<span class="js__operator">function</span>&nbsp;(err)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">if</span>&nbsp;(err)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">return</span>&nbsp;res.end(<span class="js__string">&quot;Something&nbsp;went&nbsp;wrong!&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">return</span>&nbsp;res.end(<span class="js__string">&quot;File&nbsp;uploaded&nbsp;sucessfully!.&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>);&nbsp;
<span class="js__brace">}</span>);&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>Here&nbsp;<em>/api/Upload</em>&nbsp;is the action name we are going to set in out HTML page which we will create soon. And last but not the least, we need to make sure that the app is listening to our particular port, in this case it is port 2000.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_946997">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">app.listen(<span class="js__num">2000</span>,&nbsp;<span class="js__operator">function</span>&nbsp;(a)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;console.log(<span class="js__string">&quot;Listening&nbsp;to&nbsp;port&nbsp;2000&quot;</span>);&nbsp;
<span class="js__brace">}</span>);&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p><span>Create HTML page and set up uploading</span></p>
<p>You can create the page as follows with the references of the&nbsp;<em>jquery-3.1.1.min.js</em>&nbsp;and&nbsp;<em>jquery.form.min.js</em>.</p>
<div>
<div class="syntaxhighlighter xml" id="highlighter_393515">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">&lt;!DOCTYPE&nbsp;html&gt;&nbsp;
&nbsp;&nbsp;
&lt;html&nbsp;xmlns=<span class="js__string">&quot;http://www.w3.org/1999/xhtml&quot;</span>&gt;&nbsp;
&lt;head&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;meta&nbsp;charset=<span class="js__string">&quot;utf-8&quot;</span>&nbsp;/&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;Upload&nbsp;images&nbsp;to&nbsp;server&nbsp;using&nbsp;Node&nbsp;JS&lt;/title&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;script&nbsp;src=<span class="js__string">&quot;Scripts/jquery-3.1.1.min.js&quot;</span>&gt;&lt;/script&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;script&nbsp;src=<span class="js__string">&quot;Scripts/jquery.form.min.js&quot;</span>&gt;&lt;/script&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&lt;/head&gt;&nbsp;
&lt;body&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;form&nbsp;id=<span class="js__string">&quot;frmUploader&quot;</span>&nbsp;enctype=<span class="js__string">&quot;multipart/form-data&quot;</span>&nbsp;action=<span class="js__string">&quot;api/Upload/&quot;</span>&nbsp;method=<span class="js__string">&quot;post&quot;</span>&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;input&nbsp;type=<span class="js__string">&quot;file&quot;</span>&nbsp;name=<span class="js__string">&quot;imgUploader&quot;</span>&nbsp;multiple&nbsp;/&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;input&nbsp;type=<span class="js__string">&quot;submit&quot;</span>&nbsp;name=<span class="js__string">&quot;submit&quot;</span>&nbsp;id=<span class="js__string">&quot;btnSubmit&quot;</span>&nbsp;value=<span class="js__string">&quot;Upload&quot;</span>&nbsp;/&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/form&gt;&nbsp;
&lt;/body&gt;&nbsp;
&lt;/html&gt;&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<p>Please be noted that the&nbsp;<em>ecctype&nbsp;</em>for your form must be&nbsp;<em>multipart/form-data</em>&nbsp;and the action must be same as we set in our API.</p>
<p><span>Create Ajax submit event</span></p>
<p>Now it is time to create our ajax event where we are going to call our API.</p>
<div>
<div class="syntaxhighlighter jscript" id="highlighter_688709">
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>JavaScript</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">js</span>

<div class="preview">
<pre class="js">&lt;script&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$(document).ready(<span class="js__operator">function</span>&nbsp;()&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">var</span>&nbsp;options&nbsp;=&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;beforeSubmit:&nbsp;showRequest,&nbsp;&nbsp;<span class="js__sl_comment">//&nbsp;pre-submit&nbsp;callback</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;success:&nbsp;showResponse&nbsp;&nbsp;//&nbsp;post-submit&nbsp;callback&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>;&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__sl_comment">//&nbsp;bind&nbsp;to&nbsp;the&nbsp;form's&nbsp;submit&nbsp;event</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$(<span class="js__string">'#frmUploader'</span>).submit(<span class="js__operator">function</span>&nbsp;()&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$(<span class="js__operator">this</span>).ajaxSubmit(options);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__sl_comment">//&nbsp;always&nbsp;return&nbsp;false&nbsp;to&nbsp;prevent&nbsp;standard&nbsp;browser&nbsp;submit&nbsp;and&nbsp;page&nbsp;navigation</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">return</span>&nbsp;false;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>);&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__sl_comment">//&nbsp;pre-submit&nbsp;callback</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__operator">function</span>&nbsp;showRequest(formData,&nbsp;jqForm,&nbsp;options)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;alert(<span class="js__string">'Uploading&nbsp;is&nbsp;starting.'</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">return</span>&nbsp;true;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__sl_comment">//&nbsp;post-submit&nbsp;callback</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__operator">function</span>&nbsp;showResponse(responseText,&nbsp;statusText,&nbsp;xhr,&nbsp;$form)&nbsp;<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;alert(<span class="js__string">'status:&nbsp;'</span>&nbsp;&#43;&nbsp;statusText&nbsp;&#43;&nbsp;<span class="js__string">'\n\nresponseText:&nbsp;\n'</span>&nbsp;&#43;&nbsp;responseText&nbsp;);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__brace">}</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/script&gt;&nbsp;
</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
</div>
<blockquote>
<p><em>ajaxSubmit</em>&nbsp;function is part of the plugin&nbsp;<em>jquery.form.min.js</em>, so please make sure that you have included it.</p>
</blockquote>
<p><span>Run your application</span></p>
<p>Now please run your application. Before running your application, you can always set your script file as your start up file, to set it, please right click on your project and click on properties.</p>
<div class="wp-caption x_alignnone" id="attachment_11970"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/Set-start-up-file.png"><img class="size-large x_wp-image-11970" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/Set-start-up-file-1024x383.png" alt="set-start-up-file" width="634" height="237"></a>
<p class="wp-caption-text">set-start-up-file</p>
</div>
<p>Now you can open your command prompt, you can manually locate your project in command prompt or you can use the &lsquo;Open command prompt here&rsquo; option. To select, please right click on your project and select the option as follows.</p>
<div class="wp-caption x_alignnone" id="attachment_11971"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/Open_command_prompt_here_option.png"><img class="size-full x_wp-image-11971" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/Open_command_prompt_here_option-e1481369183917.png" alt="open_command_prompt_here_option" width="773" height="1008"></a>
<p class="wp-caption-text">open_command_prompt_here_option</p>
</div>
<p>Now type&nbsp;<em>node server.js</em>&nbsp;in your command prompt which will make sure that your server is running. And if everything is fine, you can see a window as follows.</p>
<div class="wp-caption x_alignnone" id="attachment_11972"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/Node_server_js_output.png"><img class="size-full x_wp-image-11972" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/Node_server_js_output.png" alt="node_server_js_output" width="583" height="414"></a>
<p class="wp-caption-text">node_server_js_output</p>
</div>
<p>We can run our webpage now as our server is ready, please go to your browser and type the URL as&nbsp;<a href="http://localhost:2000/" target="_blank">http://localhost:2000</a>. Select few files using the file uploader we have created.</p>
<div class="wp-caption x_alignnone" id="attachment_11973"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/Select_fiels_in_file_upload-e1481369767333.png"><img class="size-full x_wp-image-11973" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/Select_fiels_in_file_upload-e1481369767333.png" alt="select_fiels_in_file_upload" width="634" height="117"></a>
<p class="wp-caption-text">select_fiels_in_file_upload</p>
</div>
<p>If you click submit, you can see we are calling our method action and the files are uploaded.</p>
<div class="wp-caption x_alignnone" id="attachment_11974"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/File_uploaded_successfully_-e1481369870966.png"><img class="size-full x_wp-image-11974" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/File_uploaded_successfully_-e1481369870966.png" alt="file_uploaded_successfully_" width="634" height="122"></a>
<p class="wp-caption-text">file_uploaded_successfully_</p>
</div>
<div class="wp-caption x_alignnone" id="attachment_11975"><a href="http://sibeeshpassion.com/wp-content/uploads/2016/12/Solution_explorer_window_after_saving_files-e1481369985988.png"><img class="size-full x_wp-image-11975" src="http://sibeeshpassion.com/wp-content/uploads/2016/12/Solution_explorer_window_after_saving_files-e1481369985988.png" alt="solution_explorer_window_after_saving_files" width="634" height="603"></a>
<p class="wp-caption-text">solution_explorer_window_after_saving_files</p>
</div>
<p>You can always download the source code attached to see the complete code and application. Happy coding!.</p>
</li>