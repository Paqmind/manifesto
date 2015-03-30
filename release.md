# Release questions

## Build folders and VCS

### Full
Builds are under VCS.
Every commit must include corresponding build changes (if there are).

### Partial 
Builds are under VCS.
Every release must include corresponding build changes.

### Pure 
Builds are out of VCS.
Fetches and builds are performed as part of install / update process.

<table>
<tr>
  <th>&nbsp;</th><th><h4>Full</h4></th><th><h4>Partial</h4></th><th><h4>Pure</h4></th>
</tr>
<tr>
  <th>Deployment depends on network connection</th><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
<tr>
  <th>Deployment depends on 3-rd party package repos existance</th><td>no (+)</td><td>no (+)</td><td>yes</td>
</tr>  
</table>

