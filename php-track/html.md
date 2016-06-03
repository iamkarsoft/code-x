### Tables

##### example

```
<table>
	//table row
	<tr>
		//table cells
		<td>Name</td>
		<td>E-mail</td>
		<td>Job role</td>
	</tr>
	<tr>
		//table cells
		<td>Kofi Ramose</td>
		<td>koofi@kofi.work</td>
		<td>Cook / Web Developer</td>
	</tr>

</table>
```

##### Styling first row to become table heads 


```
<table>

	//table row
	<tr>
		//table cells
		<th>Name</th>
		<th>E-mail</th>
		<th>Job role</th>
	</tr>
	<tr>
		//table cells
		<td>Kofi Ramose</td>
		<td>koofi@kofi.work</td>
		<td>Cook / Web Developer</td>
	</tr>

</table>
```

##### defining table heads

- scope is used to define table and head by row or column. the attribute scope ="row" for row or scope="col" for columns

```
<table>

	//table row
	<tr>
		//table cells
		<th scope="col">Name</th>
		<th scope="col">E-mail</th>
		<th scope="col">Job role</th>
	</tr>
	<tr>
		//table cells
		<th scope="row">Kofi Ramose</th>
		<td>koofi@kofi.work</td>
		<td>Cook / Web Developer</td>
	</tr>

</table>
```

##### Adding a tabel head,body and footer


```
<table>

	<thead>
			//table row
			<tr>
				//table cells
				<th scope="col">Name</th>
				<th scope="col">E-mail</th>
				<th scope="col">Job role</th>
			</tr>
	</thead>

	//table footer
	<tfoot>
		<tr>
			<td colspan="3">Data is updated every 15 minutes</td>
		</tr>
	</tfoot>

	<tbody>
			<tr>
				//table cells
				<th scope="row">Kofi Ramose</th>
				<td>koofi@kofi.work</td>
				<td>Cook / Web Developer</td>
			</tr>
	</tbody>

</table>
```

##### Caption element for table 


```
<table>
	<caption>Employee Information</caption>
	<thead>
			//table row
			<tr>
				//table cells
				<th scope="col">Name</th>
				<th scope="col">E-mail</th>
				<th scope="col">Job role</th>
			</tr>
	</thead>

	//table footer
	<tfoot>
		<tr>
			<td colspan="3">Data is updated every 15 minutes</td>
		</tr>
	</tfoot>

	<tbody>
			<tr>
				//table cells
				<th scope="row">Kofi Ramose</th>
				<td>koofi@kofi.work</td>
				<td>Cook / Web Developer</td>
			</tr>
	</tbody>

</table>
```

