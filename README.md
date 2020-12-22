# **MIGAPRINTV2 - API Documentation**
### *Connecting outer world with worlds most reliable order monitoring system.*

---

[![Migaprintv2 Logo](https://github.com/migastone/migaprint-api/blob/master/docs_images/logo.png)](https://migastone.kartra.com/checkout/78c34c2b72c90b466b5d8d1cd24e5b1d)

---

**Authentication**

---

  How to verify if the credential you got are valid and working. You can call the `root` or `index` method to check. However if you are sure then you can skip this `optional` step.

  * **URL**

  	/migaprintv2/api OR
 
  	/migaprintv2/api/index

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 

	{
		"error": null,
		"data": {
			"api_id": "3",
			"app_id": "4",
			"value_id": "315",
			"api_token": "9aefe2-41299b-03f28f-e998cd-676496",
			"api_slug": "foodprintv2-official",
			"api_status": "1",
			"api_last_accessed_at": "2020-08-10 12:40:42",
			"created_at": "2020-08-10 12:40:42",
			"id": "3"
		}
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**

	`{ "error": "Invalid Access.", "data": null }` OR
	
	`{ "error": "Invalid Parameter(s) Found.", "data": null }` OR

	`{ "error": "No Api Slug Key Posted.", "data": null }` OR

	`{ "error": "No Api Slug Posted.", "data": null }` OR

	`{ "error": "Invalid Api Slug.", "data": null }` OR

	`{ "error": "No Token Key Posted.", "data": null }` OR

	`{ "error": "No Token Posted.", "data": null }` OR

	`{ "error": "Invalid Token.", "data": null }` OR

	`{ "error": "App Api Status is Disabled.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**Heartbeat**

---
  
  This method will be use to check if API is currently live and working as expected. For example not down for maintenance.

  * **URL**

  	/migaprintv2/api/heartbeat

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 

	{
		"error": null,
		"data": {
			"status": "Migaprintv2 API Running.",
			"version": "1.0.0",
			"slug": "foodprintv2-official",
			"title": "Migaprintv2 Official API Services"
		}
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**

	`{ "error": "Invalid Access.", "data": null }` OR
	
	`{ "error": "Invalid Parameter(s) Found.", "data": null }` OR

	`{ "error": "No Api Slug Key Posted.", "data": null }` OR

	`{ "error": "No Api Slug Posted.", "data": null }` OR

	`{ "error": "Invalid Api Slug.", "data": null }` OR

	`{ "error": "No Token Key Posted.", "data": null }` OR

	`{ "error": "No Token Posted.", "data": null }` OR

	`{ "error": "Invalid Token.", "data": null }` OR

	`{ "error": "App Api Status is Disabled.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/heartbeat",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**All Printers or Filtered**

---
  
  This method will load all the printers created in the system. One can also filtered them by using `search_field_title` parameter where you can specify the name of the printer field like `search_field_title = store_id` and with the combination of the `search_field_value` parameter where you can specify the value of the searched `search_field_title`. For example if you want to search a printer by store id than you can specify it like  `search_field_title = store_id` and `search_field_value = 3`. This means now you will get the printer with `store_id` is `3`.

  * **URL**

  	/migaprintv2/api/stores

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

	**Optional:**

	`search_field_title = [string]`

	`search_field_value = [mixed]`

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	//Without Filter
	{
		"error": null,
		"data": [
			{
				"printer_id": "5",
				"app_id": "4",
				"value_id": "315",
				"store_id": "3",
				"printer_title": "Printer Pro 02",
				"printer_type": "2",
				"printer_restaurant_id": "18459076",
				"printer_password": "953874",
				"printer_ping_counter": "0",
				"created_at": "2020-07-09 09:35:02",
				"updated_at": "2020-07-09 09:35:02",
				"id": "5"
			},
			{
				"printer_id": "7",
				"app_id": "4",
				"value_id": "315",
				"store_id": "2",
				"printer_title": "Printer Pro 01",
				"printer_type": "3",
				"printer_restaurant_id": "12589053",
				"printer_password": "179334",
				"printer_ping_counter": "2",
				"created_at": "2020-07-30 10:49:20",
				"updated_at": "2020-08-12 11:01:16",
				"id": "7"
			}
		]
	}

```

```javascript 
	
	//With Filter
	{
		"error": null,
		"data": [
			{
				"printer_id": "5",
				"app_id": "4",
				"value_id": "315",
				"store_id": "3",
				"printer_title": "Printer Pro 02",
				"printer_type": "2",
				"printer_restaurant_id": "18459076",
				"printer_password": "953874",
				"printer_ping_counter": "0",
				"created_at": "2020-07-09 09:35:02",
				"updated_at": "2020-07-09 09:35:02",
				"id": "5"
			}
		]
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**

	`{ "error": "Invalid column name or value.", "data": null }` OR
	
	`{ "error": "No printer found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/printers",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
				'search_field_title' => 'store_id' ,  //optional
				'search_field_value' => '3' , //optional
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**All Stores**

---
  
  This method will load all the stores created in the system.

  * **URL**

  	/migaprintv2/api/stores

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": [
			{
				"store_id": "2",
				"name": "Pro Store 01"
			},
			{
				"store_id": "3",
				"name": "Pro Store 02"
			},
			{
				"store_id": "6",
				"name": "Table Ordering"
			}
		]
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No store found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/stores",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**All Stores with Printers Assigned or Filtered**

---
  
  This method will load all the stores with printers assigned to them. One can also filtered them by using `search_field_title` parameter where you can specify the name of the store or printer field like `search_field_title = store_id` and with the combination of the `search_field_value` parameter where you can specify the value of the searched `search_field_title`. For example if you want to search a store & printer by store id than you can specify it like  `search_field_title = store_id` and `search_field_value = 3`. This means now you will get the store & printer with `store_id` is `3`.

  * **URL**

  	/migaprintv2/api/storeprinters

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

	**Optional:**

	`search_field_title = [string]`

	`search_field_value = [mixed]`

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	//Without Filter
	{
		"error": null,
		"data": [
			{
				"printer_id": "5",
				"printer_title": "Printer Pro 02",
				"printer_type": "2",
				"printer_restaurant_id": "18459076",
				"printer_password": "953874",
				"store_id": "3",
				"name": "Pro Store 02"
			},
			{
				"printer_id": "7",
				"printer_title": "Printer Pro 01",
				"printer_type": "3",
				"printer_restaurant_id": "12589053",
				"printer_password": "179334",
				"store_id": "2",
				"name": "Pro Store 01"
			}
		]
	}

```

```javascript 
	
	//With Filter
	{
		"error": null,
		"data": [
			{
				"printer_id": "5",
				"printer_title": "Printer Pro 02",
				"printer_type": "2",
				"printer_restaurant_id": "18459076",
				"printer_password": "953874",
				"store_id": "3",
				"name": "Pro Store 02"
			}
		]
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**

	`{ "error": "Invalid column name or value.", "data": null }` OR
	
	`{ "error": "No store printer found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/storeprinters",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
				'search_field_title' => 'store_id' ,  //optional
				'search_field_value' => '3' , //optional
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**All Orders**

---
  
  This method will load all the orders in descending order by date. It will be a multidimensional array of JSON with list of products dispatched to each order as well. One can also filtered them by using `search_field_title` parameter where you can specify the name of the order field like `search_field_title = store_id` and with the combination of the `search_field_value` parameter where you can specify the value of the searched `search_field_title`. For example if you want to search an order by store id than you can specify it like  `search_field_title = store_id` and `search_field_value = 3`. This means now you will get the orders with `store_id` is `3`.

  * **URL**

  	/migaprintv2/api/orders

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

	**Optional:**

	`search_field_title = [string]`

	`search_field_value = [mixed]`

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	//without filter
	{
		"error": null,
		"data": [
			{
				"order_id": "38",
				"app_id": "4",
				"value_id": "315",
				"store_id": "2",
				"customer_id": "1",
				"custom_order_id": "9",
				"sib_order_id": "21",
				"order_number": "O0000005",
				"order_payment_method": "Cash",
				"order_delivery_method": "Delivery",
				"order_customer_firstname": "David",
				"order_customer_lastname": "John",
				"order_customer_email": "abc@gmail.com",
				"order_customer_street": "Street 01",
				"order_customer_postcode": "12344",
				"order_customer_city": "New York",
				"order_customer_phone": "+323222578",
				"order_deliverytime": "2020-08-06 12:21:00",
				"order_delivery_note": "",
				"order_total": "6.1200",
				"order_paid_amount": "0.0000",
				"order_transaction_id": null,
				"order_note": null,
				"order_fetched_count": "6",
				"order_processing_email_count": "0",
				"order_date": "2020-08-03 09:22:18",
				"order_fetch_time": "2020-08-12 11:01:18",
				"order_response_time": "2020-08-12 11:01:48",
				"order_status": "1",
				"order_module": "2",
				"order_type": "printer",
				"order_receipt_code": "IzEyNTg5MDUzKioyXzkqQ0xJRU5UXHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cckltcmFuIFJhc2hpZFxyUGFrIFRvL3duLFdhemlyYWJhZFxyQ0FQIDEyMzQ0XHIrMzkzMzQ2ODI0NTc4XHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cck9SREVSIG4gMl85XHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1ccjE7UGl6emEgMDE7VVNENi4wMDtGb3JtYXQ6IExvdmVseTs7O09wdGlvbjo7OzsxO09wdGlvbiAwMTtVU0QxLjAyO0Nob2ljZTogQ2hvaWNlIDAxLCBDaG9pY2UgMDI7OztcclByb2R1Y3RzOiAxLCBPcHRpb25zOiAxOzs7Kio7OzstLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cclRPVEFMIFVTRDYuMTJcci0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLVxyREVMSVZFUlkgRGVsaXZlcnlcclBBWU1FTlQgQ2FzaFxyREFURSAwMy8wOC8yMDIwIDA5OjIyOjE4XHJDT01NRU5UUyBQcmVmZXJyZWQgRGVsaXZlcnkgVGltZTowNi8wOC8yMDIwIDEyOjIxXHJcclxyXHJccjs7OzsqIw==",
				"order_code_range": null,
				"order_commerce": "Commerce Pro",
				"submitted_number": null,
				"delivery_method_id": "3",
				"updated_from": "",
				"updated_by": "4",
				"created_at": "2020-08-03 09:23:49",
				"updated_at": "2020-08-12 11:01:48",
				"id": "38",
				"products": [
					{
						"product_id": "112",
						"app_id": "4",
						"value_id": "315",
						"store_id": "2",
						"customer_id": "1",
						"custom_order_id": "9",
						"sib_order_id": "21",
						"order_id": "38",
						"product_name": "Pizza 01",
						"product_quantity": "1.00",
						"product_total": "6.0000",
						"product_choices": "a:1:{i:2;a:1:{s:16:\"selected_options\";a:2:{i:0;s:1:\"3\";i:1;s:1:\"4\";}}}",
						"product_options": "a:1:{i:0;a:6:{s:9:\"option_id\";s:1:\"1\";s:4:\"name\";s:9:\"Option 01\";s:10:\"base_price\";d:1.02;s:5:\"price\";d:1;s:14:\"price_incl_tax\";d:1.02;s:3:\"qty\";i:1;}}",
						"product_format": "a:3:{s:2:\"id\";s:1:\"1\";s:5:\"title\";s:6:\"Lovely\";s:5:\"price\";s:4:\"5.00\";}",
						"product_status": "1",
						"created_at": "2020-08-03 09:23:50",
						"updated_at": "2020-08-12 11:01:48",
						"id": "112"
					}
				]
			},
			{
				"order_id": "37",
				"app_id": "4",
				"value_id": "315",
				"store_id": "2",
				"customer_id": "1",
				"custom_order_id": "8",
				"sib_order_id": "20",
				"order_number": "O0000004",
				"order_payment_method": "Cash",
				"order_delivery_method": "In store",
				"order_customer_firstname": "Johny",
				"order_customer_lastname": "Liver",
				"order_customer_email": "xyz@gmail.com",
				"order_customer_street": "Street 098",
				"order_customer_postcode": "12344",
				"order_customer_city": "Orange",
				"order_customer_phone": "+123446824578",
				"order_deliverytime": "",
				"order_delivery_note": "",
				"order_total": "11.2200",
				"order_paid_amount": "0.0000",
				"order_transaction_id": null,
				"order_note": null,
				"order_fetched_count": "0",
				"order_processing_email_count": "0",
				"order_date": "2020-08-03 08:54:22",
				"order_fetch_time": "0000-00-00 00:00:00",
				"order_response_time": "0000-00-00 00:00:00",
				"order_status": "1",
				"order_module": "2",
				"order_type": "printer",
				"order_receipt_code": null,
				"order_code_range": null,
				"order_commerce": "Commerce Pro",
				"submitted_number": null,
				"delivery_method_id": "1",
				"updated_from": "owner",
				"updated_by": "4",
				"created_at": "2020-08-03 08:59:24",
				"updated_at": "2020-08-05 10:42:32",
				"id": "37",
				"products": [
					{
						"product_id": "111",
						"app_id": "4",
						"value_id": "315",
						"store_id": "2",
						"customer_id": "1",
						"custom_order_id": "8",
						"sib_order_id": "20",
						"order_id": "37",
						"product_name": "Pizza 01",
						"product_quantity": "1.00",
						"product_total": "11.0000",
						"product_choices": "a:1:{i:2;a:1:{s:16:\"selected_options\";a:3:{i:0;s:1:\"3\";i:1;s:1:\"4\";i:2;s:1:\"5\";}}}",
						"product_options": "a:1:{i:0;a:6:{s:9:\"option_id\";s:1:\"2\";s:4:\"name\";s:9:\"Option 02\";s:10:\"base_price\";d:2.04;s:5:\"price\";d:2;s:14:\"price_incl_tax\";d:2.04;s:3:\"qty\";i:1;}}",
						"product_format": "a:3:{s:2:\"id\";s:1:\"2\";s:5:\"title\";s:5:\"Yummy\";s:5:\"price\";s:4:\"9.00\";}",
						"product_status": "1",
						"created_at": "2020-08-03 08:59:25",
						"updated_at": "2020-08-05 10:42:32",
						"id": "111"
					}
				]
			},
		 ]
	}

```

```javascript 
	
	//with filter
	{
		"error": null,
		"data": [
			{
				"order_id": "38",
				"app_id": "4",
				"value_id": "315",
				"store_id": "2",
				"customer_id": "1",
				"custom_order_id": "9",
				"sib_order_id": "21",
				"order_number": "O0000005",
				"order_payment_method": "Cash",
				"order_delivery_method": "Delivery",
				"order_customer_firstname": "David",
				"order_customer_lastname": "John",
				"order_customer_email": "abc@gmail.com",
				"order_customer_street": "Street 01",
				"order_customer_postcode": "12344",
				"order_customer_city": "New York",
				"order_customer_phone": "+323222578",
				"order_deliverytime": "2020-08-06 12:21:00",
				"order_delivery_note": "",
				"order_total": "6.1200",
				"order_paid_amount": "0.0000",
				"order_transaction_id": null,
				"order_note": null,
				"order_fetched_count": "6",
				"order_processing_email_count": "0",
				"order_date": "2020-08-03 09:22:18",
				"order_fetch_time": "2020-08-12 11:01:18",
				"order_response_time": "2020-08-12 11:01:48",
				"order_status": "1",
				"order_module": "2",
				"order_type": "printer",
				"order_receipt_code": "IzEyNTg5MDUzKioyXzkqQ0xJRU5UXHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cckltcmFuIFJhc2hpZFxyUGFrIFRvL3duLFdhemlyYWJhZFxyQ0FQIDEyMzQ0XHIrMzkzMzQ2ODI0NTc4XHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cck9SREVSIG4gMl85XHItLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1ccjE7UGl6emEgMDE7VVNENi4wMDtGb3JtYXQ6IExvdmVseTs7O09wdGlvbjo7OzsxO09wdGlvbiAwMTtVU0QxLjAyO0Nob2ljZTogQ2hvaWNlIDAxLCBDaG9pY2UgMDI7OztcclByb2R1Y3RzOiAxLCBPcHRpb25zOiAxOzs7Kio7OzstLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS1cclRPVEFMIFVTRDYuMTJcci0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLVxyREVMSVZFUlkgRGVsaXZlcnlcclBBWU1FTlQgQ2FzaFxyREFURSAwMy8wOC8yMDIwIDA5OjIyOjE4XHJDT01NRU5UUyBQcmVmZXJyZWQgRGVsaXZlcnkgVGltZTowNi8wOC8yMDIwIDEyOjIxXHJcclxyXHJccjs7OzsqIw==",
				"order_code_range": null,
				"order_commerce": "Commerce Pro",
				"submitted_number": null,
				"delivery_method_id": "3",
				"updated_from": "",
				"updated_by": "4",
				"created_at": "2020-08-03 09:23:49",
				"updated_at": "2020-08-12 11:01:48",
				"id": "38",
				"products": [
					{
						"product_id": "112",
						"app_id": "4",
						"value_id": "315",
						"store_id": "2",
						"customer_id": "1",
						"custom_order_id": "9",
						"sib_order_id": "21",
						"order_id": "38",
						"product_name": "Pizza 01",
						"product_quantity": "1.00",
						"product_total": "6.0000",
						"product_choices": "a:1:{i:2;a:1:{s:16:\"selected_options\";a:2:{i:0;s:1:\"3\";i:1;s:1:\"4\";}}}",
						"product_options": "a:1:{i:0;a:6:{s:9:\"option_id\";s:1:\"1\";s:4:\"name\";s:9:\"Option 01\";s:10:\"base_price\";d:1.02;s:5:\"price\";d:1;s:14:\"price_incl_tax\";d:1.02;s:3:\"qty\";i:1;}}",
						"product_format": "a:3:{s:2:\"id\";s:1:\"1\";s:5:\"title\";s:6:\"Lovely\";s:5:\"price\";s:4:\"5.00\";}",
						"product_status": "1",
						"created_at": "2020-08-03 09:23:50",
						"updated_at": "2020-08-12 11:01:48",
						"id": "112"
					}
				]
			},
		]
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**

	`{ "error": "Invalid column name or value.", "data": null }` OR
	
	`{ "error": "No order found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/orders",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
				'search_field_title' => 'store_id' ,  //optional
				'search_field_value' => '3' , //optional
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**Settings**

---
  
  This method will load all the settings created in the system.

  * **URL**

  	/migaprintv2/api/settings

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": {
			"config_id": "1",
			"app_id": "4",
			"value_id": "315",
			"config_order_start_date": "2020-02-01",
			"config_shop_status": "2",
			"config_receipt_delivery": "1",
			"config_processing_time_limit": "50",
			"config_ping_time": "50",
			"config_ping_total": "2",
			"config_commerce": "Commerce Pro",
			"config_sms_gateway": "Twilio",
			"config_sms_gateway_id": "",
			"config_sms_gateway_password": "",
			"config_sms_textlocal_api_key": "",
			"config_twilio_from_phone": "+4232323232320",
			"config_twilio_account_sid": "asdsa23232qweasdsd4233322",
			"config_twilio_auth_token": "3212ewds34q2eas3232q23232323",
			"config_current_estimated_processing_time": "30",
			"config_cover": "",
			"config_shop_open_title": "We Are Open",
			"config_shop_open_description": "Just Open.",
			"config_shop_forced_open_title": "We Are Full Open",
			"config_shop_forced_open_description": "Needs to be opened.",
			"config_shop_closed_title": "We Are CLosed",
			"config_shop_closed_description": "Timeup.",
			"config_shop_forced_closed_title": "We Are Banned",
			"config_shop_forced_closed_description": "We are sorry.",
			"delivery_address": "mandatory",
			"config_migaprint_type": "1",
			"config_can_change_commerce": "0",
			"created_at": "2020-05-06 20:33:37",
			"id": "1"
		}
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No setting found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/settings",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**All App Owners/Admins**

---
  
  This method will load all the app owners/admins created in the system.

  * **URL**

  	/migaprintv2/api/appowners

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": [
			{
				"customer_id": "23",
				"app_id": "4",
				"civility": null,
				"firstname": "John",
				"lastname": "Doe",
				"nickname": "",
				"email": "j.doe@gmail.com",
				"password": "712d7cc555fa100c4eb30929d907399d7f1af124",
				"language": "",
				"image": null,
				"is_custom_image": "0",
				"show_in_social_gaming": "0",
				"can_access_locked_features": "0",
				"is_active": "1",
				"gdpr_token": null,
				"privacy_policy": "1",
				"communication_agreement": "0",
				"session_uuid": null,
				"created_at": "2019-10-11 11:11:10",
				"updated_at": "2019-10-11 11:11:10",
				"id": "23"
			},
			{
				"customer_id": "30",
				"app_id": "4",
				"civility": null,
				"firstname": "Johny",
				"lastname": "Angel",
				"nickname": "",
				"email": "ja@gmail.com",
				"password": "7c4a8d09ca3762af61e59520943dc26494f8941b",
				"language": "",
				"image": null,
				"is_custom_image": "0",
				"show_in_social_gaming": "0",
				"can_access_locked_features": "0",
				"is_active": "1",
				"gdpr_token": null,
				"privacy_policy": "1",
				"communication_agreement": "0",
				"session_uuid": null,
				"created_at": "2019-12-05 13:46:51",
				"updated_at": "2019-12-05 13:46:51",
				"id": "30"
			}
		]
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No customer found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/appowners",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**Printer Logs**

---
  This method will load all the printer logs created in the system.

  * **URL**

  	/migaprintv2/api/printerlogs

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": [
			{
				"log_id": "7444",
				"app_id": "4",
				"value_id": "315",
				"order_id": "38",
				"custom_order_id": "9",
				"printer_restaurant_id": "12589053",
				"log_query_string": "a=12589053&o=2_9&ak=accepted&dt=12:12",
				"log_called_by": "API",
				"log_call_type": "Call back.",
				"log_status": "Confirmed",
				"log_type": "1",
				"created_at": "2020-08-12 11:01:48",
				"name": "Test App",
				"printer_id": "7",
				"printer_title": "Printer Pro 01"
			},
			{
				"log_id": "7443",
				"app_id": "4",
				"value_id": "315",
				"order_id": "38",
				"custom_order_id": "9",
				"printer_restaurant_id": "12589053",
				"log_query_string": "a=12589053&u=12589053&p=179334",
				"log_called_by": "API",
				"log_call_type": "Order patch.",
				"log_status": "Processing",
				"log_type": "1",
				"created_at": "2020-08-12 11:01:18",
				"name": "Test App",
				"printer_id": "7",
				"printer_title": "Printer Pro 01"
			},
		]
	}		

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No printer log found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/printerlogs",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**System Logs**

---
  
  This method will load all the system logs created in the system.

  * **URL**

  	/migaprintv2/api/systemlogs

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": [
			{
				"log_id": "7444",
				"app_id": "4",
				"value_id": "315",
				"order_id": "0",
				"custom_order_id": "0",
				"printer_restaurant_id": "",
				"log_query_string": "Database Error",
				"log_called_by": "API",
				"log_call_type": "Call back.",
				"log_status": "",
				"log_type": "2",
				"created_at": "2020-08-12 11:01:48",
				"name": "Test App",
				"printer_id": "0",
				"printer_title": ""
			},
			{
				"log_id": "7443",
				"app_id": "4",
				"value_id": "315",
				"order_id": "0",
				"custom_order_id": "0",
				"printer_restaurant_id": "",
				"log_query_string": "Connection Error",
				"log_called_by": "API",
				"log_call_type": "",
				"log_status": "",
				"log_type": "2",
				"created_at": "2020-08-12 11:01:18",
				"name": "Test App",
				"printer_id": "0",
				"printer_title": ""
			},
		]
	}		

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No system log found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/systemlogs",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None

---

**Notification Templates**

---
  
  This method will load all the notification templates created in the system.

  * **URL**

  	/migaprintv2/api/notificationtemplates

  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **Data Params**
  
  	None

  * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": {
			"notification_id": "1",
			"app_id": "4",
			"value_id": "315",
			"notification_processing_status": "1",
			"notification_processing_sent_by": "a:2:{i:2;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_processing_title": "Processing Notification",
			"notification_processing_body": "Dear @@firstname@@,\r\n\r\n                There is the order no. @@custom_order_id@@ received at @@order_date@@ from store @@store_name@@ that still in PROCESSING since @@order_processing_minutes@@ minutes.\r\n\r\n                Login to @@domain@@ with your email @@email@@ and check the order manually.\r\n\r\n\r\n                MIGASTONE SUPPORT TEAM.",
			"notification_ping_status": "1",
			"notification_ping_sent_by": "a:2:{i:2;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_ping_title": "Ping Notification",
			"notification_ping_body": "Dear @@firstname@@,\r\n\r\n                Warning! Your printer from store @@store_name@@ seems not online during the past @@order_ping_minutes@@ minutes, please check if the printer is turned on or the sim card has credits.\r\n\r\n                Last time we saw your printer online was: @@last_order_date@@\r\n\r\n                If the problem persist Login to @@domain@@ with your email @@email@@ and check the order manually.\r\n\r\n\r\n                MIGASTONE SUPPORT TEAM.",
			"notification_suspend_status": "1",
			"notification_suspend_sent_by": "a:2:{i:2;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_suspend_title": "Suspended Notification",
			"notification_suspend_body": "Dear @@firstname@@,\r\n\r\n                We moved the order no. @@custom_order_id@@ dated @@order_date@@ from store @@store_name@@ to SUSPENDED STATUS because we reported a conflict between the PRINTER LAST ORDER PRINTED and the ONLINE PROCESSING ORDER.\r\n\r\n                The printer is not aligned to the server.\r\n\r\n                We solved automatically the problem but you should login and fix the SUSPENDED ORDER manually.\r\n\r\n                Please login to @@domain@@ with your email @@email@@.\r\n\r\n\r\n                MIGASTONE SUPPORT TEAM.",
			"notification_refund_status": "1",
			"notification_refund_sent_by": "a:4:{i:1;s:1:\"1\";i:2;s:1:\"1\";i:4;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_refund_title": "Refund Notification",
			"notification_refund_body": "Dear @@order_customer_firstname@@,\r\n\r\n                Your order having order # @@custom_order_id@@ from store @@store_name@@ has been rejected. You have paid @@order_total@@ for this order on @@order_date@@ using paypal.\r\n\r\n                Your refund has been initiated and will be processed soon.\r\n\r\n\r\n                Thanks,\r\n                Pizzaria Team.",
			"notification_status_status": "1",
			"notification_status_sent_by": "a:4:{i:1;s:1:\"1\";i:2;s:1:\"1\";i:4;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_status_title": "Order Status Notification",
			"notification_status_body": "Dear @@order_customer_firstname@@,\r\n\r\n                Your order having order # @@custom_order_id@@ from store @@store_name@@ has been changed to status '@@order_status@@'.\r\n\r\n\r\n                Thanks,\r\n                Pizzaria Team.",
			"notification_pdt_status": "1",
			"notification_pdt_sent_by": "a:2:{i:1;s:1:\"1\";i:4;s:1:\"1\";}",
			"notification_pdt_title": "Preferred Delivery Time Notification",
			"notification_pdt_body": "Dear @@order_customer_firstname@@,\r\n\r\n                Preferred delivery time for the order having order # @@custom_order_id@@ from store @@store_name@@ has been changed from @@selected_preferred_delivery_time@@ to @@updated_preferred_delivery_time@@.\r\n\r\n\r\n                Thanks,\r\n                Pizzaria Team.",
			"notification_sms_status": "1",
			"notification_sms_sent_by": "Array",
			"notification_sms_title": "SMS",
			"notification_sms_body": "Dear @@firstname@@, Order #: @@custom_order_id@@, Store: @@store_name@@, Date: @@order_date@@, Customer: @@order_customer_firstname@@, Link: @@order_link@@",
			"notification_order_status": "1",
			"notification_order_sent_by": "a:2:{i:2;s:1:\"1\";i:5;s:1:\"1\";}",
			"notification_order_title": "New Order Notification",
			"notification_order_body": "Dear @@firstname@@,\r\n\t\t\t\t\r\n                A new order has been placed. Below are the details of the order:\r\n\t\t\t\t\r\n\t\t\t\tOrder #: @@custom_order_id@@\r\n\t\t\t\tStore: @@store_name@@,\r\n\t\t\t\tDate: @@order_date@@\r\n\t\t\t\tCustomer: @@order_customer_firstname@@\r\n\t\t\t\tStatus: @@order_status@@\r\n\r\n                Thanks,\r\n                Pizzaria Team.",
			"created_at": "2020-05-06 20:37:45",
			"id": "1"
		}
	}	

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "No system log found.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/notificationtemplates",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None


## Printer Callbacks for Fetching Orders & Updating Order Status in Real Time

---

**Get or Fetch Order**

----
  
  This method is not a generic method like any other methods stated above. All the other method stated above are `read-only`. Whenever a client will call this method, it will fetch the `latest order` from the database having status either `Queue` or `Processing`. It will tell the client that what was the `old status` of the order before you fetched and what is the `current status` of the order. 
  
  Usually an order which is not fetched yet has a status of `Queue`. When an order is fetched for the first time it's status is immediately changed to `Processing`. And it will remain in the order list until it's status is changed to any other status other than `Queue` or `Processing`.

  Below are steps that will explain how this method will work:

  1) When a client will call this method it will be looking for an order with status either `Queue = 3` or `Processing = 4`.

  2) If their is such an order, it will return a `JSON` with `order code` that `printer` reads & client should feed that into printer programmatically.

  3) Now the order status is updated from `Queue` or `Processing`.

  4) When the `order code` is feeded to the `printer`, printer will wait for the feedback from client using `OK/Accept` and `KO/Reject` buttons.

  5) Than printer send the feedback to printer's `call back URL` and than again it will be the responsibility of the programmer to updated the `Migaprintv2` system using `API call back method` which can be accessed using `/migaprintv2/api/updateorderstatus?query_string`.

  6) When API callback method receives the call it will updated the `order status` according to the client's selection using `OK/Accept` and `KO/Reject` buttons.

  7) Printer limit for maximum receipt size is `1024 bytes` and order equals to or less than `1024 bytes` will be considered `"order_type": "Normal Length"`. And such order can be processed as stated in above steps.

  8) If you see `"order_type": "Long Receipt"` than consider this order as a `partial content order`.

  9) `Long Receipt` means that order code size is greater than `1024 bytes`. So now you need to process the order partially into chunks `1024 bytes` until you reached the end.

  10) If you are using a web server for printer calls, than your server must support status `HTTP/1.1 206 Partial Content` header.

  11) Pinter will keep on calling the get/fetch order callback until it receives the whole order.

  12) Our API will create that order `chunks` for you and keep you posted until order completes.

  13) Printer when reads the end it will move to status callback automatically.

  For more information about partial order see the bellow picture from official printer documentation to understand the flow:


[![Migaprintv2 Logo](https://github.com/migastone/migaprint-api/blob/master/docs_images/printer.png)](https://migastone.kartra.com/checkout/78c34c2b72c90b466b5d8d1cd24e5b1d)

  * **URL**

  	/migaprintv2/api/getorder?a=12589053&u=12589053&p=179334
	  
  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **GET/Query-String Params**

    **Required:**

	`a = [string]` 

	`u = [string]`
	
	(a = username/printer id/restaurant-id , u = username/printer id/restaurant-id : `[string]` will be your printer's username/printer id/restaurant-id e.g. `12589053`)

	`p = [string]` 
	
	(p = password : `[string]` will be your printer's password e.g. `179334`)

  * **Data Params**
  
  	None

 * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	//normal length
	{
		"error": null,
		"data": {
			"receipt_order_id": "2_9",
			"order_id": "38",
			"store_id": "2",
			"custom_order_id": "9",
			"order_code": "#12589053**2_9*CLIENT\\r------------------------------\\John Doe\\rNew York,USA\\rCAP 12344\\r+2322346824578\\r------------------------------\\rORDER n 2_9\\r------------------------------\\r1;Pizza 01;USD6.00;Format: Lovely;;;Option:;;;1;Option 01;USD1.02;Choice: Choice 01, Choice 02;;;\\rProducts: 1, Options: 1;;;**;;;------------------------------\\rTOTAL USD6.12\\r------------------------------\\rDELIVERY Delivery\\rPAYMENT Cash\\rDATE 03/08/2020 09:22:18\\rCOMMENTS Preferred Delivery Time:06/08/2020 12:21\\r\\r\\r\\r\\r;;;;*#",
			"order_type": "Normal Length",
			"order_old_status_code": 3,
			"order_old_status": "Queued",
			"order_current_status_code": 4,
			"order_current_status": "Processing",
			"order_date": "03/08/2020 09:22:18"
		}
	}

	//long receipt
	{
		"error": null,
		"data": {
			"receipt_order_id": "3_9",
			"order_id": "39",
			"store_id": "2",
			"custom_order_id": "10",
			"order_code": "#12589053**3_9*CLIENT\\r------------------------------\\John Doe\\rNew York,USA\\rCAP 12344\\r+2322346824578\\r------------------------------\\rORDER n 3_9\\r------------------------------\\r1;Pizza 01;USD6.00;Format: Lovely;;;Option:;;;1;Option 01;USD1.02;Choice: Choice 01, Choice 02;;;\\rProducts: 1, Options: 1;;;**;;;------------------------------\\rTOTAL USD6.12\\r------------------------------\\rDELIVERY Delivery\\rPAYMENT Cash\\rDATE 03/08/2020 09:22:18\\rCOMMENTS Preferred Delivery Time:06/08/2020 12:21\\r\\r\\r\\r\\r;;;;*#",
			"order_type": "Long Receipt",
			"order_old_status_code": 3,
			"order_old_status": "Queued",
			"order_current_status_code": 4,
			"order_current_status": "Processing",
			"order_date": "03/08/2020 09:22:18"
		}
	}	

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "CRON is running.", "data": null }` OR 
	
	`{ "error": "Printer is not allowed.", "data": null }` OR 
	
	`{ "error": "No product found.", "data": null }` OR 
	
	`{ "error": "No order found.", "data": null }` OR 
	
	`{ "error": "Invalid printer credentials.", "data": null }` OR 
	
	`{ "error": "No query string was present.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/getorder?a=12589053&u=12589053&p=179334",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;


		// If order is partial or long receipt & you are using PHP for pinter then this is the valid response header
		header( "HTTP/1.1 206 Partial Content" );
		header( "Accept-Ranges: $start_range-$end_range" );
		header( "Content-Range: bytes $start_range-$end_range/$order_length" );
		header( "Content-Length: $content_length" );
		header( "Content-Type: text/plain" );

```

  * **Notes:**

	None

---

**Update Order or Order Status**

----
  
  This method is not a generic method like any other methods stated above. All the other method stated above are `read-only`. This method will be used to send callback for updating the order status. This will be called when client either press `OK/Accept` or `KO/Reject` buttons. Programmer should send a feedback to this mehtod also so that order status gets updated on the `Migaprintv2` system too.

  Client can optionally changed the `delivery time` from printer too that can be sent to the API using `dt` parameter.

  This method will really change the status in the system so mind it.


* **URL**

  	/migaprintv2/api/updateorderstatus?a=12589053&o=2_9&ak=accepted&dt=12:12
	  
  * **Method:**

	`POST`
  
  * **POST Params**

    **Required:**

	`o4FLb6OWVq6vXgaes1zNS0NDKhQM44 = [string]` 
	
	(TOKEN_KEY = TOKEN : `[string]` will be your API token e.g. `9aefe2-41299b-03f28f-e998cd-676496`)

	`slug = [string]` 
	
	(API_SLUG_KEY = API_SLUG : `[string]` will be your API slug which will always be `foodprintv2-official`)

  * **GET/Query-String Params**

    **Required:**

	`a = [string]` 
	
	(a = username/printer id/restaurant-id : `[string]` will be your printer's username/printer id/restaurant-id e.g. `12589053`)

	`o = [string]` 
	
	(o = order id : `[string]` will be your order id that printer has for the order e.g. `2_9`)

	**Optional:**

	`dt = [string]` 
	
	(dt = delivery time : `[string]` will be the delivery time that is change from the printer e.g. `12:12`)

  * **Data Params**
  
  	None

 * **Success Response:**

  	* **Code:** 200
	  
    * **Content:** 
	
```javascript 
	
	{
		"error": null,
		"data": {
			"receipt_order_id": "2_9",
			"order_id": "38",
			"store_id": "2",
			"custom_order_id": "9",
			"order_status": "Confirmed"
		}
	}

```
 
  * **Error Response:**
  
    * **Code:** 200
	  
    * **Content:**
	
	`{ "error": "Wrong order id.", "data": null }` OR 
	
	`{ "error": "Invalid printer credentials.", "data": null }` OR 
	
	`{ "error": "No query string was present.", "data": null }`

  * **Sample Call:**

```php
	
	<?php

		$curl = curl_init();

		curl_setopt_array( $curl , [
			CURLOPT_URL => "https://[DOMAIN]/migaprintv2/api/updateorderstatus?a=12589053&o=2_9&ak=accepted&dt=12:12",
			CURLOPT_RETURNTRANSFER => true,
			CURLOPT_ENCODING => "",
			CURLOPT_MAXREDIRS => 10,
			CURLOPT_TIMEOUT => 0,
			CURLOPT_FOLLOWLOCATION => true,
			CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
			CURLOPT_CUSTOMREQUEST => "POST",
			CURLOPT_POSTFIELDS => [ 
				'o4FLb6OWVq6vXgaes1zNS0NDKhQM44' => '9aefe2-41299b-03f28f-e998cd-676496' , 
				'slug' => 'foodprintv2-official' , 
			] , 
			CURLOPT_HTTPHEADER => [
				"Cookie: editor=inqrclv4bdh6asohlku5b7f4oo"
			] , 
		] );

		$response = curl_exec($curl);

		curl_close($curl);
		echo $response;

```

  * **Notes:**

	None


