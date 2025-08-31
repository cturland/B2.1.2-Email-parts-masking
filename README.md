<h2>2) Core — Email parts &amp; masking (find/split/replace + slicing)</h2>
<p><strong>Goal:</strong> Extract parts of a string, then manipulate a substring.</p>

<h3>Task</h3>
<ol>
  <li>Ask the user for an email address.</li>
  <li>Print:
    <ol type="a">
      <li>The <strong>local part</strong> (before <code>@</code>)</li>
      <li>The <strong>domain</strong> (after <code>@</code>)</li>
      <li>A <strong>masked</strong> version where only the <strong>first and last</strong> characters of the local part are shown; every middle character becomes <code>*</code>. Keep the domain unchanged.</li>
    </ol>
  </li>
</ol>

<h3>Rules / edge cases</h3>
<ul>
  <li>Assume there is exactly one <code>@</code>.</li>
  <li>If the local part length is 1, show it unchanged (no stars).</li>
  <li>If the local part length is 2, show both characters unchanged (no stars).</li>
</ul>

<h3>Examples</h3>
<pre><code>Input:   alex.mason@school.ch
Local:   alex.mason
Domain:  school.ch
Masked:  a********n@school.ch
</code></pre>

<pre><code>Input:   ab@site.com
Masked:  ab@site.com
</code></pre>

<details>
  <summary><strong>Hints</strong></summary>
  <ul>
    <li>Find <code>@</code> via <code>at = email.index('@')</code> (or <code>.find()</code>).</li>
    <li>Local → <code>email[:at]</code>, domain → <code>email[at+1:]</code>.</li>
    <li>Middle mask: <code>"*" * (len(local) - 2)</code></li>
  </ul>
</details>
