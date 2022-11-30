# Welcome to deposits!
This doc helps you to get started with deposits. It contains the various pointers you need to make use of our services. 
If you have any questions, please reach out on the slack channel for support.

# Setting Up
To get started, you have to create an account on our console. It’s recommended that you create an account on the sandbox environment first before you do so in production. This would help you understand how to go about working with the SDK and APIs in production.

## Environments
You can access our APIs from the base URLs depending on the stage of development you're in, for easy development and testing.

| Environment | Console URL | Base URLs |
| --- | --- | --- |
| Sandbox | https://console.deposits.dev/client-admin/login | https://api.deposits.dev/api/v2/ |
| Production | https://console.ondeposits.com/client-admin/login | https://api.ondeposits.com/api/v2/ |

## Creating a Client
To setup your account,
1. Register on the console using the specified URL above.
2. After successful registration, verify your account.
3. Create a client on the dashboard by clicking the “Add Client” button. Fill out the form and submit it for approval. Client approvals are handled automatically in the sandbox environment. In production, however, our business and compliance teams will review before approving.
4. On the dashboard, click “view” to open the client page.
5. To retrieve your API keys, navigate to the “Keys” page. These keys would grant you access to our APIs.

# Endpoints
The following are endpoints that you might require for the success of operating virtual accounts. 

## Users
When dealing with individual entities, you can do things like create a user (entity), retrieve their profile, and so on. To learn more, find documentation [here](https://docs.deposits.dev/api/entity/individual).

## Withdrawals
Using our API, you can perform various withdrawal transactions such as withdrawing to a saved account, or getting the withdrawal transactions of a user. To learn more about our payout endpoints, settlement types, and cut-off times, see our [documentation](https://docs.deposits.dev/api/pay-outs).   

## Card Issuing
To issue cards and perform other card operations, you can find the documentation [here](https://github.com/DepositsTeam/deposits-md/blob/master/card_issuing.md). 

# References
- [Deposits Staging Console](https://console.deposits.dev)
- [Deposits Production Console](https://launch.new)
- [Deposits API Architecture and Resource Structure](https://docs.deposits.dev/#api-architecture-and-resource-structure)
- [Deposits API Reference](https://docs.deposits.dev)
