---
layout: docs
title: Properties
prev_section: resourcexml
next_section: posts
permalink: /docs/properties/
---
## Predefined Tokens

CellName is predefined variable. Any extract operation automatically replaces Cell Name with a token

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <p><code>CellName</code></p>
      </td>
      <td>
        <p>

		Name of the cell
        </p>
        <p><code>CellName=MyCell</code></p>
      </td>
    </tr>
  </tbody>
</table>
</div>

## Common Properties
"_import" allows the user to import property file. This can be useful if there are common properties across the environments 
or if properties file is too big to manage then it can be broken in small files.

							
	<code>_import=common.properties</code>
	 
## Name and location

Create properties file under the properties directory. The name of this property file should same as the name specified in the
 env.name value passed from command line. For e.g. if the value of emv.name is vm-04 the properties file name should be vm-04.properties

