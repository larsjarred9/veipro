<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="CSRF_Tokens_0"></a>CSRF Tokens</h2>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>CSRF Token Generation</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="9" class="language-php"><span class="hljs-keyword">if</span> (<span class="hljs-keyword">empty</span>(<span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'token'</span>])) {
    <span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'token'</span>] = bin2hex(random_bytes(<span class="hljs-number">32</span>));
}
<span class="hljs-variable">$token</span> = <span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">'token'</span>];
</code></pre>
<p class="has-line-data" data-line-start="10" data-line-end="11"><strong>CSRF Token in form</strong></p>
<pre><code class="has-line-data" data-line-start="12" data-line-end="14" class="language-php">&lt;input type=<span class="hljs-string">"hidden"</span> name=<span class="hljs-string">"token"</span> value=<span class="hljs-string">"&lt;?php echo $token ?&gt;"</span>&gt;
</code></pre>
<p class="has-line-data" data-line-start="15" data-line-end="16"><strong>CSRF Token verrify</strong></p>
<pre><code class="has-line-data" data-line-start="17" data-line-end="27" class="language-php"><span class="hljs-keyword">if</span> (<span class="hljs-keyword">empty</span>(<span class="hljs-variable">$_POST</span>[<span class="hljs-string">'token'</span>])) {
    header(<span class="hljs-string">"location: ../../index?error=Token field did not contain any information."</span>);
    <span class="hljs-keyword">return</span> <span class="hljs-keyword">false</span>;
}

<span class="hljs-keyword">if</span> (!hash_equals(<span class="hljs-variable">$_SESSION</span>[<span class="hljs-string">"token"</span>], <span class="hljs-variable">$_POST</span>[<span class="hljs-string">"token"</span>])) {
    header(<span class="hljs-string">"location: ../../index?error=Anti-Spam Token field failed."</span>);
    <span class="hljs-keyword">return</span> <span class="hljs-keyword">false</span>;
}
</code></pre>
<p class="has-line-data" data-line-start="28" data-line-end="30"><strong>More information</strong><br>
<a href="https://stackoverflow.com/questions/6287903/how-to-properly-add-cross-site-request-forgery-csrf-token-using-php">https://stackoverflow.com/questions/6287903/how-to-properly-add-cross-site-request-forgery-csrf-token-using-php</a></p>