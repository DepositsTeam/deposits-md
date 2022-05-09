
# Deposits One Click Checkout Web SDK Update

##### New Fields
1. `reference` optional but should be unique  each time and minimum length is 15 chars
2. `business_public_key` optional and it should be the business whom this transaction should be credited to and ensure it belongs to a business and correct.
3. `theme_color` optional and it should be the the hex color code of your business. 

Below is what an implementation of the new `DepositsCheckout` would look like:

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
        reference: “your-unique-reference”,
        business_public_key: public-key-of-the-business-to-be credited”,
        theme_color: "your-hex-color-code",
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
