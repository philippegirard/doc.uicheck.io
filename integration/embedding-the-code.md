# Embedding the code 🏓

It is very easy to integrate UiCheck to your website. Just copy paste the following code and replace the following values : 

* **uicheck\_id** : your UiCheck id 
* **stripe\_customer\_id**: the stripe customer ID you want UiCheck to display
* **signature**: a signature showing that it is really you making the request to UiCheck servers.

```markup
<div id="uicheck-embed"></div>
<script>
    window.uicheckSettings = {
        uicheckId: 'uicheck_id',
        customerId: 'stripe_customer_id',
        signature: 'signature',
    }
</script>
<script src="https://cdn.uicheck.io/uicheck.js" async></script>
```

{% hint style="info" %}
Need more help?[ Chat with us on Facebook!](https://m.me/UiCheck) We will be happy to see how we can help you and improve our doc. If something is not clear we would love to hear about it 😍
{% endhint %}

