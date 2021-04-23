<h1 class="code-line" data-line-start=0 data-line-end=1 ><a id="Prepared_Statement_0"></a>Prepared Statement</h1>
<p class="has-line-data" data-line-start="2" data-line-end="3"><strong>Select</strong></p>
<pre><code class="has-line-data" data-line-start="4" data-line-end="11" class="language-php"><span class="hljs-variable">$stmt</span> = <span class="hljs-variable">$conn</span>-&gt;prepare(<span class="hljs-string">"SELECT id, admin, password FROM users WHERE username = ?"</span>);
<span class="hljs-variable">$stmt</span>-&gt;bind_param(<span class="hljs-string">"s"</span>, <span class="hljs-variable">$username</span>);
<span class="hljs-variable">$stmt</span>-&gt;execute();
<span class="hljs-variable">$stmt</span>-&gt;bind_result(<span class="hljs-variable">$id</span>, <span class="hljs-variable">$isadmin</span>, <span class="hljs-variable">$password_filter</span>);
<span class="hljs-variable">$stmt</span>-&gt;fetch();
<span class="hljs-variable">$stmt</span>-&gt;close();
</code></pre>
<p class="has-line-data" data-line-start="12" data-line-end="13"><strong>Insert</strong></p>
<pre><code class="has-line-data" data-line-start="14" data-line-end="19" class="language-php"><span class="hljs-variable">$stmt</span> = <span class="hljs-variable">$conn</span>-&gt;prepare(<span class="hljs-string">"INSERT INTO clients (organization, firstname, lastname, telephone, email, password) VALUES (?, ?,?,?,?,?)"</span>);
<span class="hljs-variable">$stmt</span>-&gt;bind_param(<span class="hljs-string">"isssss"</span>, <span class="hljs-variable">$orgid</span>, <span class="hljs-variable">$firstname</span>, <span class="hljs-variable">$lastname</span>, <span class="hljs-variable">$telephone</span>, <span class="hljs-variable">$email</span>, <span class="hljs-variable">$password</span>);
<span class="hljs-variable">$stmt</span>-&gt;execute();
<span class="hljs-variable">$stmt</span>-&gt;close();
</code></pre>
<p class="has-line-data" data-line-start="20" data-line-end="21"><strong>Update</strong></p>
<pre><code class="has-line-data" data-line-start="22" data-line-end="27" class="language-php"><span class="hljs-variable">$stmt</span> = <span class="hljs-variable">$conn</span>-&gt;prepare(<span class="hljs-string">"UPDATE clients SET firstname = ?, lastname = ?, telephone = ?, email = ? WHERE id = ?"</span>);
<span class="hljs-variable">$stmt</span>-&gt;bind_param(<span class="hljs-string">"ssssi"</span>, <span class="hljs-variable">$firstname</span>, <span class="hljs-variable">$lastname</span>, <span class="hljs-variable">$telephone</span>, <span class="hljs-variable">$email</span>, <span class="hljs-variable">$userid</span>);
<span class="hljs-variable">$stmt</span>-&gt;execute();
<span class="hljs-variable">$stmt</span>-&gt;close();
</code></pre>
<p class="has-line-data" data-line-start="28" data-line-end="29"><strong>Delete</strong></p>
<pre><code class="has-line-data" data-line-start="30" data-line-end="35" class="language-php"><span class="hljs-variable">$stmt</span> = <span class="hljs-variable">$conn</span>-&gt;prepare(<span class="hljs-string">"DELETE FROM members WHERE email=?"</span>);
<span class="hljs-variable">$stmt</span>-&gt;bind_param(<span class="hljs-string">"s"</span>, <span class="hljs-variable">$email</span>);
<span class="hljs-variable">$stmt</span>-&gt;execute();
<span class="hljs-variable">$stmt</span>-&gt;close();
</code></pre>