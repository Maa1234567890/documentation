===============
Customer credit
===============

Odoo offers a way to provide customers with credit. This feature allows them to purchase items by
incurring a debt toward the company while :ref:`settling this debt later <pos/settle_accounts>`,
either directly through a POS transaction or by settling a generated invoice.

Configuration
=============

To allow customers to pay on credit,

#. :doc:`Create a payment method <../payment_methods>`.
#. Tick the :guilabel:`Identify Customer` checkbox.
#. Leave the :guilabel:`Journal` field empty.

Default credit limit
--------------------

To limit the maximum sales credit,

#. Go to :menuselection:`Accounting --> Configuration --> Settings`.
#. Scroll down to the :guilabel:`Customer Invoices` section.
#. Tick the :guilabel:`Sales Credit Limit` checkbox.
#. Enter the desired maximum amount in the :guilabel:`Default Credit Limit` field.

When the cart value exceeds the defined maximum amount, or the customer has already contracted more
than the maximum amount, a warning appears next to the customer's name. However, this warning does
**not** prevent making the sale.

Usage guidelines
================

To make a sale on credit, add products to the cart, select a customer, and proceed to payment using
the dedicated payment method.

When you make a sale on credit, the following accounting entries are created:

- A debit in Accounts Receivable.
- A credit in the Income account.

When you later settle the accounts (i.e., receive payment from the customer), the following
accounting entries are created:

- A debit in an Outstanding Account.
- A credit in Accounts Receivable.

.. note::
   To ensure proper tracking and management of the customer's outstanding debt, generate an invoice
   for the order or activate the Accounting application.

.. seealso::
   :doc:`../../../finance/accounting/get_started/chart_of_accounts`

Customer statements
-------------------

This amount is considered a debt until the customer pays it off. To know how much a customer owes.
To open the customer statements report,

#. Go to :menuselection:`Point of Sale --> Orders --> Customers`.
#. Select a customer to open the form.
#. Click :guilabel:`Customer Statements` on the top bar. There, you can see a report with all
   invoiced outstanding payments that need to be settled.

.. warning::
   If you did not generate an invoice for the order, the Customer Statements remains empty.

Alternatively, from an open session, click :guilabel:`Customers` to open the list of customers. The
total due amount is displayed right from their name.

.. _pos/settle_accounts:

Settle due accounts
-------------------

Settlement can be made by paying the generated invoice, but also from an open POS session. To do so,

#. Click :guilabel:`Customers`.
#. Click the :icon:`fa-bars` icon (:guilabel:`hamburger menu`) next to the desired customer.
#. Select :guilabel:`Settle due accounts`.
#. Choose the payment method.
#. Click :guilabel:`Validate`.

Then, click :guilabel:`Yes` to confirm the deposit of the payment received from the customer.
