# Get all colors from CSS file (BASH Script)
![CSS COLOR](https://raw.githubusercontent.com/mnbarinov/get_all_colors_from_css_file_script/main/csscolor.png)<br />
Get all colors from CSS file

<h2>Dependencies</h2>
<ol>
  <li><h3>Curl</h3>
    <code>sudo apt -y install curl</code>    
  </li>
</ol>
<h2>Create and Install</h2>
<ol>
  <li>
<p>
Create bash script:<br />
<code>nano csscolor.sh</code>
</p>
 </li>
 <li>
<p>
Insert code<br />
<code>
#!/bin/bash
</code><br />
<code>
curl -s $1 | egrep -oh "rgb(a){0,1}\([0-9]{1,3},(\s){0,1}[0-9]{1,3},(\s){0,1}[0-9]{1,3}((\,){0,1}(\s){0,1}(\.){0,1}[0-9]{1,3}){0,1}(\%){0,1}\);"\|"(#[0-9a-fA-F]{3,6};)"\|"(hls\([0-9]{1,3},(\s){0,1}[0-9]{1,3}\%,(\s){0,1}[1-9]{1,3}\%\);)" | sort | uniq
</code>
</p>
</li>
<li>
  <p>
    Save<br />
    <code>ctrl+o ENTER</code>
  </p>
</li>
<li>
  <p>
  Change the access permissions<br />
    <code>
      sudo chmod +x csscolor.sh
    </code>
  </p>
</li>
<li>
  <p>Installation<br />
    <code>
      cp csscolor.sh /usr/bin/csscolor
    </code>
  </p>
</li>
</ol>
  
<h2>How to use</h2>
<p>
  <b>Command:</b><br />
<code>csscolor https://github.githubassets.com/assets/github-6b25e59bc074.css</code></p>
<p><b>Result:</b><br />
<pre>
<code>
#000;
#1d7fb3;
#1db34f;
#1e7e34;
#256aae;
#2cbe4e;
...
...
</code>
</pre>
</p>
