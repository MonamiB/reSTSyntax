1) POST /orders/search
======================
**Description** - Search order items using specific filters.

You can get order items and their details based on the order date, dispatch date, order states, and seller SKU ID. The first call to the POST API below returns the default, finite number of results based on the “pageSize” value. Calling the URL returned in the “nextPageURL” field of the response can get the subsequent pages for order item results. The response of the search API contains the items and sub-items that comprise of one shipment, packed together, and only one label is generated for that group.

**Request Parameters**

**Headers:** `Content-type:application/json`

**Request Structure:**::

    {
    "filter": {
    “orderDate” { 
    “fromDate” : date string (in ISO format) from which orders need to be searched,
    “toDate” : date string (in ISO format) upto which orders need to be searched
    }
    “dispatchByDate” { 
    “fromDate” : date string (in ISO format) from which orders need to be searched,
    “toDate” : date string (in ISO format) upto which orders need to be searched
    }
    "states": List<String> of states in which orders need to be searched. See validations.
    “sku”:List<String> of skus for which orders need to be searched
    },
    "filter" : {
    “modifiedDate” {
    “fromDate” : date string (in ISO format) from which orders need to be searched,
    “toDate” : date string (in ISO format) upto which orders need       to be searched
    }
    }
    "pagination": {
    "pageSize": 20 // Number of search results in the response.
    Default = 20
    },
    "sort": {
    "field": can be one of the the 2 fields orderDate or
    dispatchByDate
    "order": "desc" or “asc”
    }
    }    

**Request Body Parameters**

==============  ==================  =============
Parameter Name  Mandatory/Optional  Default Value
==============  ==================  =============
False           False               False
True            False               False
False           True                False
True            True                True
==============  ==================  =============


+----------------+--------------------+---------------------+
|                |                    |                     |                            
+================+====================+=====================+
|                |                    |                     |                            
+----------------+--------------------+---------------------+
|                |                    |                     |                            
+----------------+--------------------+---------------------+
|                |                    |                     |                            
+----------------+--------------------+---------------------+
|                |                    |                     |                                                        
+----------------+--------------------+---------------------+
|                |                    |                     |                            
+----------------+--------------------+---------------------+
|                |                    |                     |                            
+----------------+--------------------+---------------------+


*\* If toDate is specified, the default fromDate is calculated as 14 days prior to the toDate.*

`OrderDate: fromDate`
Optional
Start of time
`OrderDate: toDate`
Optional
Current date
`DispatchByDate: fromDate`
Optional
Start of time
`DispatchByDate: toDate`
Optional
Current date
`States`
Optional
All states
`sku`
Optional
All SKU
`pageSize`
Optional 
20
`Sort field`
Optional
dispatchByDate
`Sort order`
Optional
asc
`modifiedDate: fromDate`
Optional
Start of time*
`modifiedDate: toDate`
Optional
Current date

Response
Response Code
Description
200
Successful call
400
Bad request or validation failures


**Response Structure:**
~~~
    for success cases: http code 200
    {
    "hasMore": true,
              "orders": [
            {
            “orderItemId” : order item id
            …...other order item attributes….
            “subItems” : [{
                ….subItem attributes….
                       }]
            }
                    ]
    "url": Relative URL for current page search results,
      "nextPageUrl": Relative URL for next page search results. Not present
      for last page.
     "previousPageUrl": Relative URL for previous page search results. Not
      present for first page
}
for failure cases: http code 4XX, 5XX.
{
 "errorCode": "INVALID_DATE_FORMAT"
   "errorMessage": "Date format is invalid."            
}
~~~

Validations:
~~~
           pageSize: value between 1 and 20 inclusive
           states: Possible values are 
                      APPROVED, ON_HOLD, PACKED, READY_TO_DISPATCH, CANCELLED
           filter: all filters are optional.
           sort field: can be one of orderDate or dispatchByDate
~~~

***Notes:***

1. *Dates are in ISO format.
2. *Provides only those orders, which are to be fulfilled by sellers. Flipkart Advantage (FA) orders are not shown.*
3. *Provides the default sort order that is, sort by dispatchByDate asc (to be marked RTD).*


**Possible Response Error Codes**

| Error Codes                    | Reason for Error | 
|---------------------------|------------------------------------|
|`INVALID_REQUEST_PAGE_SIZE`|Validation failure of the requested page size value.|
|`INVALID_REQUEST_STATE`|Validation failure of the selected state.|
|`INVALID_REQUEST_JSON`|JSON parsing failure of the request.|
|`INVALID_DATE_FORMAT`|Parsing failure of the from or to dates.|  


**Example:**::

    Request: /orders/search
       {
    "filter": {
             "orderDate": {
                       "fromDate": "2014-07-23T00:00:00Z",
                 "toDate": "2014-07-23T10:00:00Z"
              },
              "dispatchByDate": {
                 "fromDate": "2014-07-25T00:00:00Z",
                 "toDate": "2014-07-25T10:00:00Z"
                 },
              "states": [
                        "APPROVED"
              ],
              "sku": [
                        "1",
                        "2"
              ],
              "pagination": {
                        "pageSize": 20
              }
    },
    "sort": {
              "field": "dispatchByDate",
              "order": "asc"
    }
      }
    Response:
       {
           "hasMore": true,
           "orders": [
               {
                   "orderItemId": 1179576,
                   "state": "APPROVED",
                   "orderDate": "2014-07-18T10:00:00Z",
                   "dispatchByDate": "2014-07-20T10:00:00Z",
                   "sla": 1,
                   "quantity": 1,
                   "title": "Samsung Galaxy S3 Pebble Blue",
                   "listingId": "LSTMOBDACGHGSMVG9VSIQLWV5",
                   "fsn": "MOBDACGHGSMVG9VS",
                   "sku": "1",
       "price": 100,
    "shippingFee": 50,
    "octroi": 0,
    "emi": 0,
                   "stateDocuments": ["eSugam"],
                   "subItems": [
                       {
                           "orderItemId": 1173467,
                           "state": "APPROVED",
                           "quantity": 1,
                           "title": "Skullcandy 2XL Headphone Black Shakedown X5SHFZ-820",
                           "listingId": "LSTACCDB56E2HUNGVNMPLEDW2"
                           "fsn": "ACCDB56E2HUNGVNM",
                           "sku": "Seller SKU Id",
            "price": 100,
                  "shippingFee": 50,
                  "octroi": 0,
                 "emi": 0,
          "orderDate": "2014-07-18T10:00:00Z",
                        "dispatchByDate": "2014-07-20T10:00:00Z",
                        "sla": 1
                       }
                   ]
               }
           ],
           "url": "/orders/search/ic3RhcnRpbmdQY0=/ewogICCn0=",
           "nextPageUrl": "/orders/search/ewogICJzb3JCB9Cn0=/ewogn0="
           "previousPageUrl": "/orders/search/ewossICJzb3JCB9Cn0=/ewogn0="
       }

