
# Deposits One Click Checkout Tenant Onboarding Guide



The Deposits One-Click Checkout allows allows merchants to quickly enroll, onboard, and checkout customers. We provide powerful Web and Mobile SDK for you.

  

## Setup
You have to first create an account on our console, we advise you do so on our sandbox environment first to enable you understand and play around with the SDK and APIs.

Deposits Console URL in sandbox
```sh
https://sandbox.launch.new/client-admin/login
```
Deposits Console URL in production
```sh
https://launch.new/client-admin/login
```

##### First steps in the console

1. Login/Register on the console, if you do register you would need to verify your account.

2. Click on the Add Client button on the dashboard, fill the form and submit, In Sandbox your tenant will be automatically approved but in production our business and compliance team will review before approving.
3. On the dashboard click on view to open the client page.
4. Navigate to the Keys screen and copy your API to use with our APIs

Deposits API URL in Sandbox
```sh
https://api.deposits.dev/api/v1
```
Deposits API URL in Production
```sh
https://api.ondeposits.com/api/v1
```

With our API you would have access to create users, add ACH and Wire accounts, withdraw funds and more, below is the URL to our Documentation and a static link to our Postman collection, kindly import it to your Postman app or on their website.
  
```sh
https://docs.deposits.dev
```

```
https://www.getpostman.com/collections/e67c7ba863f80797ba4d
```

#### Javascript SDK Resources

![deposits-one-click-checkout-flutter_cover](https://assets.ondeposits.com/img/checkout/sdk-banner-js.png)

To use our Javascript SDK kindly go through this link.
```sh
https://github.com/DepositsTeam/deposits-md/blob/master/deposits_one_click_checkout_web_sdk.md
```

Below are links to our example implementation of the JS SDK on the web. We have a normal setup where we generate a reference and credit the funds to the Master/Tenant wallet, a setup where you can send a unique reference to us and we use that as the reference for the transaction and then a case where you have your own merchants and would want them to receive the funds, your merchants will be created as businesses on our end.
Sandbox
```sh
https://api.deposits.dev/example/checkout
```
```sh
https://api.deposits.dev/example/checkout-reference
```
```sh
https://api.deposits.dev/example/checkout-reference-business
```
Production
```sh
https://api.ondeposits.com/example/checkout
```
```sh
https://api.ondeposits.com/example/checkout-reference
```
```sh
https://api.ondeposits.com/example/checkout-reference-business
```
#### Flutter SDK Resources

![deposits-one-click-checkout-flutter_cover](https://assets.ondeposits.com/img/checkout/sdk-banner.png)

To use our Flutter SDK listed below are some links to places where the code base is hosted.

Github
```sh
https://github.com/DepositsTeam/deposits-oneclick-checkout
```
Pub.dev
```sh
https://pub.dev/packages/deposits_oneclick_checkout
```

## Contributing

Only members of the deposits team can contribute to this. You can create an issue if you find a bug or have any challenge using this Guide.