# WHMCS
1. EzDeFi Plugin for WHMCS Installation Guide

Please make sure that you have the EzDeFi plugin file for WHMCS. In case you don’t, click on the link below to download the file and install:

[WHMCS Marketplace](https://marketplace.whmcs.com/product/5231)

After you have your installation file, copy the files from the downloaded folder to the root of your WHMCS server.
> **Notice**:
>
> Please make sure you copy the files from the plugin folder into the root folder.

To install EzDeFi plugin, go to **Setup** -> **Payment** -> **Payment Gateway**, and upload the EzDeFi plugin setup file.

Then under **All Payment Gateways** tab, click on **EzDeFi** and your plugin is activated!

![Activate EzDeFi](../../img/whmcs-actv.png "Activate EzDeFi")

After installation completed, click on **Manage Existing Gateways**.

![Manage EzDeFi Gateway](../../img/whmcs-manage.png "Manage EzDeFi Gateway")

2. EzDeFi Configuration Guide

First, you need to register for a merchant account on EzDeFi homepage:

[EzDeFi Merchant Registration](https://merchant.ezdefi.com/register?utm_source=docs)

After registering for an account on EzDeFi Gateway, you can configure EzDeFi Plugin. Please make sure that your account on EzDeFi is ready, then move on to the next steps.

![EzDeFi Gateway Settings](../../img/whmcs-setting.png "EzDeFi Gateway Settings")

I. **Show on Order From**: Turn On/Off EzDeFi Plugin on your store interface. This field allows EzDeFi to be the payment method for your customer.

II. **Display Name**: Change the name of the payment method on your store interface.

III. **Gateway API Url**: Equal to Gateway Endpoint. This field is automatically configured.

IV. **Gateway API Key**: The API Key of the account you registered on EzDeFi homepage. Go to your EzDeFi merchant account and paste it into this field.

V. **Pay with any crypto wallet**: is the payment method for customers who prefer to use their wallets of choice.

For this payment method to function properly, you need to set **Acceptable price variation** and **Decimal** (for each coin/token)

**Acceptable price variation**: Enter the acceptable fluctuation rate to generate the difference in price with the total price of the Order.

> **Notice:**
> 1. If the number of orders at one moment is too large  and the value of each order is similar, the **Acceptable price variation** should be > 1%.
> 2. If your product price is low, the recommended **Acceptable price variation** is between 2 - 5%.

**Decimal**: Set decimal for all the accepted cryptocurrency in your store.

> **Notice:** 
> 
> With coin/token that has big value like BTC, ETH, etc., the decimal should be more or equal to 8.

VI. **Pay with EzDeFi wallet**: is the payment method for customers who prefer to use their wallets of choice.

VII. **Accepted Currency**: Setup the cryptocurrency that are allowed in your store.

Initially, EzDeFi automatically includes NewSD, Bitcoin, and Ethereum. You can add more coin/token by clicking on **Add currency**. Then enter the necessary information into the field.

We have a list of our supported coins/tokens. If we don't have your coin/token in this list, please fill out the form at [Supported Coins/Tokens](https://ezdefi.com/news/supported-coins-tokens/)

![Add currency](../../img/whmcs-add.png "Add currency")

* **Discount**: Enter the discount percentage for each coin/token.
* **Expiration**: Enter the time for checkout before it expires.
* **Wallet address**: Enter the wallet address to receive coin/token payment.
* **Block confirmation**: The number of blocks that you want to record customer’s transaction and confirm the transaction.

> **Notice:** 
> 
> With coin/token that has large value i.e. BTC, ETH, etc., you should enter big enough number, but the downside is that confirming customers’ transactions would take more time.

VIII. **Manage Exception**

Click on **Open Exception table** to open EzDeFi exception management. 

IX. **Save changes**

Finally, don’t forget to save your configs.

3. EzDeFi Payment Guide

Step 1: Select EzDeFi Payment method, click on **Complete Order**

Step 2: The system will display EzDeFi QR Code, it will select the first coin/token by default.

![WHMCS QR Code](../../img/whmcs-qr.png "WHMCS QR Code")

Step 3: Select the preferred payment wallet, if you use wallet other than EzDeFi Wallet, please select **Pay with any crypto currency wallet** and enter the right amount on the QR Code to complete the payment. Otherwise, if you use EzDeFi Wallet, please select **Pay with EzDeFi wallet** to complete the payment.

> **Notice:** 
> 
> We recommend *EzDeFi Wallet* for smoother and easier checkout.

4. Processing Orders Paying after the QR Code Expires (For merchant)

Click on **EzDeFi exception management**

In EzDeFi exception management, **Exception** is the record of the amount corresponding with each order. Customer’s QR code generation and amount is stored in EzDeFi exception table. This will help the merchant to handle order issues and other related problems.

I. Confirm invoice:

![Confirm Invoice](../../img/whmcs-exception1.png "Confirm Invoice")

Select the valid order, then click on **Confirm Paid** button.

II. Change the invoice status from **Paid** to **Not paid**

![Reverse Order](../../img/whmcs-exception2.png "Reverse Order")

Select the order you want to change, click **Reverse** button.

III. Assign amount doesn’t belong to any order

![Assign amount to order](../../img/whmcs-exception3.png "Assign amount to order")

E.g: Your customer uses **Pay with any crypto currency**, but doesn’t enter the exact amount displayed in QR Code. You can go to **EzDeFi exception** to find the amount that customers paid, click on **OrderID** to find the order you want to confirm, then click on **Confirm Paid** to complete the order.

> **Notice:**
>
> **AmountId** is the unique payment amount, generated each time the order is refreshed on the checkout page by changing a very small amount of the total price of the order, to identify the order that has the same **OrderId**. After the plugin received the **AmountId** of the completed order, it'll send back to the merchant the information of that order so the merchant will know which order did the customer pay for.

IV. Choose order to assign

You can assign each amount for any order you want, or you can create a new order and assign the amount for it.
Sequence: Click on **Choose order to assign** -> Select 1 order -> Click on **Assign**.

V. Search

**EzDeFi exception management** supports search based on **Amount**, **OrderID**, **Currency**, **Email**, **Payment method**, **Status**.
