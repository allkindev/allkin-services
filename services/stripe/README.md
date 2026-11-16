# Stripe

Payments, customers, invoices, subscriptions, refunds, payment links.

## The key

**<https://dashboard.stripe.com/apikeys>**. Prefer a **restricted key** with only the permissions the agent needs, and start with the **test mode** key (`sk_test_…`): nothing real moves with it.

## Good to know

Everything that moves money — refunds, charges, payouts, paying an invoice, subscriptions — asks for your confirmation, as does deleting. Amounts are in the smallest unit (cents).
