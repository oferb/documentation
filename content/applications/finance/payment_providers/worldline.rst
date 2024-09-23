=========
Worldline
=========

`Worldline <https://worldline.com/>`_, is a France-based company and the world's number 4 payments
leader.

.. seealso::
   - :ref:`payment_providers/add_new`
   - `Worldline's documentation <https://worldline.com/en/home/main-navigation/solutions/merchants/online-payment-gateway>`_.

Settings in Worldline
=====================

Create an API user
------------------

Log into your Worldline Merchant Portal and from the menu, go to the :guilabel:`Back Office`. From
there, head to the :guilabel:`Configuration` tab.

You need to create an **API user** to be used in the creation of transactions from Odoo. While you
can use your main account to do so, using an **API user** ensures that if the credentials used in
Odoo are leaked, no access to your Worldline configuration is possible. Additionally, passwords for
**API users** do not need to be updated regularly, unlike normal users.

To create an **API user**, go to :menuselection:`Configuration --> Users` and click on
:guilabel:`New User`. The following fields must be configured:

.. _worldline/worldline:

- :guilabel:`UserID`: you can choose anything you want.
- :guilabel:`User's Name, E-mail and Timezone`: you can enter the information you want.
- :guilabel:`Profile`: should be set to :guilabel:`Admin`.
- :guilabel:`Special user for API`: should be checked.

.. tip::
   If you already have an user set up, make sure it is activated without any error.

Set up Worldline for Odoo
-------------------------

Worldline must now be configured to accept payments from Odoo.

From your merchant portal, head to :menuselection:`Developer --> Payment API`, click on
:guilabel:`Add API key`

Write down your :guilabel:`API key ID` and the associated :guilabel:`Secret API key`, you'll need
these to set up your provider.

When done, head to :menuselection:`Developer --> Webhooks` and :guilabel:`generate webhooks keys`.

Write down your :guilabel:`Webhook key` and the associated :guilabel:`Webhook secret`, you'll need
these to set up your provider.

On the same page, you can now :guilabel:`Add webhook endpoint`.

There, you can enter the **URL**, it should contain the same following URL, with `<example>`
replaced by your database: `https://<example>/payment/worldline/webhook`.


Settings in Odoo
================

To set up Worldline in Odoo, head to :menuselection:`Accounting --> Configuration --> Payment
Providers` and open the Worldline provider. In the :guilabel:`Credentials` tab, enter the **PSPID**
of your Worldline account, and fill out the other fields as configured in your :ref:`Worldline
portal <worldline/worldline>`.
