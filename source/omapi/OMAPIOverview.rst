Orders Management API Overview
==============================

The FMSAPIs for Order Management enable a seller to search orders based on dates, state, seller SKU ID, and orderItemId. A seller can also take actions such as “Pack Orders” or “Ready to Dispatch” to ensure order fulfillment and pickup by the logistics partners.

**Format:** JSON

**Protocol:** HTTPS

+---------------------------+------------------------------------+
| API                       | API Description / Use Case         | 
+===========================+====================================+
|POST /orders/search        |Search orders based on dates, state,|
|                           |seller SKU ID, or orderItemId       |                            
+---------------------------+------------------------------------+
|GET /orders/{orderItemId}  |Get order item details based on     |
|                           |orderItemId                         |
+---------------------------+------------------------------------+
|POST /orders/labels        |Mark orders as packed (create       |
|                           |labelRequest)                       |
+---------------------------+------------------------------------+
|GET /orders/labelRequest/  |Check the status of order packing   |
|{labelRequestId}           |(labelRequest)                      | 
+---------------------------+------------------------------------+
|GET /orders/labels?        |Print shipping labels               |
|orderItemId=<id list>      |                                    |
+---------------------------+------------------------------------+
|GET /orders/invoices?      |Print customer invoices             |
|orderItemId=<id list>      |                                    |
+---------------------------+------------------------------------+
|POST /orders/dispatch      |Mark orders “Ready to Dispatch”     |
+---------------------------+------------------------------------+

See the API Reference section for details on each API.