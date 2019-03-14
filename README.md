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
  <table>
	<thead>
		<th>Parameter Name</th>
		<th>Parameter Description</th>
		<th>Parameter Type</th>
		<th>Possible/Default Value</th>
	</thead>
	<tbody>
		<tr>
			<td>$env</td>
			<td>System Environment</td>
			<td>string</td>
			<td>sandbox/live</td>
		</tr>
		<tr>
			<td>$consumer_key</td>
			<td>Pesapal Consumer Key</td>
			<td>string </td>
			<td>behdklejdkjdw</td>
		</tr>
		<tr>
			<td>$consumer_secret</td>
			<td>Pesapal Consumer Secret</td>
			<td>string </td>
			<td>ncjdbckdcdhcjdcvjldhckadlxhska</td>
		</tr>
		<tr>
			<td>$callback_url</td>
			<td>Site Callback Endpoint/Link</td>
			<td>string </td>
			<td>https://yoursiteurl.tld/process_ipn</td>
		</tr>
	</tbody>
</table>
  
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
			<td>amount</td>
			<td>number/text</td>
			<td>100</td>
		</tr>
		<tr>
			<td>type </td>
			<td>text</td>
			<td>MERCHANT</td>
		</tr>
		<tr>
			<td>description </td>
			<td>text</td>
			<td>Order Description</td>
		</tr>
		<tr>
			<td>reference </td>
			<td>number/text</td>
			<td>001</td>
		</tr>
		<tr>
			<td>first_name </td>
			<td>text</td>
			<td>John</td>
		</tr>
		<tr>
			<td>last_name </td>
			<td>text</td>
			<td>Doe</td>
		</tr>
		<tr>
			<td>email </td>
			<td>email</td>
			<td>john@yahoo.com</td>
		</tr>
		<tr>
			<td>phone</td>
			<td>tel</td>
			<td>254700000000</td>
		</tr>
	</tbody>
</table>
  
### Process Payment
Call the iframe() method where you would like to render the Pesapal iframe
<br>
  `PesaPal::iframe();`

### Process IPN Response
#### Update Database
Create a function to update your database with payment details - this function must return a boolean (true on success, false on failure). The function takes the response data an an argument.
<br>
#### Process IPN
Call the mehod on your callback url, passing the name of the callback function above as an argument
<br>
  `PesaPal::process_ipn( $callback );`
  
## Licencing 
MIT(LICENSE)
