---
description: Coming Soon!
---

# Generating the signature





{% tabs %}
{% tab title="Python / Django / Flask" %}
```python
import hmac
import hashlib

stripe_customer_id = "cus_12345678"
uicheck_id="your_uicheck_id"
uicheck_secret="your_uicheck_secret"

signature = hmac.new(
    uicheck_secret.encode("ascii"), # keep this secret safe on your server.
    (uicheck_id + stripe_customer_id).encode("ascii"),
    digestmod=hashlib.sha256,  # hash function
).hexdigest() # pass this result to the frontend.

print(signature) # prints something like 22af9d...c00d8c 
        
```
{% endtab %}

{% tab title="Javascript / Node" %}
```javascript
const crypto = require("crypto");

var stripe_customer_id = "cus_12345678"
var uicheck_id="your_uicheck_id"
var uicheck_secret="your_uicheck_secret"

const signature = crypto.createHmac(
    "sha256",
    uicheck_secret // keep this secret safe on your server.
).update(uicheck_id + stripe_customer_id).digest("hex") // pass the result to the frontend.

console.log(signature) // prints something like 22af9d...c00d8c 
```
{% endtab %}

{% tab title="Ruby / Rails" %}
```ruby
require 'openssl'

stripe_customer_id = "cus_12345678"
uicheck_id="your_uicheck_id"
uicheck_secret="your_uicheck_secret"

signature = OpenSSL::HMAC.hexdigest(
    'sha256', # hash function
    uicheck_secret, # keep this secret safe on your server.
    (uicheck_id + uicheck_secret) # pass this result to the frontend.
) # pass the result to the frontend.

puts(signature) # prints something like 22af9d...c00d8c 
```
{% endtab %}
{% endtabs %}



{% hint style="info" %}
Need more help?[ Chat with us on Facebook!](https://m.me/UiCheck) We will be happy to see how we can help you and improve our doc. If something is not clear we would love to hear about it 😍
{% endhint %}

