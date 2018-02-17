# PaySrc CLI Client


![Screenshot](https://github.com/payrsrc/cli-client/raw/master/screenshot.png)

This is a basic CLI client for [PaySrc](https://paysrc.com/), a BCH payment platform.  
Tested with PaySrc API v1 on PHP 7.0.

The idea behind this client is a quick, dependency-less (except PHP) terminal client.  
Feel free to take a look at the code and adapt it to your needs.

Visit [PaySrc.com](https://paysrc.com/) for more information.

## Installation & Usage

Just clone this git, go into the directory and run paysrc.  
Only depends on PHP 7.0+.

```bash
git clone https://github.com/choval/paysrc-cli-client.git --depth=1
cd paysrc-cli-client
php paysrc
php paysrc --query 10022
```

Check the same payment at:
[https://paysrc.com/p/10022](https://paysrc.com/p/10022)



```
Usage
php paysrc.php --address="1MH5fNnWJ4YduxW61rHqpuekoMwCmgWp2M" --amount=0.001
php paysrc.php --query <PAYMENT_ID>

Returns
Payment Request

ID:      <PAYMENT_ID>
Amount:  BCH <AMOUNT>
Address: <ADDRESS>
Created: <CREATED>
Expires: <EXPIRATION>
Status:  <PAYMENT_STATUS>
Link:    https://paysrc.com/p/<PAYMENT_ID>
----

Parameters:

  --address <address>
            A cashaddr or legacy address where the final funds will be sent.
            This address is hidden to the payer, you can use the same address multiple times.
            Legacy addresses will be converted to cashaddr format.
            !REQUIRED

  --amount <amount>
            The amount of BCH to request.
            !REQUIRED

  --from <from>
            Name and email of who is requesting the payment (beneficiary).
            Examples: --from "Name <user@domain>"
                      --from "Name"
                      --from "<user@domain>"

  --to <to>
            Name and email of the customer or person to whom the payment is being sent (payer).
            To send a notification to the payer's email, the beneficiary's email must be provided too.
            Examples: --from "Name <user@domain>"
                      --from "Name"
                      --from "<user@domain>"

  --message <message>
            An optional message/text string.
            Warning: This message is public and not logged on the blockchain.

  --confirmations <confirmations>
            A number of confirmations required for the payer's confirmation.
            If not set, the minimum number of confirmations possible is used.

  --expires <expires>
            An optional UTC date-time expiration for the payment request.
            Examples: --expires "2018-12-31 12:34:56"
                      --expires "+3 months"
                      --expires "1546225200"

  --query <payment_id>
            Returns the Payment

Settings

  --json    Outputs the result in JSON format and exits.
  --testnet Runs on testnet. Make sure your address is testnet address.
  --nowait  Print and exit, do not wait for payment completion.
  --noqr    Do not print the QR code.
  --legacy  Displays legacy addresses.
```

## TODO

- Notification & Redirect URIs.
- A proper library class.

## License

This bundle is under the MIT license. For the full copyright and license information please view the LICENSE file that was distributed with this source code.
