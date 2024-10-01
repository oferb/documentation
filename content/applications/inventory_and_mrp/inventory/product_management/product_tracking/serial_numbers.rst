==============
Serial numbers
==============

*Serial numbers* are one of the two ways to identify and track products in Odoo, along with
:doc:`lots <lots>`. A serial number is a unique identifier assigned to a product to distinguish it
from other products in a series. Serial numbers can consist of several character types: they can
contain numbers, letters, other typographical characters, or any mix of these character types.

The goal of assigning serial numbers allows for the tracking of individual products and their
:doc:`expiration dates <expiration_dates>` and location throughout the supply chain. For instance,
serial numbers can help manufacturers locate products to provide after-sales services or in the
event of a recall.

.. seealso::
   - `Odoo Tutorials: Serial Numbers <https://www.youtube.com/watch?v=ZP-gMz2X5AY>`

.. _inventory/product_management/enable-lots:

Enable lots & serial numbers
============================

To track products using serial numbers, there are two settings that need be enabled.

.. _inventory/product_management/traceability-setting:

Traceability Setting
--------------------

The :guilabel:`Lots & Serial Numbers` traceability feature *must* be enabled first to track
products. To do so, go to :menuselection:`Inventory app --> Configuration --> Settings`, scroll
down to the :guilabel:`Traceability` section, and click the box next to
:guilabel:`Lots & Serial Numbers`. Remember to click the :guilabel:`Save` button to save changes.


.. image:: serial_numbers/enabled-setting.png
   :align: center
   :alt: Enabled Lots & Serial Numbers setting.

.. _inventory/product_management/operation-type-setting:

By Operation Type
-----------------

Next, the ability to create new serial numbers needs to be turned on for specific operation types,
such as receiving or shipping goods. In other words, this setting allows for serial number tracking
on warehouse receipts and delivery orders.

To enable the creation of new serial numbers on an operation, navigate to
:menuselection:`Inventory app --> Configuration --> Operations Types`.

From the :guilabel:`Operations Types` page, select the desired operation type (e.g.
:guilabel:`Receipts`, :guilabel:`Delivery Orders`, or :guilabel:`Manufacturing`), and select the
:guilabel:`Create New` option in the :guilabel:`Lots/Serial Numbers` section of the operation type's
configuration page.

.. image:: serial_numbers/create-new-setting.png
   :align: center
   :alt: Show "Create New" option is selected on the Receipts operation type.

.. _inventory/product_management/detailed-operations:

Configure serial number tracking on individual products
=======================================================

Once the :guilabel:`Lots & Serial Numbers` setting has been activated, individual products can now
be tracked using serial numbers. To track a product, go to :menuselection:`Inventory app -->
Products --> Products`, and select the desired product.

In the :guilabel:`General Information` tab on the product form, make sure the box next to
:guilabel:`Track Inventory` is checked. Then, select :guilabel:`By Unique Serial Number`, and click
:guilabel:`Save` to save the changes. Now, existing or new serial numbers can now be selected and
assigned to newly-received or manufactured batches of this product.

.. image:: serial_numbers/product-tracking.png
   :align: center
   :alt: Enabled serial number tracking on product form.

.. _inventory/product_management/assign-sn:

Assign serial numbers
=====================

In Odoo, serial numbers can be assigned at several times and places:

- When a product is :ref:`already in stock <inventory/product_management/already-in-stock>`
- Via the :ref:`Moves smart button <inventory/product_management/moves-button>` on a
  receipt
- Via the :ref:`Open: Stock move window <inventory/product_management/stock-move>` on a
  receipt
- :doc:`During a manufacturing order
  <../../../manufacturing/basic_setup/configure_manufacturing_product>` for a product tracked by
  lots/serial numbers
- When :doc:`making an inventory adjustment
  <../../warehouses_storage/inventory_management/count_products>`

.. _inventory/product_management/already-in-stock:

Create new serial numbers for products already in stock
-------------------------------------------------------

New serial numbers can be created for products already in stock with no assigned serial number. To
do so, go to :menuselection:`Inventory --> Products --> Lots/Serial Numbers`, and click
:guilabel:`New`. Doing so reveals a blank lot/serial number form. On this form, a new
:guilabel:`Lot/Serial Number` is generated automatically.

.. tip::
   While Odoo automatically generates a new lot/serial number to follow the most recent number, it
   can be edited and changed to any desired number, by clicking the line under the
   :guilabel:`Lot/Serial Number` field, and changing the generated number.

Once the :guilabel:`Lot/Serial Number` is generated, click the blank field next to
:guilabel:`Product` to reveal a drop-down menu. From this menu, select the product to which this new
number will be assigned.

This form also provides the option to adjust the :guilabel:`Quantity`, to assign a unique
:guilabel:`Internal Reference` number (for additional traceability), and to assign this specific
lot/serial number configuration to a specific company in the :guilabel:`Company` field. A detailed
description of this specific lot/serial number can also be added in the
:guilabel:`Description` tab below.

When all desired configurations are complete, click the :guilabel:`Save` button to save all changes.

.. image:: serial_numbers/new-serial-number.png
   :align: center
   :alt: New serial number created for existing product stock.

After a new serial number has been created, assigned to the desired product, and saved, navigate
back to the product form, by going to :menuselection:`Products --> Products`, and selecting the
product that this newly-created serial number was just assigned to.

On that product's detail form, click the :guilabel:`Lot/Serial Numbers` smart button to view the new
serial number.

.. warning::
   If a product doesn't have a serial number assigned to it, a user error pop-up window may appear.
   The error message states that the product(s) in stock have no lot/serial number. However, a
   lot/serial number can be assigned to the product by making an inventory adjustment.

.. _inventory/product_management/incoming-outgoing-products:

Create serial numbers to incoming or outgoing products
------------------------------------------------------

Serial numbers can be assigned to both incoming and outgoing goods. The receipt and delivery order
forms mirror one another; the instructions below can be followed to assign serial numbers in either
form.

- **Incoming goods:** Assign serial numbers directly on the **receipt**. Receipts can be accessed by
  navigating to :menuselection:`Inventory app --> Operations --> Receipts`.
- **Outgoing goods:** Assign serial numbers directly on the **delivery order**. Receipts can be
  accessed by navigating to :menuselection:`Inventory app --> Operations --> Deliveries`.

.. important::
   Before assigning serial numbers on receipts or delivery orders, be sure that the ability to
   :ref:`create new serial numbers by operations type
   <inventory/product_management/operation-type-setting>` is enabled.

Lots/serial number field
~~~~~~~~~~~~~~~~~~~~~~~~

Serial numbers can be entered directly into the Serial Numbers field on a receipt or delivery order.

.. image:: serial_numbers/enter-in-field.png
   :align: center
   :alt: Select value for Serial Number field on receipt.

.. important::
   To make the Serial Numbers field visible on a receipt or delivery order, click the
   :icon:`oi-settings-adjust` :guilabel:`(Adjust Settings)` icon, and ensure the box next to Serial
   Numbers is checked.

   .. figure:: serial_numbers/field-visible.png
      :align: center
      :alt: Allow Serial Numbers field to show on a receipt or delivery order.

.. _inventory/product_management/stock-move:

Stock move pop-up window
~~~~~~~~~~~~~~~~~~~~~~~~

For various methods of assigning serial numbers individually or in bulk, click the
:guilabel:`⦙≣ (bulleted list)` icon in the product line of a receipt.

Add a line
**********

In the :guilabel:`Open: Stock move` pop-up window that appears, serial numbers can be manually input
in the :guilabel:`Lot/Serial Number` column. This method is best reserved for adding only one or a
few serial numbers.

.. image:: serial_numbers/stock-move-add-line.png
   :align: center
   :alt: Add a line on the stock move pop-up.

.. _inventory/product_management/generate-serials:

Generate serials
****************

Assign multiple serial numbers at once by clicking the :guilabel:`Generate Serials/Lots` button in
the :guilabel:`Open: Stock move` pop-up window.

.. image:: serial_numbers/stock-move-generate-serials.png
   :align: center
   :alt: Show generate serials pop-up.

Doing so opens a new popup, :guilabel:`Generate Serial numbers`, which contains a few fields:

- :guilabel:`First SN`: Input the first serial number that should start the sequence.
  From there, Odoo will automatically detect what pattern should be followed to generate more serial
  numbers.
- :guilabel:`Number of SN`: Specify the desired number of serial numbers to generate.

  .. important::
   The number of serials generated will be reflected in the :guilabel:`Quantity` field on a receipt
   or delivery order. Even if the number of serial numbers generated exceeds the :guilabel:`Demand`
   value, Odoo will still allow the quantity (based on the serial numbers) to be delivered or
   received.

   .. image:: serial_numbers/stock-move-generate-quantity-tip.png
      :align: center
      :alt: Show how the quantity of serial numbers alters the delivery order quantity.
- :guilabel:`Keep current lines` checkbox: Check this box to keep existing serial numbers that may
  have been previously added. To replace existing serial numbers in the list, leave the box
  unchecked.

After filling out these fields, click the :guilabel:`Generate` button. The newly generates serials
will now appear in the :guilabel:`Open: Stock move` window. By clicking :guilabel:`Save`, the
:guilabel:`Quantity`and the :guilabel:`Serial Numbers` fields on the delivery order or receipt will
update automatically.

Import serials
**************

Another option for assigning multiple serial numbers at once is to click the
:guilabel:`Import Serials/Lots` button in the :guilabel:`Open: Stock move` pop-up window.

.. important::
   If the import button is not visible, ensure the :guilabel:`Create New` box is checked in the
   :ref:`receipt's configuration page <inventory/product_management/operation-type-setting>`.

Doing so opens the :guilabel:`Import Lots` pop-up window. Enter each serial number on a separate
line in the :guilabel:`Lots/Serial numbers` text field.

.. image:: serial_numbers/stock-move-import-serials.png
   :align: center
   :alt: Show import serials pop-up.

To expedite this process, copy/paste serial numbers from an existing spreadsheet and add them to
the :guilabel:`Lots/Serial numbers` text field.

.. image:: serial_numbers/copy-from-spreadsheet.png
   :align: center
   :alt: Show spreadsheet from which to copy serial numbers.

As when :ref:`generating serials <inventory/product_management/generate-serials>`, check the
:guilabel:`Keep current lines` box to keep existing serial number, or leave it unchecked to
overwrite existing serial numbers.

Finally, click :guilabel:`Generate`.

.. example::
   For a receipt with a :guilabel:`Demand` of `3.00` products, one product has already been assigned
   a serial number in the :guilabel:`Open: Stock move` pop-up window.

   So, in the :guilabel:`Import Lots` pop-up window, two serial numbers, `124` and `125` are
   assigned to the remaining products by entering the following in the :guilabel:`Lots/Serial
   numbers` input field:

   .. code-block::

      124
      125

   The :guilabel:`Keep current lines` option is selected to add these two serial numbers **in
   addition** to the serial number, `123`, that has already been assigned.

   .. image:: serial_numbers/import-serial.png
      :align: center
      :alt: Show example of correctly inputting serial numbers in the text field.

.. _inventory/product_management/moves-button:

Moves smart button
~~~~~~~~~~~~~~~~~~

Accessible from both receipt and delivery order forms, the :guilabel:`Moves` page shows a detailed
view of product movements, including information about serial numbers, exact locations, expiration
dates, etc. This level of detail permits more precise tracking, for example, when handling
perishable or regulated goods.

To access this page, first :ref:`select a warehouse receipt or delivery order
<inventory/product_management/incoming-outgoing-products>`. Click on the
:icon:`oi-view-list` :guilabel:`Moves smart button` at the top of the page.

In the :guilabel:`Lot/Serial Number` column, manually type (or select from the dropdown)
the desired serial numbers for each individual product.

.. image:: serial_numbers/moves-button.png
   :align: center
   :alt: Show the detailed Moves page.

When finished, click the receipt/delivery order's breadcrumb trail, and the assigned serial numbers
will be automatically saved.

Traceability & Reporting
========================

Manufacturers and companies can refer to the :guilabel:`Lots/Serial Numbers dashboard` and
traceability reports to see the entire lifecycle of a product: when and where it originated,
where it was stored, and who it was shipped to.

Lots/Serial Numbers dashboard
-----------------------------

To see the full traceability of a product, or group by serial numbers, go to
:menuselection:`Inventory app --> Products --> Lots/Serial Numbers`. Doing so reveals the
:guilabel:`Lots/Serial Numbers` dashboard.

Reporting
---------

From here, products with serial numbers assigned to them will be listed by default. Click the
:icon:`fa-caret-right` :guilabel:`(expand)` icon to show which serial numbers are assigned to the
chosen product.

To group by serial numbers (or lots), first remove any default filters from the search bar in the
upper-right corner. Then, click :guilabel:`Group By`, and select :guilabel:`Add Custom Group`, which
reveals a mini drop-down menu. From this mini drop-down menu, select :guilabel:`Lot/Serial Number`,
and click :guilabel:`Apply`.

Doing so reveals all existing serial numbers and lots. Each row can be expanded to show all
quantities of product assigned to that serial/lot number. For unique serial numbers that are not
reused, there should be just one product per serial number.

.. image:: serial_numbers/sn-dashboard.png
   :align: center
   :alt: Serial numbers reporting page with drop-down lists.

.. tip::
   For additional information regarding an individual serial number (or lot number), click the line
   item for the serial number to reveal that specific serial number's :guilabel:`Serial Number`
   form. From this form, click the :guilabel:`Location` and :guilabel:`Traceability` smart buttons
   to see all stock on-hand using that serial number, and any operations made using that serial
   number.

.. seealso::
   :doc:`/applications/inventory_and_mrp/inventory/product_management/product_tracking/reassign`

.. tip::
   In addition to using the :guilabel:`Lots/Serial Numbers dashboard`, there are several other
   reporting templates that display serial number. Go to
   :menuselection:`Inventory app --> Reporting`, where the :guilabel:`Locations`report,
   :guilabel:`Moves History`report, and :guilabel:`Moves Analysis`report all include either
   the :guilabel:`Lot/Serial Number` field or the ability to filter by serial number.
