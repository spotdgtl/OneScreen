# Lemon Squeezy Setup

OneScreen now supports direct Lemon Squeezy license activation, validation, and deactivation from the Mac app.

## Dashboard setup

1. Create the OneScreen product in Lemon Squeezy.
2. Enable license keys for the product or variant.
3. Set the activation limit for the number of Macs you want each license to support.
4. Copy the Lemon Squeezy `store_id` and either the `variant_id` or `product_id` for OneScreen.
5. Copy the hosted checkout URL you want the app to open when the user clicks `Buy License`.

Official docs:

- [License keys guide](https://docs.lemonsqueezy.com/guides/tutorials/license-keys)
- [Test mode guide](https://docs.lemonsqueezy.com/help/getting-started/test-mode)

## Xcode build settings

Fill in these target Info.plist build settings for both Debug and Release:

- `LEMON_SQUEEZY_STORE_ID`
- `LEMON_SQUEEZY_VARIANT_ID` or `LEMON_SQUEEZY_PRODUCT_ID`
- `LEMON_SQUEEZY_CHECKOUT_URL`

The app only considers Lemon Squeezy verification enabled when `LEMON_SQUEEZY_STORE_ID` and at least one of `LEMON_SQUEEZY_VARIANT_ID` or `LEMON_SQUEEZY_PRODUCT_ID` are set.

## App behavior

- `Activate License` creates a Lemon Squeezy license instance for the current Mac and stores the returned `instance.id`.
- `Revalidate` validates that saved instance with Lemon Squeezy.
- `Deactivate & Remove` deactivates that saved instance before clearing the local license state.
- If the checkout email is entered, OneScreen verifies it against the purchase email returned by Lemon Squeezy.

## Testing

1. Leave the store in Lemon Squeezy test mode.
2. Use the hosted checkout link to complete a test purchase.
3. Launch OneScreen and paste the test license key from the receipt or `My Orders`.
4. Confirm the app reports `Active`.
5. Click `Deactivate & Remove` once to confirm the activation is released cleanly.
