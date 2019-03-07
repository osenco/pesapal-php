# PesaPal PHP SDK
PHP SDK for implementing the PesaPal API.

## Usage
### Installation
include the pesapal.php file in your application
<br>
  `require_once('pesapal.php');`

### Configuration
At the top of your code, configure the Pesapal object
<br>
  `PesaPal::config( $env, $consumer_key, $consumer_secret, $callback_url );`
  
### Payment Form
Create a form with the following fields:
<table>
	<thead>
		<th>Field Name</th>
		<th>Field Type</th>
		<th>Possible/Default Value</th>
	</thead>
	<tbody>
		<tr>
			<td>amount int 100</td>
		</tr>
		<tr>
			<td>type </td>
			<td>string </td>
			<td>MERCHANT</td>
		</tr>
		<tr>
			<td>description </td>
			<td>string </td>
			<td>Order Description</td>
		</tr>
		<tr>
			<td>reference </td>
			<td>mixed string/int </td>
			<td>001</td>
		</tr>
		<tr>
			<td>first_name </td>
			<td>string </td>
			<td>John</td>
		</tr>
		<tr>
			<td>last_name </td>
			<td>string </td>
			<td>Doe</td>
		</tr>
		<tr>
			<td>email </td>
			<td>string </td>
			<td>john@yahoo.com</td>
		</tr>
	</tbody>
</table>
  
### Process Payment
Call the iframe() method where you would like to render the Pesapal iframe
<br>
  `PesaPal::iframe();`

### Process IPN Response
#### Process IPN
Create a function to update your database with payment details - this function must return a boolean (true on success, false on failure). The name of this callback function is passed as an argument to the `process_ipn();` method.
<br>
  `PesaPal::process_ipn( $callback );`
  
## Licencing 
MIT(LICENSE)
