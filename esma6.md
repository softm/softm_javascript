# ECMA6
##### [source : https://jsfiddle.net/softm/vcrfj2tu/ ](https://jsfiddle.net/softm/vcrfj2tu/)

<pre>
<span style="font-family: Consolas">
<span style="color: #000000">※ 참고 : https:</span><span style="color: #008000">//www.sitepoint.com/javascript-versioning-es6-es2015</span>

<span style="color: #000000"># ECMAScript </span><span style="color: #800080">2015 </span><span style="color: #000000">Releases</span>
   <span style="color: #000000">- Classes</span>
   <span style="color: #000000">- Promises</span>
   <span style="color: #000000">- Arrow functions</span>
   <span style="color: #000000">- ES Modules</span>
   <span style="color: #000000">- Generators and Iterators</span>

<span style="color: #000000"># ES2016</span>
   <span style="color: #000000">- </span><span style="color: #ff0000">Array</span><span style="color: #000000">.prototype.includes</span>
        <span style="color: #008000">// pre-ES2016:</span>
        <span style="color: #0000ff">const </span><span style="color: #000000">hasBob = names.indexOf(</span><span style="color: #ff00ff">'bob'</span><span style="color: #000000">) &gt; -</span><span style="color: #800080">1</span><span style="color: #000000">;</span>

        <span style="color: #008000">// ES2016:</span>
        <span style="color: #0000ff">const </span><span style="color: #000000">hasBob = names.includes(</span><span style="color: #ff00ff">'bob'</span><span style="color: #000000">);</span>

   <span style="color: #000000">- Exponent Operator</span>
        <span style="color: #008000">// pre-ES2016</span>
        <span style="color: #ff0000">Math</span><span style="color: #000000">.pow(</span><span style="color: #800080">5</span><span style="color: #000000">, </span><span style="color: #800080">3</span><span style="color: #000000">); </span><span style="color: #008000">// =&gt; 125</span>

        <span style="color: #008000">// ES2016</span>
        <span style="color: #800080">5 </span><span style="color: #000000">** </span><span style="color: #800080">3</span><span style="color: #000000">; </span><span style="color: #008000">// =&gt; 125</span>

<span style="color: #000000"># ES2017</span>
    <span style="color: #000000">- Asynchronous Functions</span>
        <span style="color: #008000">// promises</span>
        <span style="color: #0000ff">const </span><span style="color: #000000">getProfile = name =&gt; {</span>
          <span style="color: #0000ff">return </span><span style="color: #000000">fetch(`https:</span><span style="color: #008000">//some-api/people/${name}`)</span>
            <span style="color: #000000">.then(res =&gt; res.json())</span>
            <span style="color: #000000">.then(({ profile }) =&gt; profile); </span><span style="color: #008000">// destructuring `profile` from parsed object</span>
        <span style="color: #000000">};</span>

        <span style="color: #008000">// async/await</span>
        <span style="color: #0000ff">const </span><span style="color: #000000">getProfile = async name =&gt; {</span>
          <span style="color: #0000ff">const </span><span style="color: #000000">res = await fetch(`https:</span><span style="color: #008000">//some-api/people/${name}`);</span>
          <span style="color: #0000ff">const </span><span style="color: #000000">{ profile } = await res.json();</span>
          <span style="color: #0000ff">return </span><span style="color: #000000">profile;</span>
        <span style="color: #000000">};</span>

   <span style="color: #000000">- </span><span style="color: #ff0000">String </span><span style="color: #000000">Padding Methods</span>
     <span style="color: #ff0000">String</span><span style="color: #000000">.prototype.padStart(length, padder) and padEnd(length, padder) will</span>

    <span style="color: #ff00ff">'foo'</span><span style="color: #000000">.padStart(</span><span style="color: #800080">6</span><span style="color: #000000">);          </span><span style="color: #008000">// =&gt; '   foo';</span>
    <span style="color: #ff00ff">'foo'</span><span style="color: #000000">.padEnd(</span><span style="color: #800080">6</span><span style="color: #000000">);            </span><span style="color: #008000">// =&gt; 'foo   ';</span>
    <span style="color: #ff00ff">'foo'</span><span style="color: #000000">.padStart(</span><span style="color: #800080">10</span><span style="color: #000000">, </span><span style="color: #ff00ff">'bar'</span><span style="color: #000000">);  </span><span style="color: #008000">// =&gt; 'barbarbfoo';</span>
    <span style="color: #ff00ff">'foo'</span><span style="color: #000000">.padEnd(</span><span style="color: #800080">10</span><span style="color: #000000">, </span><span style="color: #ff00ff">'bar'</span><span style="color: #000000">);    </span><span style="color: #008000">// =&gt; 'foobarbarb';</span>

<span style="color: #000000"># ES2018</span>
   <span style="color: #000000">- Asynchronous Iterators</span>
    <span style="color: #000000">While Promise.all() allows you to await the resolution of multiple promises,</span>
    <span style="color: #000000">there are cases </span><span style="color: #0000ff">in </span><span style="color: #000000">which you may need to sequentially iterate over asynchronously-retrieved values.</span>
    <span style="color: #000000">It’s now possible to await async iterators along </span><span style="color: #0000ff">with </span><span style="color: #000000">arrays of promises:</span>

    <span style="color: #000000">(async () =&gt; {</span>
      <span style="color: #0000ff">const </span><span style="color: #000000">personRequests = [</span><span style="color: #ff00ff">'bob'</span><span style="color: #000000">, </span><span style="color: #ff00ff">'sarah'</span><span style="color: #000000">, </span><span style="color: #ff00ff">'laura'</span><span style="color: #000000">].map(</span>
        <span style="color: #000000">n =&gt; fetch(`https:</span><span style="color: #008000">//api/people/${n}`)</span>
      <span style="color: #000000">);</span>

      <span style="color: #0000ff">for </span><span style="color: #000000">await (</span><span style="color: #0000ff">const </span><span style="color: #000000">response of personRequests) {</span>
        <span style="color: #000000">console.log(await response.json());</span>
      <span style="color: #000000">}</span>
    <span style="color: #000000">})();</span>

   <span style="color: #000000">- Object Spread and Rest Properties</span>
     <span style="color: #000000">함수 호출 용            : myFunction(...iterableObj);</span>
     <span style="color: #000000">배열 리터럴 용          : [...iterableObj, </span><span style="color: #800080">4</span><span style="color: #000000">, </span><span style="color: #800080">5</span><span style="color: #000000">, </span><span style="color: #800080">6</span><span style="color: #000000">]</span>
     <span style="color: #000000">비구조화destructuring 용:[a, b, ...iterableObj] = [</span><span style="color: #800080">1</span><span style="color: #000000">, </span><span style="color: #800080">2</span><span style="color: #000000">, </span><span style="color: #800080">3</span><span style="color: #000000">, </span><span style="color: #800080">4</span><span style="color: #000000">, </span><span style="color: #800080">5</span><span style="color: #000000">];</span>

<span style="color: #000000"># 참고</span>
    <span style="color: #000000">:: [JavaScript] ES6 문법 정리</span>
        <span style="color: #000000">※ 원본 : https:</span><span style="color: #008000">//github.com/lukehoban/es6features</span>
        <span style="color: #000000">※ 출처 : http:</span><span style="color: #008000">//itstory.tk/entry/JavaScript-ES6-문법-정리#arrows [덕's IT Story]</span>
</span>
</pre>


<pre id="contents">
※ 참고 : https://www.sitepoint.com/javascript-versioning-es6-es2015

# ECMAScript 2015 Releases
   - Classes
   - Promises
   - Arrow functions
   - ES Modules
   - Generators and Iterators

# ES2016
   - Array.prototype.includes
        // pre-ES2016:
        const hasBob = names.indexOf('bob') > -1;

        // ES2016:
        const hasBob = names.includes('bob');

   - Exponent Operator
        // pre-ES2016
        Math.pow(5, 3); // => 125

        // ES2016
        5 ** 3; // => 125

# ES2017
    - Asynchronous Functions
        // promises
        const getProfile = name => {
          return fetch(`https://some-api/people/${name}`)
            .then(res => res.json())
            .then(({ profile }) => profile); // destructuring `profile` from parsed object
        };

        // async/await
        const getProfile = async name => {
          const res = await fetch(`https://some-api/people/${name}`);
          const { profile } = await res.json();
          return profile;
        };

   - String Padding Methods
     String.prototype.padStart(length, padder) and padEnd(length, padder) will

    'foo'.padStart(6);          // => '   foo';
    'foo'.padEnd(6);            // => 'foo   ';
    'foo'.padStart(10, 'bar');  // => 'barbarbfoo';
    'foo'.padEnd(10, 'bar');    // => 'foobarbarb';

# ES2018
   - Asynchronous Iterators
    While Promise.all() allows you to await the resolution of multiple promises,
    there are cases in which you may need to sequentially iterate over asynchronously-retrieved values.
    It’s now possible to await async iterators along with arrays of promises:

    (async () => {
      const personRequests = ['bob', 'sarah', 'laura'].map(
        n => fetch(`https://api/people/${n}`)
      );

      for await (const response of personRequests) {
        console.log(await response.json());
      }
    })();

   - Object Spread and Rest Properties
     함수 호출 용            : myFunction(...iterableObj);
     배열 리터럴 용          : [...iterableObj, 4, 5, 6]
     비구조화destructuring 용:[a, b, ...iterableObj] = [1, 2, 3, 4, 5];

# 참고
    :: [JavaScript] ES6 문법 정리
        ※ 원본 : https://github.com/lukehoban/es6features
        ※ 출처 : http://itstory.tk/entry/JavaScript-ES6-문법-정리#arrows [덕's IT Story]

</pre>

<script>
function autolink(doc) {
  //var container = document.getElementById(id);
  //var doc = container.innerHTML;
  var regURL = new RegExp("(http|https|ftp|telnet|news|irc)://([-/.a-zA-Z0-9_~#%$?&=:200-377()]+)","gi");
  var regEmail = new RegExp("([xA1-xFEa-z0-9_-]+@[xA1-xFEa-z0-9-]+\.[a-z0-9-]+)","gi");
  return doc.replace(regURL,"<a href='$1://$2' target='_blank'>$1://$2</a>").replace(regEmail,"<a href='mailto:$1'>$1</a>");
}

window.onload = function () {
/* console.log(document.getElementsByTagName("pre")) */
  var containers = document.getElementsByTagName("pre");
  //var container = document.getElementById("contents");  
  for ( var i=0;i<containers.length;i++) {
  	console.log(containers[i].innerHTML);
  	containers[i].innerHTML = autolink(containers[i].innerHTML);
  }
  
}
</script>
