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
  
### Process Payment
<br>
  `PesaPal::iframe();`

### Process IPN Response
#### Process IPN
Create a function to update your database with payment details - this function must return a boolean (true on success, false on failure). The name of this callback function is passed as an argument to the `process_ipn();` method.
<br>
  `PesaPal::process_ipn( $callback );`
  
## Licencing 
MIT(LICENSE)
