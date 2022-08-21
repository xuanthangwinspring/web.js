# web-shortcode.js
Shortcode
<article class="markdown-body entry-content container-lg" itemprop="text"><h1 dir="auto"><a id="user-content-shortcodejs" class="anchor" aria-hidden="true" href="#shortcodejs"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a><a href="https://github.com/xuanthangwinspring/web-shortcode.js/">web-shortcode.js</a></h1>
<p dir="auto">Replace <a href="http://codex.wordpress.org/Shortcode" rel="nofollow">Wordpress-style shortcodes</a> with anything. No dependencies required.</p>
<h2 dir="auto"><a id="user-content-usage" class="anchor" aria-hidden="true" href="#usage"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Usage</h2>
<p dir="auto"><code>Shortcode</code> accepts 2 arguments: an element, and an object of tags to match.</p>
<p dir="auto">Each tag method returns a string to replace the original tag (in the DOM) and accepts an (optional) asynchronous callback. <code>this</code> is bound to the match object.</p>
<div class="highlight highlight-source-js notranslate position-relative overflow-auto"><pre><span class="pl-c">/* Replaces [hello text="Hello world"] in `body` with "Hello world" */</span>
<span class="pl-k">new</span> <span class="pl-v">Shortcode</span><span class="pl-kos">(</span><span class="pl-smi">document</span><span class="pl-kos">.</span><span class="pl-en">querySelector</span><span class="pl-kos">(</span><span class="pl-s">'body'</span><span class="pl-kos">)</span><span class="pl-kos">,</span> <span class="pl-kos">{</span>
  <span class="pl-en">hello</span>: <span class="pl-k">function</span><span class="pl-kos">(</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
    <span class="pl-k">return</span> <span class="pl-smi">this</span><span class="pl-kos">.</span><span class="pl-c1">options</span><span class="pl-kos">.</span><span class="pl-c1">text</span><span class="pl-kos">;</span>
  <span class="pl-kos">}</span>
<span class="pl-kos">}</span><span class="pl-kos">)</span><span class="pl-kos">;</span></pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="/* Replaces [hello text=&quot;Hello world&quot;] in `body` with &quot;Hello world&quot; */
new Shortcode(document.querySelector('body'), {
  hello: function() {
    return this.options.text;
  }
});" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path fill-rule="evenodd" d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 010 1.5h-1.5a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-1.5a.75.75 0 011.5 0v1.5A1.75 1.75 0 019.25 16h-7.5A1.75 1.75 0 010 14.25v-7.5z"></path><path fill-rule="evenodd" d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0114.25 11h-7.5A1.75 1.75 0 015 9.25v-7.5zm1.75-.25a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-7.5a.25.25 0 00-.25-.25h-7.5z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto">Tip: Because shortcode replaces an element's html, you will lose existing event bindings inside that element. Use delegated bindings where possible and call shortcode at the start of your code.</p>
<h2 dir="auto"><a id="user-content-features" class="anchor" aria-hidden="true" href="#features"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Features</h2>
<ul dir="auto">
<li>Supports multiple tag instances</li>
<li>Supports single and start-end tags</li>
<li>Supports multi-line tags</li>
<li>Supports asynchronous callbacks</li>
<li>Supports DOM or jQuery selectors</li>
<li>Includes jQuery plugin definition</li>
<li>Ignores tags inside <code>pre</code> and <code>code</code></li>
<li>Tested with Jasmine</li>
</ul>
<h2 dir="auto"><a id="user-content-supported-browsers" class="anchor" aria-hidden="true" href="#supported-browsers"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Supported browsers</h2>
<p dir="auto">Shortcode.js should work in any browser that supports <code>Function.prototype.bind</code> (Sorry IE7 &amp; 8). If you need to support &lt;IE9, try the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind#Compatibility" rel="nofollow">polyfill published in MDN</a>.</p>
<h2 dir="auto"><a id="user-content-using-async" class="anchor" aria-hidden="true" href="#using-async"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Using async</h2>
<p dir="auto">Sometimes you need to do asynchronous work. Don't return anything from the shortcode method. Instead, call <code>done</code> with your return value to update the DOM.</p>
<div class="highlight highlight-source-js notranslate position-relative overflow-auto"><pre><span class="pl-k">new</span> <span class="pl-v">Shortcode</span><span class="pl-kos">(</span><span class="pl-smi">document</span><span class="pl-kos">.</span><span class="pl-en">querySelector</span><span class="pl-kos">(</span><span class="pl-s">'body'</span><span class="pl-kos">)</span><span class="pl-kos">,</span> <span class="pl-kos">{</span>
  <span class="pl-en">hello</span>: <span class="pl-k">function</span><span class="pl-kos">(</span><span class="pl-s1">done</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
    <span class="pl-k">var</span> <span class="pl-s1">self</span> <span class="pl-c1">=</span> <span class="pl-smi">this</span><span class="pl-kos">;</span>

    <span class="pl-c">/* setTimeout is used here to simulate an async event */</span>
    <span class="pl-en">setTimeout</span><span class="pl-kos">(</span><span class="pl-k">function</span><span class="pl-kos">(</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
      <span class="pl-s1">done</span><span class="pl-kos">(</span><span class="pl-s1">self</span><span class="pl-kos">.</span><span class="pl-c1">options</span><span class="pl-kos">.</span><span class="pl-c1">text</span><span class="pl-kos">)</span><span class="pl-kos">;</span>
    <span class="pl-kos">}</span><span class="pl-kos">,</span> <span class="pl-c1">1000</span><span class="pl-kos">)</span><span class="pl-kos">;</span>
  <span class="pl-kos">}</span>
<span class="pl-kos">}</span><span class="pl-kos">)</span><span class="pl-kos">;</span></pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="new Shortcode(document.querySelector('body'), {
  hello: function(done) {
    var self = this;

    /* setTimeout is used here to simulate an async event */
    setTimeout(function() {
      done(self.options.text);
    }, 1000);
  }
});" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path fill-rule="evenodd" d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 010 1.5h-1.5a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-1.5a.75.75 0 011.5 0v1.5A1.75 1.75 0 019.25 16h-7.5A1.75 1.75 0 010 14.25v-7.5z"></path><path fill-rule="evenodd" d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0114.25 11h-7.5A1.75 1.75 0 015 9.25v-7.5zm1.75-.25a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-7.5a.25.25 0 00-.25-.25h-7.5z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h2 dir="auto"><a id="user-content-start-and-end-tags" class="anchor" aria-hidden="true" href="#start-and-end-tags"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Start and end tags</h2>
<p dir="auto">Shortcode.js supports tags like <code>[note]This is a note[/note]</code>. The content between tags will be availble in your callback under <code>this.contents</code>.</p>
<div class="highlight highlight-source-js notranslate position-relative overflow-auto"><pre><span class="pl-k">new</span> <span class="pl-v">Shortcode</span><span class="pl-kos">(</span><span class="pl-smi">document</span><span class="pl-kos">.</span><span class="pl-en">querySelector</span><span class="pl-kos">(</span><span class="pl-s">'body'</span><span class="pl-kos">)</span><span class="pl-kos">,</span> <span class="pl-kos">{</span>
  <span class="pl-en">note</span>: <span class="pl-k">function</span><span class="pl-kos">(</span><span class="pl-s1">done</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
    <span class="pl-k">return</span> <span class="pl-smi">this</span><span class="pl-kos">.</span><span class="pl-c1">contents</span><span class="pl-kos">;</span>
  <span class="pl-kos">}</span>
<span class="pl-kos">}</span><span class="pl-kos">)</span><span class="pl-kos">;</span></pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="new Shortcode(document.querySelector('body'), {
  note: function(done) {
    return this.contents;
  }
});" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path fill-rule="evenodd" d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 010 1.5h-1.5a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-1.5a.75.75 0 011.5 0v1.5A1.75 1.75 0 019.25 16h-7.5A1.75 1.75 0 010 14.25v-7.5z"></path><path fill-rule="evenodd" d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0114.25 11h-7.5A1.75 1.75 0 015 9.25v-7.5zm1.75-.25a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-7.5a.25.25 0 00-.25-.25h-7.5z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h2 dir="auto"><a id="user-content-jquery" class="anchor" aria-hidden="true" href="#jquery"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>jQuery</h2>
<p dir="auto">While shortcode.js doesn't rely on jQuery, you may find it convenient to use. Shortcode can accept a jQuery object or a DOM object as the first argument.</p>
<p dir="auto">Alternatively, a jQuery plugin wrapper is supplied.</p>
<div class="highlight highlight-source-js notranslate position-relative overflow-auto"><pre><span class="pl-en">$</span><span class="pl-kos">(</span><span class="pl-s">'body'</span><span class="pl-kos">)</span><span class="pl-kos">.</span><span class="pl-en">shortcode</span><span class="pl-kos">(</span><span class="pl-kos">{</span>
  <span class="pl-en">hello</span>: <span class="pl-k">function</span><span class="pl-kos">(</span><span class="pl-kos">)</span> <span class="pl-kos">{</span>
    <span class="pl-k">return</span> <span class="pl-smi">this</span><span class="pl-kos">.</span><span class="pl-c1">options</span><span class="pl-kos">.</span><span class="pl-c1">text</span><span class="pl-kos">;</span>
  <span class="pl-kos">}</span>
<span class="pl-kos">}</span><span class="pl-kos">)</span><span class="pl-kos">;</span></pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="$('body').shortcode({
  hello: function() {
    return this.options.text;
  }
});" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path fill-rule="evenodd" d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 010 1.5h-1.5a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-1.5a.75.75 0 011.5 0v1.5A1.75 1.75 0 019.25 16h-7.5A1.75 1.75 0 010 14.25v-7.5z"></path><path fill-rule="evenodd" d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0114.25 11h-7.5A1.75 1.75 0 015 9.25v-7.5zm1.75-.25a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-7.5a.25.25 0 00-.25-.25h-7.5z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h2 dir="auto"><a id="user-content-releases" class="anchor" aria-hidden="true" href="#releases"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Releases</h2>
<p dir="auto">See <a href="https://github.com/xuanthangwinspring/shortcode.js/releases">Releases</a> for current version and release notes.</p>
<h2 dir="auto"><a id="user-content-contributing-and-dev-setup" class="anchor" aria-hidden="true" href="#contributing-and-dev-setup"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Contributing and dev setup</h2>
<p dir="auto">See <code>CONTRIBUTING.md</code></p>
<h2 dir="auto"><a id="user-content-license" class="anchor" aria-hidden="true" href="#license"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>License</h2>
<p dir="auto">MIT (c) 2014 Nic Aitch</p>
</article>
