<h2 class="code-line" data-line-start=0 data-line-end=1 ><a id="Database_0"></a>Database</h2>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>Setup Database</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="15" class="language-php"><span class="hljs-preprocessor">&lt;?php</span>
<span class="hljs-comment">// database Logingegevens</span>
<span class="hljs-variable">$db_hostname</span> = <span class="hljs-string">'localhost'</span>; <span class="hljs-comment">//of '127.0.0.1'</span>
<span class="hljs-variable">$db_username</span> = <span class="hljs-string">'root'</span>;
<span class="hljs-variable">$db_password</span> = <span class="hljs-string">''</span>;
<span class="hljs-variable">$db_database</span> = <span class="hljs-string">'snoepkoning'</span>;

<span class="hljs-comment">// maak de database-verbinding</span>
<span class="hljs-variable">$conn</span> = mysqli_connect(<span class="hljs-variable">$db_hostname</span>, <span class="hljs-variable">$db_username</span>, <span class="hljs-variable">$db_password</span>, <span class="hljs-variable">$db_database</span>);
<span class="hljs-preprocessor">?&gt;</span>
</code></pre>