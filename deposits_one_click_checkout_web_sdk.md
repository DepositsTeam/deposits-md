
# Deposits One Click Checkout Web SDK



The Deposits One-Click Checkout SDK allows allows merchants to quickly enroll, onboard, and checkout customers. We provide powerful and customizable UI screens that can be used out-of-the-box to collect payments from your users with or without a deposit account

  

![deposits-one-click-checkout-flutter_cover](https://assets.deposits.com/img/checkout/sdk-banner-js.png)

  

## To Initiate A Checkout
You have to first import out Javascript SDK however we have an example that can guide you on sandbox and production.

#### Example

Example in sandbox
```sh
https://api.deposits.dev/example/checkout
```
Example in production
```sh
https://api.deposits.com/example/checkout
```

#### How to use

SDK Url and JS Import in sandbox
```sh
https://api.deposits.dev/sdk/checkout.js

<script src="https://api.deposits.dev/sdk/checkout.js"></script>
```
SDK Url and JS Import in production
```sh
https://api.deposits.com/sdk/checkout.js

<script src="https://api.deposits.com/sdk/checkout.js"></script>
```

The Second line of code imports our SDK to your web page. With this, you can call the appropriate function to initiate the Deposits checkout flow.
  

Below is what an implementation of the `DepositsCheckout` would look like:

```sh
<!DOCTYPE html>
<html lang=“en”>
<head>
  <title>Checkout Demo</title>
</head>
<body>
  <form id=“form”>
    <label for=“email”>
      Email
    </label>
    <input id=“email” name=“email” type=“email” required placeholder=“Enter your email address” />
    <label for=“amount”>
      Amount
    </label>
    <input id=“amount” name=“amount” type=“number” required placeholder=“Enter a valid amount” />
    <button type=“submit”>
      Initiate Checkout
    </button>
  </form>
  <script src=“https://api.deposits.com/sdk/checkout.js”></script>
  <script>
    document.getElementById(“form”).addEventListener(“submit”, function (e) {
      e.preventDefault();
      const email = document.getElementById(“email”).value;
      const amount = document.getElementById(“amount”).value;
      DepositsCheckout({
        amount,
        api_key: “your-api-key”,
        email,
        callback: (data) => {
          console.log(“callback”, data);
        },
        on_page_closed: () => {
          console.log(“Page got closed”);
        },
        redirect_url: “https://google.com”,
      });
    });
  </script>
</body>
</html>

```

```
document.getElementById("form").addEventListener("submit", function (e) {
        // code
    }
)
```

This is an event listener that lets your webpage know when to call our SDK to initiate the checkout process. This line of code tells the web page to initiate the checkout experience when the user tries to submit the form.

`const email = document.getElementById("email").value;`
`const amount = document.getElementById("amount").value;`

In this line, we get the information entered by the user which are two of the required fields to initiate the one click checkout. By getting the amount and the email address of the customer, we are be able to initiate the one click checkout experience when the user tries to submit the form.



```sh
DepositsCheckout({
    amount,
    api_key: "your-api-key",
    email,
    // primary_background: "red",
    // primary_foreground: "white",
    callback: (data) => {
        console.log("callback", data);
    },
    on_page_closed: () => {
        console.log("Page got closed");
    },
    redirect_url: "https://yourlink.com",
});
```

Calling the `DepositsCheckout` function initiates the checkout process. This function becomes available in your code because of the script we imported initially. This function expects a single argument which is an object that gives the SDK all the information it needs to properly initiate checkout.
  
##### Successful Payment
If the payment is successful, a response similar to this will be gotten:

```
{
	“data”: {
		“amount”: “540”,
		“merchant_name”: “money”,
		“transaction_id”: “DPST_OCC_9ce705decede887e7e2534a07”
	},
	“message”: “Card charged successfully”,
	“status”: “success”
}
```

##### Callbacks & Redirects
After calling `DepositsCheckout` and the payment is completed, what happens next?
There are two options to determine this.

1. Callbacks: With callbacks, you specify the Javascript function for us to call after the payment has been made successfully.

2. Redirects: If you specify a redirect_url like we specified in the example above, your customers will be directed to that URL after successful payment.

###### PS: 
It is important to note that a redirect takes precedence over a callback. What this means is that if a redirect_url is specified, it will be called rather than the callback.

##### Payment Failure
If for some reason a customer’s payment fails, the modal remains open for the customer to try to make the payment again.

We send an email to notify you, if and when this occurs.

##### Cancelled Payments
If the customer closes the payment modal before making payment or clicks "Cancel Payment", we'll cancel the payment session, hide the modal, and you won't be notified. If you do want to be notified, though, you can specify an onclose function. We'll call this function if the payment is cancelled.

  
#### Framework Integrations
The SDK is framework agnostic, it is universal for any Javascript framework. This SDK is written in pure Javascript, it can be used with any Javascript framework, like React, Vue, etc.
  

## Features

**Simplified Security**: We make it simple for you to collect sensitive data such as credit card numbers, ACH details and remain PCI compliant. This means the sensitive data is sent directly to Deposits instead of passing through your server.

  

**Payment methods**: Accepting card and ACH payments helps your business expand its global reach and improve checkout conversion.

  

**Native UI**: We provide native screens and elements to securely collect payment details on Android and iOS.

  

## Contributing

Only members of the deposits team can contribute to this. You can create an issue if you find a bug or have any challenge using this SDK.