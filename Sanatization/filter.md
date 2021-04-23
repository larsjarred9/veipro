<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="Sanatization_0"></a>Sanatization</h2>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>Filter Email</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="13" class="language-php"><span class="hljs-variable">$email</span> = <span class="hljs-string">"john.doe@example.com"</span>;

<span class="hljs-keyword">if</span> (filter_var(<span class="hljs-variable">$email</span>, FILTER_VALIDATE_EMAIL)) {
  <span class="hljs-keyword">echo</span>(<span class="hljs-string">"$email is a valid email address"</span>);
} <span class="hljs-keyword">else</span> {
  <span class="hljs-keyword">echo</span>(<span class="hljs-string">"$email is not a valid email address"</span>);
}
<span class="hljs-preprocessor">?&gt;</span>
</code></pre>
<p class="has-line-data" data-line-start="14" data-line-end="15"><strong>Filter String</strong></p>
<pre><code class="has-line-data" data-line-start="16" data-line-end="18" class="language-php"><span class="hljs-variable">$password_filter</span> = filter_var(<span class="hljs-variable">$_POST</span>[<span class="hljs-string">'password'</span>], FILTER_SANITIZE_STRING);
</code></pre>
<p class="has-line-data" data-line-start="19" data-line-end="20"><strong>Filter Int</strong></p>
<pre><code class="has-line-data" data-line-start="21" data-line-end="23" class="language-php"><span class="hljs-variable">$password_filter</span> = filter_var(<span class="hljs-variable">$_POST</span>[<span class="hljs-string">'password'</span>], FILTER_SANITIZE_NUMBER_INT);
</code></pre>
<p class="has-line-data" data-line-start="24" data-line-end="25"><strong>Hash Password</strong></p>
<pre><code class="has-line-data" data-line-start="26" data-line-end="28" class="language-php"><span class="hljs-variable">$password_hash</span> = password_hash(password, PASSWORD_BCRYPT);
</code></pre>
<p class="has-line-data" data-line-start="29" data-line-end="30"><strong>Remove special characters</strong></p>
<pre><code class="has-line-data" data-line-start="31" data-line-end="34" class="language-php"><span class="hljs-variable">$new</span> = htmlspecialchars(<span class="hljs-string">"&lt;a href='test'&gt;Test&lt;/a&gt;"</span>, ENT_QUOTES);
<span class="hljs-keyword">echo</span> <span class="hljs-variable">$new</span>; <span class="hljs-comment">// &amp;lt;a href=&amp;#039;test&amp;#039;&amp;gt;Test&amp;lt;/a&amp;gt;</span>
</code></pre>
<p class="has-line-data" data-line-start="35" data-line-end="36"><strong>If empty (If not set or empty)</strong></p>
<pre><code class="has-line-data" data-line-start="37" data-line-end="42" class="language-php"><span class="hljs-keyword">if</span> (<span class="hljs-keyword">empty</span>(<span class="hljs-variable">$_POST</span>[<span class="hljs-string">"vat"</span>])) {
    header(<span class="hljs-string">"location: ../../agency/clients?error={$messages['vat']} {$messages['noinformation']}"</span>);
    <span class="hljs-keyword">return</span> <span class="hljs-keyword">false</span>;
}
</code></pre>
<p class="has-line-data" data-line-start="43" data-line-end="44"><strong>If int is more then</strong></p>
<pre><code class="has-line-data" data-line-start="45" data-line-end="50" class="language-php"><span class="hljs-keyword">if</span> (strlen(<span class="hljs-variable">$_POST</span>[<span class="hljs-string">"adress"</span>]) &gt; <span class="hljs-number">32</span>) {
    header(<span class="hljs-string">"location: ../../agency/clients?error={$messages['address']} {$messages['32chars']}"</span>);
    <span class="hljs-keyword">return</span> <span class="hljs-keyword">false</span>;
}
</code></pre>
<p class="has-line-data" data-line-start="51" data-line-end="52"><strong>Compare Hash Password</strong></p>
<pre><code class="has-line-data" data-line-start="53" data-line-end="59" class="language-php"><span class="hljs-keyword">if</span> (password_verify(<span class="hljs-variable">$password_filter</span>, <span class="hljs-variable">$password</span>)) {
    <span class="hljs-comment">//CODE</span>
} <span class="hljs-keyword">else</span> {
    <span class="hljs-comment">//ERROR</span>
}
</code></pre>