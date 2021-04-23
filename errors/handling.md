<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="Error_Handling_0"></a>Error Handling</h2>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>Try Catch</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="11" class="language-php"><span class="hljs-keyword">try</span> {
    <span class="hljs-comment">/* all your code */</span>
} <span class="hljs-keyword">catch</span> (<span class="hljs-keyword">Exception</span> <span class="hljs-variable">$e</span>) {
   <span class="hljs-comment">/* if something fails inside try block will be catched here */</span>
    <span class="hljs-keyword">print</span> <span class="hljs-variable">$e</span>-&gt;getMessage();
}
</code></pre>
<p class="has-line-data" data-line-start="12" data-line-end="13"><strong>Throw Exception</strong></p>
<pre><code class="has-line-data" data-line-start="14" data-line-end="16" class="language-php"><span class="hljs-keyword">throw</span> <span class="hljs-keyword">new</span> <span class="hljs-keyword">Exception</span>(<span class="hljs-string">"I think something's failing"</span>);
</code></pre>
<p class="has-line-data" data-line-start="17" data-line-end="18"><strong>Show errors on plesk</strong></p>
<pre><code class="has-line-data" data-line-start="19" data-line-end="23" class="language-php">ini_set(<span class="hljs-string">'display_errors'</span>, <span class="hljs-number">1</span>);
ini_set(<span class="hljs-string">'display_startup_errors'</span>, <span class="hljs-number">1</span>);
error_reporting(E_ALL);
</code></pre>