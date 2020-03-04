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

## Where to find uicheck\_id

Go to the integration page in the UiCheck dashboard \([https://app.uicheck.io/app/integration](https://app.uicheck.io/app/integration)\)

![](../.gitbook/assets/frame_chrome_mac_light-19.png)



## Where to find the stripe\_customer\_id

During development, you can find Stripe customer ID in your Stripe dashboard. However, in production this value should accessible in your database and related to a user. 

### Access stripe\_customer\_id in Stripe dashboard

1. Go to the customers section of the Stripe dashboard \([https://dashboard.stripe.com/customers](https://dashboard.stripe.com/customers)\) 
2. Click on the customer you want to get the stripe\_customer\_id
3. Copy the stripe\_customer\_id \(see screenshot below\)

![](../.gitbook/assets/frame_chrome_mac_light-15.png)

You can then use this value as the stripe\_customer\_id in UiCheck code snippet.

### Accessing the stripe\_customer\_id from your database

Normally you should retrieve the stripe\_customer\_id from your database when rendering the billing page in your subscription software. The simplest way to do that with an SQL database is to add a column name stripe\_customer\_id in your user table and put their the stripe customer id of each of your user.

| email | name | hashed\_password | stripe\_customer\_id |
| :--- | :--- | :--- | :--- |
| user1@email.com | user one | .... .... .... | cus\_GqQ7SyqddqdEU4 |
| user2@email.com | user two | .... .... .... | cus\_jkQ7SyqddqdEU4 |
| ... |  |  |  |

Note that you will need to create a Stripe customer id programmatically for each of you users using the Stripe SDK. We have a tutorial on that here:

{% page-ref page="../closing-the-loop/how-to-create-customers-in-stripe-programmatically.md" %}

## What is the signature

The signature is a cryptographic mechanism that ensure your customers will only be able to see their billing information. It is a protection against forgery. You generate a different signature for every of your customers. The signature is created with the uicheck\_secret. To learn how to generate the signature check the following part of the tutorial:

{% page-ref page="generating-the-signature.md" %}



{% hint style="info" %}
Need more help?[ Chat with us on Facebook!](https://m.me/UiCheck) We will be happy to see how we can help you and improve our doc. If something is not clear we would love to hear about it 😍
{% endhint %}

