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
  <th>&nbsp;</th><th><h4>Full</h4></th><th><h4>Partial</h4></th><th><h4>Pure</h4></th>
</tr>
<tr>
  <th>Aspect</th><th colspan="3">Deployment</th>
</tr>  
<tr>
  <th>May break by network disconnect</th><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <th>May break by dep. repo removal</th><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <th>Is fast</th><td>yes (+)</td><td>yes (+)</td><td>no</td>
</tr>  
<tr>
  <td colspan="4"></td>
</tr>  

<tr>
  <th>Aspect</th><th colspan="3">Unsyncs</th>
</tr>  
<tr>
  <th>Between sources and dists</th>
  <td>high probability (-)</td>
  <td>low probability</td>
  <td>zero probability (+)</td>
</tr>
<tr>
  <th>Between tested and installed dependency version</th>
  <td>impossible (+)</td>
  <td>impossible (+)</td>
  <td>possible (*)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>

<tr>
  <th>Aspect</th><th colspan="3">Tags / versions</th>
</tr>  
<tr>
  <th>Are locked</th><td>no (+)</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>

<tr>
  <th>Aspect</th><th colspan="3">History</th>
</tr> 
<tr>
  <th>Big commits</th><td>yes</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <th>Big repo</th><td>yes</td><td>yes</td><td>no (+)</td>
</tr>
<tr>
  <td colspan="4"></td>
</tr>
</table>

### Aspects

All projects may be roughly divided into apps and libs.

#### Deployment
Critical to apps. Agnostic to libs.

#### Unsyncs
Cricital to both apps and libs as may lead to broken commits.
(*) – unsyncs between tested and installed dependency version may be
prevented by strict version pinning.

#### Tags versions
Medium importance to both apps and libs.

#### History
Bigger history increases disk and network traffic usage. Probably is more critical to apps
considering their commit number is usually bigger in order(s) of magnitude.
