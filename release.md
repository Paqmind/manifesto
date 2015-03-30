# Release questions

## Build folders and VCS

### Options

#### Full
Builds are under VCS.
Every commit must include corresponding build changes (if there are).

#### Partial 
Builds are under VCS.
Every release must include corresponding build changes.

#### Pure 
Builds are out of VCS.
Fetches and builds are performed as part of install / update process.

<table>
<tr>
  <th>Aspect</th><th><h4>Full</h4></th><th><h4>Partial</h4></th><th><h4>Pure</h4></th>
</tr>

<tr>
  <th>&nbsp;</th><th colspan="3">Development</th>
</tr>  
<tr>
  <td><code>$ git add -p</code> is complicated</td><td>yes (-)</td><td>kinda</td><td>no (+)</td>
  <td>Every member must have dev. tools installed</td><td>no (+)</td><td>maybe</td><td>yes (-)</td>
</tr>  
<tr>
  <td colspan="4"></td>
</tr>  

<tr>
  <th>&nbsp;</th><th colspan="3">Deployment</th>
</tr>  
<tr>
  <td>Is complicated</td><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <td>May break by network disconnect</td><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <td>May break by dep. repo removal</td><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <td>Is fast</td><td>yes (+)</td><td>yes (+)</td><td>no</td>
</tr>  
<tr>
  <td colspan="4"></td>
</tr>  

<tr>
  <th>&nbsp;</th><th colspan="3">Broken commits</th>
</tr>  
<tr>
  <td>Sources and dists are unsynced</td>
  <td>high probability (-)</td>
  <td>low probability</td>
  <td>zero probability (+)</td>
</tr>
<tr>
  <td>Installation of untested dep. version</td>
  <td>impossible (+)</td>
  <td>impossible (+)</td>
  <td>possible (*)</td>
</tr>
<tr>
  <td>Incompatible binaries</td>
  <td>possible</td>
  <td>possible</td>
  <td>impossible (+)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>

<tr>
  <th>&nbsp;</th><th colspan="3">Tags / versions</th>
</tr>  
<tr>
  <td>Are locked</td><td>no (+)</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>

<tr>
  <th>&nbsp;</th><th colspan="3">History</th>
</tr> 
<tr>
  <td>Big commits</td><td>yes</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <td>Big repo</td><td>yes</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>
</table>

### Aspects

All projects may be roughly divided into apps and libs.

#### Development
Critical to both apps and libs.

#### Deployment
Critical to apps. Agnostic to libs.

#### Broken commits
Cricital to both apps and libs.
(*) – unsyncs between tested and installed dependency version may be
prevented to some degree by strict version pinning (deps of deps may be [impossible to lock](https://github.com/bower/bower/pull/1592), TODO: describe NPM & Bower current state of this)

#### Tags versions
Medium importance to both apps and libs.

#### History
Bigger history increases disk and network traffic usage. Probably is more critical to apps
considering their commit number is usually bigger in order(s) of magnitude.
