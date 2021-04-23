<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="Auto_Logout_0"></a>Auto Logout</h2>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>Check Time - Auto logout script</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="10" class="language-php"><span class="hljs-keyword">if</span> ((time() - <span class="hljs-number">600</span>) &gt; <span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'timestamp'</span>]) {
    <span class="hljs-comment">// Logout te oud</span>
} <span class="hljs-keyword">else</span> {
    <span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'timestamp'</span>] = time();
}
</code></pre>
<p class="has-line-data" data-line-start="11" data-line-end="12"><strong>Init Time when login</strong></p>
<pre><code class="has-line-data" data-line-start="13" data-line-end="15" class="language-php"><span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'timestamp'</span>] = time();
</code></pre>