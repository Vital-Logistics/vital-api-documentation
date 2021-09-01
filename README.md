# Vital Logistics v1 API Documentation

Main URL: https://www.vitallogistics.ca/
Endpoints:

1. [Rate Quote](#RateQuote)
2. [Shipment](#Shipment)
3. [List](#List)
4. [Tracking](#Tracking)
5. [Void](#Void)

## <a name="RateQuote"></a>Rate Quote

|  |  |
| --- | --- |
| Authorization | Bearer Token |
| Endpoint | /api/v1/orders/rates |
| Method | GET |
| Request Example | See [Rate Quote Request Examples](#RateQuoteRequestExamples) |
| Response Example | See [Rate Quote Response Examples](#RateQuoteResponseExamples) |

## <a name="Shipment"></a>Shipment

|  |  |
| --- | --- |
| Authorization | Bearer Token |
| Endpoint | /api/v1/orders/ship |
| Method | POST |
| Request Example | See [Shipment Request Examples](#ShipmentRequestExamples) |
| Response Example | See [Shipment Response Examples](#ShipmentResponseExamples) |

## <a name="List"></a>List

|  |  |
| --- | --- |
| Authorization | Bearer Token |
| Endpoint | /api/v1/shipments/list |
| Method | GET |
| Request Example | *No request body needed* |
| Response Example | See [List Response Examples](#ListResponseExamples) |

## <a name="Tracking"></a>Tracking

\*\* Currently being refactored. Expected to be available by 2021-09-01 17:00 PT \*\*

|  |  |
| --- | --- |
| Authorization | Bearer Token |
| Endpoint | /api/v1/shipments/tracking |
| Method | GET |
| Request Example | See [Tracking Request Examples](#RequestExamples) |
| Response Example | See [Tracking Response Examples](#TrackingResponseExamples) |

## <a name="Void"></a>Void

|  |  |
| --- | --- |
| Authorization | Bearer Token |
| Endpoint | /api/v1/shipments/void |
| Method | POST |
| Request Example | ```{ "tracking_no":"1Z0596VE2093587321" }``` |
| Response Example | ```Shipment Voided``` |

## Request Examples

<a name="RateQuoteRequestExamples"></a>
<details>
  <summary>Rate Quote request</summary>
  
  ```json
{
   "sender_name":"John Doe",
   "sender_company_name":"Vital Logistics Ltd",
   "sender_email":"john.doe@gmail.com",
   "sender_phone_number":"1234567890",
   "sender_street_line_1":"204 Queen Street South",
   "sender_street_line_2":"Suite 201",
   "sender_street_line_3":null,
   "sender_city":"Mississauga",
   "sender_zip":"L5M1L3",
   "sender_state":"ON",
   "sender_country":"CA",
   "sender_is_residential": false,
   "recipient_name":"Jane Doe",
   "recipient_company_name":"Jane Doe Ltd",
   "recipient_email":"jane.doe@gmail.com",
   "recipient_phone_number":"987654321",
   "recipient_street_line_1":"160 Tycos Drive",
   "recipient_street_line_2":"Unit 124",
   "recipient_street_line_3":null,
   "recipient_city":"Toronto",
   "recipient_zip":"M6B1W8",
   "recipient_state":"ON",
   "recipient_country":"CA",
   "recipient_is_residential":false,
   "shipment_date":"2020-05-25",
   "package_type":"02",
   "package_count":"1",
   "billing_account":"default",
   "billing_duties_dhl":"default",
   "customs_terms_trade":"default",
   "direct_delivery":false,
   "ups_carbon_neutral":false,
   "saturday_delivery":false,
   "service":null,
   "packages":[
      {
         "length":"6",
         "width":"6",
         "height":"6",
         "dimensions_unit":"IN",
         "weight":"1",
         "weight_unit":"LBS",
         "declared_value":null,
         "cod":false,
         "cod_payment_method":null,
         "cod_value":null,
         "delivery_confirmation":false,
         "delivery_confirmation_value":null,
         "additional_handling":false,
         "ups_premium":false,
         "reference_number_1":null,
         "reference_number_2":null,
         "reference_number_barcode":false
      }
   ]
}
  ```
  
</details>

<a name="ShipmentRequestExamples"></a>
<details>
  <summary>Shipment request</summary>
  
  ```json
  {
   "sender_name":"John Doe",
   "sender_company_name":"Vital Logistics Ltd",
   "sender_email":"john.doe@gmail.com",
   "sender_phone_number":"123456789",
   "sender_street_line_1":"204 Queen Street South",
   "sender_street_line_2":"Suite 201",
   "sender_street_line_3":null,
   "sender_city":"Mississauga",
   "sender_zip":"L5M1L3",
   "sender_state":"ON",
   "sender_country":"CA",
   "sender_is_residential": false,
   "recipient_name":"Jane Doe",
   "recipient_company_name":"Jane Doe Ltd",
   "recipient_email":"jane.doe@gmail.com",
   "recipient_phone_number":"987654321",
   "recipient_street_line_1":"160 Tycos Drive",
   "recipient_street_line_2":"Unit 124",
   "recipient_street_line_3":null,
   "recipient_city":"Toronto",
   "recipient_zip":"M6B1W8",
   "recipient_state":"ON",
   "recipient_country":"CA",
   "recipient_is_residential":false,
   "shipment_date":"2020-05-25",
   "package_type":"02",
   "package_count":"1",
   "billing_account":"default",
   "billing_duties_dhl":"default",
   "customs_terms_trade":"default",
   "direct_delivery":false,
   "ups_carbon_neutral":false,
   "saturday_delivery":false,
   "service":14,
   "packages":[
      {
         "description": "asdas",
         "length":"6",
         "width":"6",
         "height":"6",
         "dimensions_unit":"IN",
         "weight":"1",
         "weight_unit":"LBS",
         "declared_value":null,
         "cod":false,
         "cod_payment_method":null,
         "cod_value":null,
         "delivery_confirmation":false,
         "delivery_confirmation_value":null,
         "additional_handling":false,
         "ups_premium":false,
         "reference_number_1":null,
         "reference_number_2":null,
         "reference_number_barcode":false
      }
   ],
   "selectedRates":{
      "dates":{
         "Pickup":{
            "Time":"6:30 PM Monday",
            "Date":"25 May 2020"
         },
         "Arrival":{
            "Time":"10:30 AM Tuesday",
            "Date":"26 May 2020"
         }
      },
      "disclaimers":{
         "Code":"01",
         "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
      },
      "billing_weight":"2.0",
      "billing_weight_unit":"LBS",
      "accessorials":[
         {
            "Code":"375",
            "CurrencyCode":"CAD",
            "MonetaryValue":"5.15",
            "Name":"Fuel Surcharge"
         }
      ],
      "service_code":"14",
      "service_name":"UPS Express Early",
      "zone_number":"700",
      "base_service_charge":{
         "value":"66.40",
         "currency":"CAD"
      },
      "fuel_surchage":"8.96",
      "pre_tax_subtotal":{
         "value":"75.36",
         "currency":"CAD"
      },
      "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
      "total_charges":{
         "value":"75.36",
         "currency":"CAD"
      },
      "tax_charges":{
         "MonetaryValue":"9.8",
         "Type":"HST"
      },
      "total_charges_with_taxes":{
         "value":"85.16",
         "currency":"CAD"
      },
      "user_rate_id":"1838384"
   }
}
  ```
  
</details>

## Response Examples

<a name="RateQuoteResponseExamples"></a>
<details>
  <summary>Rate Quote request</summary>
  
  ```json
  {
   "rates":[
      {
         "dates":{
            "Pickup":{
               "Time":"6:30 PM Monday",
               "Date":"22 January 2018"
            },
            "Arrival":{
               "Time":"9:00 AM Tuesday",
               "Date":"23 January 2018"
            }
         },
         "disclaimers":{
            "Code":"01",
            "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
         },
         "billing_weight":"8.0",
         "billing_weight_unit":"LBS",
         "accessorials":[
            {
               "Code":"375",
               "CurrencyCode":"CAD",
               "MonetaryValue":"10.51",
               "Name":"Fuel Surcharge"
            }
         ],
         "service_code":"14",
         "service_name":"UPS Express Early",
         "zone_number":"707",
         "base_service_charge":{
            "value":95.5,
            "currency":"CAD"
         },
         "fuel_surchage":10.51,
         "pre_tax_subtotal":{
            "value":106.01,
            "currency":"CAD"
         },
         "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
         "total_charges":{
            "value":106.01,
            "currency":"CAD"
         },
         "tax_charges":{
            "Type":"GST",
            "MonetaryValue":"5.30"
         },
         "total_charges_with_taxes":{
            "value":111.31,
            "currency":"CAD"
         }
      },
      {
         "dates":{
            "Pickup":{
               "Time":"6:30 PM Monday",
               "Date":"22 January 2018"
            },
            "Arrival":{
               "Time":"10:30 AM Tuesday",
               "Date":"23 January 2018"
            }
         },
         "disclaimers":{
            "Code":"01",
            "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
         },
         "billing_weight":"8.0",
         "billing_weight_unit":"LBS",
         "accessorials":[
            {
               "Code":"375",
               "CurrencyCode":"CAD",
               "MonetaryValue":"8.58",
               "Name":"Fuel Surcharge"
            }
         ],
         "service_code":"01",
         "service_name":"UPS Express",
         "zone_number":"407",
         "base_service_charge":{
            "value":78,
            "currency":"CAD"
         },
         "fuel_surchage":8.58,
         "pre_tax_subtotal":{
            "value":86.58,
            "currency":"CAD"
         },
         "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
         "total_charges":{
            "value":86.58,
            "currency":"CAD"
         },
         "tax_charges":{
            "Type":"GST",
            "MonetaryValue":"4.33"
         },
         "total_charges_with_taxes":{
            "value":90.91,
            "currency":"CAD"
         }
      },
      {
         "dates":{
            "Pickup":{
               "Time":"6:30 PM Monday",
               "Date":"22 January 2018"
            },
            "Arrival":{
               "Time":"3:00 PM Tuesday",
               "Date":"23 January 2018"
            }
         },
         "disclaimers":{
            "Code":"01",
            "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
         },
         "billing_weight":"8.0",
         "billing_weight_unit":"LBS",
         "accessorials":[
            {
               "Code":"375",
               "CurrencyCode":"CAD",
               "MonetaryValue":"6.92",
               "Name":"Fuel Surcharge"
            }
         ],
         "service_code":"13",
         "service_name":"UPS Express Saver",
         "zone_number":"507",
         "base_service_charge":{
            "value":62.9,
            "currency":"CAD"
         },
         "fuel_surchage":6.92,
         "pre_tax_subtotal":{
            "value":69.82,
            "currency":"CAD"
         },
         "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
         "total_charges":{
            "value":69.82,
            "currency":"CAD"
         },
         "tax_charges":{
            "Type":"GST",
            "MonetaryValue":"3.49"
         },
         "total_charges_with_taxes":{
            "value":73.31,
            "currency":"CAD"
         }
      },
      {
         "dates":{
            "Pickup":{
               "Time":"6:30 PM Monday",
               "Date":"22 January 2018"
            },
            "Arrival":{
               "Time":"11:30 PM Wednesday",
               "Date":"24 January 2018"
            }
         },
         "disclaimers":{
            "Code":"01",
            "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
         },
         "billing_weight":"8.0",
         "billing_weight_unit":"LBS",
         "accessorials":[
            {
               "Code":"375",
               "CurrencyCode":"CAD",
               "MonetaryValue":"6.50",
               "Name":"Fuel Surcharge"
            }
         ],
         "service_code":"02",
         "service_name":"UPS Expedited",
         "zone_number":"307",
         "base_service_charge":{
            "value":59.05,
            "currency":"CAD"
         },
         "fuel_surchage":6.5,
         "pre_tax_subtotal":{
            "value":65.55,
            "currency":"CAD"
         },
         "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
         "total_charges":{
            "value":65.55,
            "currency":"CAD"
         },
         "tax_charges":{
            "Type":"GST",
            "MonetaryValue":"3.28"
         },
         "total_charges_with_taxes":{
            "value":68.83,
            "currency":"CAD"
         }
      },
      {
         "dates":{
            "Pickup":{
               "Time":"6:30 PM Monday",
               "Date":"22 January 2018"
            },
            "Arrival":{
               "Time":"11:30 PM Friday",
               "Date":"26 January 2018"
            }
         },
         "disclaimers":{
            "Code":"01",
            "Description":"Taxes are included in the shipping cost and apply to the transportation charges but additional duties\/taxes may apply and are not reflected in the total amount due."
         },
         "billing_weight":"8.0",
         "billing_weight_unit":"LBS",
         "accessorials":[
            {
               "Code":"375",
               "CurrencyCode":"CAD",
               "MonetaryValue":"5.60",
               "Name":"Fuel Surcharge"
            }
         ],
         "service_code":"11",
         "service_name":"UPS Standard",
         "zone_number":"207",
         "base_service_charge":{
            "value":43.05,
            "currency":"CAD"
         },
         "fuel_surchage":5.6,
         "pre_tax_subtotal":{
            "value":48.65,
            "currency":"CAD"
         },
         "rated_shipment_warnings":"Your invoice may vary from the displayed reference rates",
         "total_charges":{
            "value":48.65,
            "currency":"CAD"
         },
         "tax_charges":{
            "Type":"GST",
            "MonetaryValue":"2.43"
         },
         "total_charges_with_taxes":{
            "value":51.08,
            "currency":"CAD"
         }
      }
   ]
}
  ```
  
</details>

<a name="ShipmentResponseExamples"></a>
<details>
  <summary>Shipment Response</summary>
  
  ```json
  {
   "ShipmentCharges":{
      "TransportationCharges":{
         "CurrencyCode":"CAD",
         "MonetaryValue":"106.01"
      },
      "ServiceOptionsCharges":{
         "CurrencyCode":"CAD",
         "MonetaryValue":"0.00"
      },
      "TotalCharges":{
         "CurrencyCode":"CAD",
         "MonetaryValue":"106.01"
      }
   },
   "NegotiatedRates":{
      "NetSummaryCharges":{
         "GrandTotal":{
            "CurrencyCode":"CAD",
            "MonetaryValue":"104.95"
         }
      }
   },
   "BillingWeight":{
      "UnitOfMeasurement":{
         "Code":"LBS",
         "Description":"Pounds"
      },
      "Weight":"8.0"
   },
   "ShipmentIdentificationNumber":"1ZA481E21528166753",
   "PackageResults":{
      "TrackingNumber":"1ZA481E21528166753",
      "ServiceOptionsCharges":{
         "CurrencyCode":"CAD",
         "MonetaryValue":"0.00"
      },
      "LabelImage":{
         "LabelImageFormat":{
            "Code":"GIF"
         },
         "GraphicImage":"R0lGODdheAUgA+cAAAAAAAEBAQICAgMDAwQEBAUFBQYGBgcHBwgICAkJCQoKCgsLCwwMDA0NDQ4ODg8PDxAQEBERERISEhMTExQUFBUVFRYWFhcXFxgYGBkZGRoaGhsbGxwcHB0dHR4eHh8fHyAgICEhISIiIiMjIyQkJCUlJSYmJicnJygoKCkpKSoqKisrKywsLC0tLS4uLi8vLzAwMDExMTIyMjMzMzQ0NDU1NTY2Njc3Nzg4ODk5OTo6Ojs7Ozw8PD09PT4+Pj8\/P0BAQEFBQUJCQkNDQ0REREVFRUZGRkdHR0hISElJSUpKSktLS0xMTE1NTU5OTk9PT1BQUFFRUVJSUlNTU1RUVFVVVVZWVldXV1hYWFlZWVpaWltbW1xcXF1dXV5eXl9fX2BgYGFhYWJiYmNjY2RkZGVlZWZmZmdnZ2hoaGlpaWpqamtra2xsbG1tbW5ubm9vb3BwcHFxcXJycnNzc3R0dHV1dXZ2dnd3d3h4eHl5eXp6ent7e3x8fH19fX5+fn9\/f4CAgIGBgYKCgoODg4SEhIWFhYaGhoeHh4iIiImJiYqKiouLi4yMjI2NjY6Ojo+Pj5CQkJGRkZKSkpOTk5SUlJWVlZaWlpeXl5iYmJmZmZqampubm5ycnJ2dnZ6enp+fn6CgoKGhoaKioqOjo6SkpKWlpaampqenp6ioqKmpqaqqqqurq6ysrK2tra6urq+vr7CwsLGxsbKysrOzs7S0tLW1tba2tre3t7i4uLm5ubq6uru7u7y8vL29vb6+vr+\/v8DAwMHBwcLCwsPDw8TExMXFxcbGxsfHx8jIyMnJycrKysvLy8zMzM3Nzc7Ozs\/Pz9DQ0NHR0dLS0tPT09TU1NXV1dbW1tfX19jY2NnZ2dra2tvb29zc3N3d3d7e3t\/f3+Dg4OHh4eLi4uPj4+Tk5OXl5ebm5ufn5+jo6Onp6erq6uvr6+zs7O3t7e7u7u\/v7\/Dw8PHx8fLy8vPz8\/T09PX19fb29vf39\/j4+Pn5+fr6+vv7+\/z8\/P39\/f7+\/v\/\/\/ywAAAAAeAUgA0AI\/gABCBxIsKDBgwgTKlzIsKHDhxAjSpxIsaLFixgzatzIsaPHjyBDihxJsqTJkyhTqlzJsqXLlzAx\/ptJs6bNmzhz6tzJs6fPn0CDCh1KdCeAokiTKl3KtKnTp1CjSp1KtapRglazat3KVerDrmChFgxLtqzZs1cbol3LtuzRtnDjmn0rt67du3jz6kU6dq\/fv1O\/Aj7bd7Dhw1QFI14Mly7jx3gd66QIubLly5iFFs7Mea\/izmKxgh79+DPp03xRqw68urXr14w3w56d2CFtorJv6+5qejdsyb6D0wQuvLjx40BzI1+Oszfzf8qfS\/\/pfDrbg7it3yZ+U2Bz7trD\/ou\/G3288OrLy5sPj349V4Wa3a8GX5Oy\/Pv4aw\/8Kzp\/1Pb6qXddf\/5pByB+LSVXIGj0dafWghBGOJSAM8VEoIRJHegVdnlRiKFuGsp3IU8eDrcfdR9a1mCFK9bXYoowulcidAa9N2KMydkWFkJ6zYjjfDp+eONkQ+ZUZHc\/LvaiifAp1eKJSUbZmY8semejlVJSF6SWFvIY2JFZAvmgkFD65COY9YUJ2JJqtokhlW56tuWVcIJVZ5yQhShjmT2dyadReHa4YVFPYhnooZGhydeYiGY451ZeJvpnoww+CqGiTBra56RGUirXi5w66OmorlHpEqkuMkonpnOxiqph\/nquJ9pmTdLIKatsvsrapyTaBZymuerKnqJ3LlWsg10mq5mlzB0rrK\/MFjgidglxuWSwzzqFbbbciqkpka4a62yKse7mYbLoppvgpqpGWGS74F7b7Y68NkdjZH3OK224VZ4UoLqnBlUuiMQCbPDBIJkZrX\/9TUvtkbjqy9ulZkqc37gWbwgvrPzmGGrGPS58cZmR2vqtrcjKC7JV21bVYMsk0vUnth2v7BvGE3IIMnoIV\/vlxzZDu\/G+J8fLZsRB7xqXzsP9TCt4txaddLM1O8n0qj2jtOzQJmcttbhANzawx2OfVraBYaf6dcoKTv0fYlArx92TXlXstrcwV+b1\/kpbM6Qwzk0BnnLeWJM9Uc5pv3a2da76uXaadz9FuFhI2jS3Y9\/ObTeXgUeu2rj2rbW3Sn0vJHDVSqLOm+r9Tt46cotP1\/jsjzfteecL0n37czNy3bXvo8ZeasGjF2\/81UaKjCBLbe\/uJNyd5muv5ZJdbqjrzqN2buLsSo08pcK3tv3x5B\/\/t9\/Z95p+arlbTeT6U2L6fcwlp1X7+eUnfDrwxY2f\/\/89w1+t4Fc5AsZnaTLLXPRsZzl2UY9m3JueAfVWM5lELnx4EyAAN4guDdZvgtABocA+hUHIaQx7IoQb61L4Hf6dh3gcjKGyumc6FobQhuqLX\/WKVkEefq2G\/jhUYQSDSD\/0oS1tMkxilzw4v27dT4JELGBb+ASqze3vcqJioNGeGEUSDpEzStxI6QYouxUaR3AqUp6wYIbCC2bGjGo7IRC7KKcvvjGMGRmjz47IRcLA8T9\/TKMLdVWj5tFRi1584BVr18QWKvKQ2uvYR4JWwkgiEY+YJB0NySgxYFURkoicIpTyFh3dSZFW4GvknhJXSEI1bI9yzKRE9PhB3gXyX20MHBopOMhOSg+UNySP7W75vF8+0IhEW5sq+wdDpjSylcFT4wvtCExrzVGEuXRbNjMERUBJ0ZsNZCI0A1XL5UVQf9b0VCXNBkNZujMk4tzlvLaZNHoSyoom\/gRnOHOYMwGSi3B9HB41W7jMVr1zlovkpC0HShaTwGidbQqXPW02UWdyk32I+2SmGEq1q2xqoQE1HCwbelCEinSk0pFnLFFYUFlJ81XAMiQkK6o44gDtZByFHX0eF9IMJlRrhHzpzdpZ0qJasIjXrKdGQUnTMXZTbTjd4lNbp9DfodScjmrqYfyn1WN2dVi9RKAncwpV\/hhPp2GNJvVQVM2vVrM0bjUrK1WaPGIyTKiNyZEziWrUvh5uk1fVF7\/iyi3CvhVrFwEpBIG6Ur+2dKNVjeNjtVVXwNE1ND2FlF1jg9fgDVOmhzTsYe922QmGryKuRN4KuerY1qoRolmK\/mw+Zzpa8TmsnGdEXS9he1fgIRNScXQZX11LXNxCVbbZessQRbvGyv5qsrXVbFpiptiTJhawLC2ucQmaVGQtartGW5VcR4fW33YSvBV6q02vN6TMRheQGqkuDfeqWuhGibf0y84395lV967ur+I9Dn6TZFO2ApO570WLfbcjv84e16rZ1e44sbtMkQyGtRLOcKHSSlr1OvKRWUywH9fLSASTR5LIpSWqDkRWJl14uBoubjw3m1wPDy4iIhabRVJK4zrGOFcDm7D9evorfX63xD\/W8IxbnDETr1hbTn5vaRnMZCH+mJYVhtiCT1xl4Tr0nxzWpo29iuMcrymw0\/Qv\/h1ZDE\/cmLS\/UUaqeQOc2zBPLc7qNDNmrFRmsN6vx3ZKMpCVV+UuswzGgvbrktW8MjyDT8+XYTSP52qhFTsYy9ta7wLhPF5Hb7S83TWgpxFF4mN+GNK7K9Ef+yw5QWNa1QD27r\/oK+k01zrSl24UmvlL2xvLZsqo5i6a0Esbur7ZYrGao6HT+1FGA3ureRRwrkk91WpHcdTB1tJe5evmAcNZyT8lNq2XPWsKJ7qvi8b2j9SNJ3ZnO927Dg6s4z3uVif51cOGLr0zeutnW63Nv3vTtCk55nd7GSK6bvCtr2hp3\/IUyakV8r3AhuRzEzfdOHS3mzRORMsSCCs+XPie\/gGtS5EnM9TH5QhwKb5hi7sW4422Nq9Da\/CslHq\/wt4x1cgNb8ElGt9hK3Rmnzg5DLvcqDDfmcxnS\/OaQ1tc3I54tCvb8DnvvOJHV7S5\/f1QkBuYqU5vK6IlTtARXzncW1bwDp9b761nXZZJTyHH1TT3jMsa5xE1I45JvsUMA12ZFEJ4VvPL8p6\/XYZxx2bBw\/6eNfJ9yHbOuYT\/\/rJQgdeOml56On2cU5KkZ+AUXTzjKTtCm\/M8T4\/\/d91tm1ayQ7aCB1S9xl0v533nXNqRJ3hbRw9hlHs5vKv887S9LSLQQ94tba\/94d+ZeBCuXkrPnydHV3ROMV695WYnFYCC\/t7E08MX68s\/aPNNK3reG7Ps+IwTV0maej\/7\/vW29z5mTa5DwePe6gSMPoGRHXvNzmxC\/fc+vuZDUWdu9pZ262Z8dnJqTNdt9Cd2uRd6u+dLb4RUUBZf1\/dtHiF9Dldr8neALRd+4ud2HwhT5fcssaYV8qN878ciOMJ12cNm1Adx7jNzyWd+ZGZ7qXaChVWCsveA4waDcOWD6SODk6SCN9h3IphJ4ydqPEhJ7Qdk\/FQlmyaAAyhuxdZ+zkN8DLhIeFd4OHiFtFeET7hna2Ui\/FGFocQyRlY33dN1RBiDrxUkEVh6sheGYiiEjzaBeAg2amhNqDVpXHQ1hDhOhaiH\/pA3aKZiiGPYhKnyNw50Zpe0hCPIgo24hWV4R6MUh5Y0Sjbnf\/p3aNwXN0fxMKT4XaiYWho0f\/vRiow4FpZHaADXf6WUhHjIhSbIh59TPVvVhqCCfxF3T0d2XRk4ZPhzjIPTNcoIiyDXTso4X9BYOsvYjJNSSgqYKLYoeZQYRo4IP6H4gqzHiYHGfQpzfmsYTM51jSPzRa7IjCHoHe1IjQZlVZAIWChjj\/HYjtZVUOphbMcmdYa3jeTTjevzjTFikPwGPdU2g9+jTH+Ijv81iFooiT90iRd4IYeIkRYJiF+VkVQkZDK4P+DyYuJoQ7j4ZLroRO8yiZXXkt4TdIBE\/l\/FCHyRGI2E1xexqFyzwmc7qZMtNlAnUifW2IH2RpJAyFTqSIEHVlNYqGCnM4Vo6CLpNxnmCJWJeJKpM4oj+YxB2ZOvc484yZPV6JV1lYrd9pVexTllmY70JnR1Z3QCmUQESYYpuYCzhT0vwzhHyV05aF32WIC115c\/xYp9hIArJZg\/2JZjRTJN0nnX4zQIyYHAWJCZeHB394jF9pB5GWINWEweRYXf8VF++Hla6ZGL+ZG\/ViP5eJqsuXYSpZovSU85qYRZlkDVspHCCJog2Icp15RuVJc7gltFF5kTY5PM9pSgxZakiIidZoHJ6I7wSI3RmY\/PmJaBl4LPKZ2l\/uiMQqlwk2ky2SgpexlaSSlYlVkvUXmclYIkAZV5X5ibytmC9zVYsbmKKVePiHmRH2OK9AiC09mfOXh5+uabVVly47lm5TlPJ4ia+kmgD3mOdSGFxZmcvQl1aAeY95mhr5ef4Uls5fQ0i5ia8hSShFeiAVig0sibVBVYBdZhdbmZFnWXesVlIXegK\/qdJxqgjWWjmgh4lLaVcoMrNxKkc0akwod5Q9pDHXiEzamivYebv7mUvMaL7wmRLnaGVRqhR0qVdlh\/cImdzKSVa3mWqvhpaUlmN5aMZwqWCrd5Z5qT3+mW8Dmm4Wl+Y8Oj5FJ+OLVTjLmc5cE1eEo5khOa\/ksnodBGnN8XYRoZolo2lrplpH5amK+4Wgkqiks1jE76pLWYpeb5olYJX91EpdpoqfbHmVcKoWTzdVOJmYnaXYHapBx5j4nZl\/spIKUqbKsIlOD3jjqYV12KqU6KlZ4FnFgaL1ZKYgrlezNjTx63pze1dg\/KljnKlxzJXsHnktvpqNO5rdnKrdOord36XBtojNAZgt\/qrXdihBI3fNOaoipKoqfaZOepm\/lkrXnorCz6qRFKqJyqqX\/GrzaojbNjoaRZke4YhK6pj\/zpFtz6n395UrKaiAJrq7V6nTSTPJqHjO\/KLC2KqjX2ojiqlr8qlVZqUE1pqFb4mW2or+mp\/rLUFaCvinoluaJ6RJgJ25oc+rARKZ\/wZ7Bb9qc\/OZEmKTK9Skiit0OdWbI8dIdX6Y\/\/6LFZuqzcg7LxCbAa6KC7+KzgSq8gdpnGmJAR+0hh2TJdGbQ+KZb7uJF1iKJWC5DByrFbKYFSGqPReiUZ60rIebdYlpi9o7X26S75drY+6aYm2rWYhZZlxaZmu3lle6RxSmmIWp28WR3CKiGR6y73aj3R6YJVGiyaW7SZylkz64CoGYW4aZi+lrMTG7hMSroyA5mZSrmr6kTn6YPVKEGfW7KDUqwkG7qJ6kAL24WPyI+7GrbSOpg1qYEIK6ARZql1ynuyy7YfO7dd217a\/kmYAdsqptqyvqufrHiu4XqM5Uqt7pq45Rte45ud1Lm6o4iBLLeJTMaccseuMeepMtq57Et6iHS53aum0rqaikipw3mw\/Bm8Epu8fYcyDVmp9iN1xie\/2AS30ouCR+vAN5WyUnW8E7e7wdW7\/WugfCqir8moyzWppRuHA9qdRPm8K2t6oxvBayuvIMu\/H0wwL6xNsjh1xtKuXvi2G1Nk2VtY81rDjSa0nlO5WRmzLITEujbERNxkRnxBDAxGUQzDIbuDxPrEOHzDdzbFPUrDMOXFzZXFjqLFhwLBW3zFQ8XFoibGRkvGrPqyZqx+VZzGPCtvdWxabpyL1DvHpJXH\/koVw50IxlV3x+oEpbp7bRrrx0HFxlAoyOzkyN64x5hLt2AnmrzLuYxMd4D8yGrcoEpMuH3IxAiCO328yZ7McZ1cZ58MwpJMvpNLyb9RfbSsMqcsvHSKyvPJkjFRyCnWWCHzykUoy0x5NLRjy5f8hsa6KClLyLrcw4AYkb5ctAEEuz7cyuJxzMZMdE7sf177zHiMpKF8yJBcrcE8zs5HzAK1zRLJzXBMUs0MzmuMzmYXY5THfmjsnBtbzmHKzuxMoYpMgggotfLMymRbEqQKbmmrh1gLis4cTfycZj0rlpmzqMjca77KsgW9zr+Iuk3rn36Hdoj8vvT8tZYYlxw0\/pf38UonvF1Ic8s6VtLHhzkPPVPNZLLap85JzKsojXgCXdMMyzeq2nTQt9HeW62+easkPXkinc9+8aU9DUAqXXyn2ZvtC9Adp6VxnMhG7VN8q3OCpdPfa837jM1+9pWw2af4itVBhGem1GogxqcY3NXAOo4M7WpNvcquW24nHdX5M9XBB83nw9Z2J57sVtFJS9eGg88T+XN5DafkRdZN69f\/A9gu1c6YTdgmiZ5ZpDm869lMJ5u\/vMl3PdIJt6SSbNrGGZ+U\/dc\/DYf+zHBDvWaJFJqG9bkp5tH969SpPNqq\/buS3SHa\/LT63M+GbB7aLNuzm9ViZXVA3Jlv\/c2v\/k3XcGJhdm3Pjy3T58zTre3afS3MuIbZ\/zzbXQTUQew0zMzVfsxaFAezuBTSC63Xhh2Q3X0wln3E3fyJGj2MpejBNQnaLfzM6zerxwfKTB3f4C00u1rf5XPfUZrMomSmGzzYiYHJiu22SA3WokxOYn2oC87g5jPdS5zfhj1WvjLBjMzbjK3QGa7iws3LIN7gIi53JC5d6umGn4rYUEveKS7fO8viDk5l2l3iHU6jxw3RF\/vOA9KKVNdPJ1S3N17QLr4zRW6U3B3jkf3dQy4tPM7cZqW70S3hIonLmr3ePo5sVU6Rqnzmkmtrox3G553Ybf3FAbzlF+5zR+7CZ4fg\/nau4GtePKD25igZTJdK1OE9p9t74XT20+6b0PDd4mzuRX2euekS6KBraQCo5NL8utyryZme4\/uludD3cVOu5hQOhqnbyGY9G1CN5VkT5HsY51FO21rKjvR5ThcVW7ce6UHtuESGXs2655Ce4LX+4a7uNbB+2pdo3rIi6aFGuRI8p7w+WipMjF0c0V7q4R2RgNg+vRB+HaGuhs89c+Nedp5L7IKkw\/fH7AeZ5rDKeel66XyU543c5XPe3M\/OsfTbr7q+jkOH0D3Y7V9M38deaTMOxY1T40rDvQDu6WBuqg2vmct92epu0Eh9cHh+b9nN7pzG6AXfQQd\/Xv2t3nJe\/tiKHvAVl32u\/OjJPhdtO+tgq+UfX+kh36khdDQKf\/JFOZOMzm\/0TpsytvGrzdEEP\/MBI\/Mm\/+06X6Z4y\/P8fVSS+fMPVrjJCTUsfKNGb981L5mdDuWbvfQoOO0YD+RbH8fySU1xVeqw7OyW3tCHzMP3DvZPD52mhqGTjVduD2aPy8UMiZdjl\/U0j\/Qxx456iqzQ2tWAJ8eg5kGYdpUgfeDDbqO6bb4gXPSAr0mCT1Ht+YSQOukHBlAcv9jKDNIVmtMrXHJl7PBdH\/N3f\/kzlPk0TqxeIuhEDNmrnrXiTfv3+vjadc8yD6bz7fGuvy6wr3jASYAvL+AaqW1Oj2pI\/uyWv035QD\/8S1T23pjzck+byC32yTWHY1KHXme4dd361A8TLa97MO1m1G2beS\/koW\/VQc\/nDImfccuGqE7+5X\/0+P\/+51H4Tp79APFPoEAABQ0eLDhQ4UKGDR0+hBhR4kSKBA9WxJhR40aOHT1+BNkR4ciLEUmeRJlSJICKLEEinJhS5kyaNW3exJlT506eOWPWDBlU6FCiRV26JEgRaVGmTZ0+hfpvaVSqVa1exZqVoUqtXZ\/C\/GnQq9GeZc2e5doSaFaxG9tafGsxJNixSkvWbTgS716FNvn+BSzxKNKpDwsHRpyY6eG4A1EqhhxZ8mTKVemavEt2ZmXOc9d+\/uQJOq7eoJcNo0WdWvVq1q3Dbu4cO\/Jh2bUlM07Yl7Zc2719\/wYO1bTwm1RbH0dOWi1NzI8dNhaae+tU6R6HB\/\/qF3vpz9u9f\/0evutu8eXNO4Wusfp59ZlFa8ebXD7yjPBfytRNPrp+u+nZw6XvP4zsE7DAmAxE8KUEFzTQvef8EwxCBvNb77TiiHJwQsAItKzC2TKcbj4RRySxRJJew0\/D3whzTCkVX4SIPxhnHEtGz2CjsTkP8zLROe56BPLC5XC08EEfQ+QIt+du3DEws4a0MccImZOysyNjrJLGKLPkcjH0TqLwxC6lAjHELYcq060g16QSyrSKbC4sK9N0\/oxNO+\/E80ojiRxTvDP79O5PQAdtr7G3mlwIUTIx6\/K6vd4k1Lju9txPUDJxYtLS3kJDsUoOIwVOU1BrE3VUU800lE4An+TS0R9VOzWqT1tV9dI8b8U1SBQhjbUuV\/Pqlb1SgyW22A4lrBOtZIc19r42Af311GgXnLVZWadz0dpAteVWNx6p63YlZJd91kJmw61vUgynzTbGwTKllc9Bq0V3w3pXvLfbDNnNd1VJ1V22XzXLRVLHMsel1Fxm2c21YYdH3FVPgfk6d+KrKraYWtoYs0pRDfn1SsyMIwZzSoKNTHJJYJ312NaHX4ZZWZNTHJnimivD+OYG9UN4VZF5\/pUSZIDdFFlnd0+Ot+WYl2aaU4OBNhqrnKPGkOoEe66TLEbdbbRW5TqutWZ6XeZPSLcGhBfn417FWsCxrQYPbsSmlrtGnwZsG1vRukY47Kb8tnjsg4tGWe2+m0Y8cZqPlrfuax3\/i+58QaYYLJ7r2zXdvHfumfAvKQ98aMY9hrq\/6r5+r2XINxV9daNcfxT20Vs\/VvW+MI+Q662zBJ1sEWX3WeJEPX9686z9HT5t4Ld7e3nrnB8P+thsl8ok3HdPknoEe5\/9bumHRzq\/KeUcGNPUJf\/+YtrTV4\/9jt0\/+kPb6S7dVO7hJy58cmFFkyX6Acdf5NYXQMEQMG7p04nU\/uaHvWQlSlb3+4\/iJDjB5IyvUpppy8IAaEBfDZCDKvtg1dhHneGgD05wsU56GObBpJkwhCQj3tPwtkGF\/c1rFMQh4mCIuhceqIfR2VlSvEWZBKrPfJobzU8ml6YYKkx7M9NeE7NnGil+i4bds+Li9kSekgVnhTkEI8x2CEEOujCAZrTZEIU4mSJuCIKGOhbfEFVFVK2HcHQE3xWdSEIyaoV4bwtQoQymvB8mpnmFXCMin\/cxUvHISSX5Uxt1N0U0kopO17FcbjAZtgxCskmd7Jwm9Qg+cSEvlP4B5BPjd7YaVo9lMgpjLB82xlEasJLuu+Xccsk22p3pcmhjZfaW\/jguUHqIX8UcTDJFuRvjodBl\/UEeEm2ETGdmkpkePGIaz6dIQ7KwkLv8Hjgf1Uep5bFC4lyZLr03JnKGyY6ouyM85UlFHubPPXic4Q3150xo\/g2Y24SiLAXKJlo284PodB5Cy9lFw5ktnQ86nmGuB7ZhqdJtqjocPWFi0IxeBEIfVVo9sTi+eG70k+sLJBH1OVCWrqmgFj0oN0HjNgfWlI0TNQ5Ot4K311BSjjzbl0eFqsKgisWkRi1qQo6q1KGGtKP+Wyksk7oxb0LGmOdqp0z7t0+ZKhR4Xj1hdsCaTyv60KY7NR1DR\/dAfAaNifMcalhJWbhv+e5SmYLpDO36\/lRVplKkW8wqGr\/YUsKa6KVj1RliV6dQruqtPNRTbMoKdtaETfGnIyWaOd+Z1f3x8Z5\/VUxb3Sm8fIrWdC1C7TMBWrzCtjale1SrVikr25bUyHp1\/GPjupnNh6YWreXTpB\/zalBhXZKTJ71mck2Z1\/wtV5nTVJ01o6lZ0nY2qvxEkw2JS9ut6pa2kXUcY29LvizG1otS3SxMe7cxEBJNi5eNk2qpeVe6TnaQ9LUuRhcH0uf285Vprd\/n5sRX1xaYNYflbm8TXMCQzTasILpm7TzLzPbebry5w9I\/jXgW+AJ4wundLm7J1j39gZaXH0YxgnV0QTVVOJHicqqBZbwa\/hVv8ZsL1vCL0YdUZJWKs9IE74VhrMEQB6\/IEdQvej97VLlCsY6vLIxIT0Rg\/CIJj361YHyFucr\/BnTGX+5Jjalr3nDiuLakzAwXQWupTz6Spzb2zJlh+14ZAtfEavSUcYnK46vyWVB0KaGDHBVo6Fizr7WEM27JPFrUbHnDQeZmKhEJabjlTIq\/tGmaFRzRz+1TknUlV\/JITGcK9e8+HS6vL+F6ZNWGCbBSFvRboQq6KSPXvabdrQl\/bGYgkxbXy6O01aIs5BejVrDGJPZ+2DiaL5JXnaSG0a9MW1JEa\/bVqBTenUvLXEpC26o6BS6vxzO0Q8Iu2FSLcuM+XGFw\/ikak8nmzpsVjEoGVtm3EMVwhktt50BLa4Pz5W+TGyjfHf16j6AG9TGXucxKeffbOe62uIXbWEWeO2rp9rbmRDhX38iaucedY7W1m\/GPJXm6XLbvXDcJyl67auUMt2zhpNvtABMYNxYlDMYxtmuJi5nBIbS40YZt4XsHb+AO9qe+b+PiYiNdokonutObDvVX60vkRu8uq7FOUQBSO1WDJfk6BX7YavO856yNISwJGPTE+ve3Ok51PTEd9alrDd+cNmeuk8t2I\/OdLSavtZKL7GcQM3XWS45rQJ198CwXyuGhBbfj\/V5Gcst28hmj6lJoyDGqiwTecVbLnGsOddLJ\/vnpp8H7tQPcwvvm\/eU3N3yfuf3MpcL+8ILv1MxoD\/LH9331LCsr287+6JrPfrHDd7HWUc6btw8994v5dLiMj2oRU5nwqqa1tq9\/18BHrNfc1wvWsLycseOVkMgXq27Vfkb0v73uumP2nEe9kk47tP0DHu6qC5\/i0X5\/2\/xvuK9DPAHcs957rXBzJQy6vLWrKqlLqPujuwRkPgn0rSRyvwtsuPeDPgj8jmh5vWrypP4in5lLOJArPwtSOE0RP5SaPrY4Pw7MOqhZP\/xZwInBOFuJwP47PU3DwKTIvIVLP\/uDwdvoOhOsL41rtazLoiW8EeeCExJ0tzsbPD1ir\/ob\/kLoQ5oZhJ8aFBhL07a5sKoBvLor\/JcWVDwd7Kx1yb41HEO7QsNR+0IlbCgu3EJya8DwGkLnYzrOo0ANVJJi40O4qz8Io8P2Mzsz8ysakyy7eEEyPJ\/SYSgzHJlCvBdKdER0a0NxG79xUr61usQTIzMtxKU8\/MRSRBVThMNDDA9V5MByuzEYtERUnMRM5DVXVBFWhEBb7KFYlD5ZREVc5C5dnBBgNMQ7BDpS9MVSJEbLM0aN6cQrFMZjhMVkVEZaRMRmvBprhEVstCVkpEZHXEatikZnlERo5Ma188ZUrK5vHCFtXLBxzMZnzMNzZL9pVCJGZMeDcscEg8ft2cf7\/utHdLTHe8xHfvzH76LHi5LHbaS4SUvHgszFg2TGhnyRcBy+gBSbdezBi4TIeVzId0xIJPvIiKRI2ckbXtSXjmTIcrzGkiy5kQTIkAydRWM65EMvd1LJXZRIcZTJ87DIs8PISSyNh7w7PEu9nJSen6y4njQPpZS4oMS8oRxIdaRJpDTJnewqpiQZIoTJYnTJSAESiEM\/qZI3qwwnrEwhliQWqPw\/i3NKTdTKGQEcyvEblOQWNntLs9SWvCwt12FL9+JKtWzFuIy2tqFL8SPKRMs7vUSgqLITvyRMEgtMuwS2yLxFw5xLxJxK1As9xkxK3nvMxbLMa5tMzxwzg5sX\/sxUzSihTGu5ycWTPCoyzWARmjhkEsj8SigTzEbUy7\/MkcxcTdMDyFtDzT5cmd2czaYswq4MGNEsyZixwuT0naqkzdXckrpMTLupN+kclfVCy6t8TjEaudYEz97rFeCELM1sRflhTu4srvbMytx8RORcrdn0TS2xTrJql1wMrSshT\/eMzmEEM1u8Ty8rTeks0MJMz+Dcz+G0FwajTwDFDr6MjwGtqgSVTPb8T9w0z1hBz+tUT\/70sg51rKKUULAsO\/5pTPlMSwrVPQQdTQHdP1czkzwSTkPER4Js0Qg9UT\/ZvBJJqBhVtANNTgy9zIWLvSS10RptUBzN0U4Lvh5F\/tEVbEAh3FEL1cjTtM0AhE8ERDssBdPfM9KXFMH8SkImNSsRjZw0FSBk2tCVhK4uPdP5DNPlJNGKdMw61dMrE1JyxMn8Ip0QddBH4iPIM0rjlFJ7UjK74dEpvdMjjbE9lVSw+z0PxTYSxc7NlD45TdQ5ZcK\/49Q+GdMJ\/c6n7NN4NKwmHUuh7FSui9Mtbbk3tY1RPS+bm9Q99bm9LMAk5b0bXVVCLU62etRW3dFYnQ8svNUoOtWOy9Nk1dNcdU1m2z8Ty9T1fNDfalRitSSOOlboodVQKVW4ZFFRnS\/fC7Uo\/Tk1BVa\/IzltDcBBpM7PHFdOVEsXNch5lSNALVOf\/llSNnXSNoU9ZO3XTdtId31XMk1WY7XX+lTDSHVWXB1RWHXUvhwSX7VJJ\/FXMBS1ohMxg5WwiXPKh1XW8JmgAKVKkZ0xaG2WD9XPjL1YdeK4kRtY6ipYj+0yBZLYuqmWkh1P7vxWVKXY01LVl22oDes83pDVmOTUeFXAW1VYj2sak4UW3lLQYZ1YKGnZdB3UyinRH\/zTeavZz7PZmyW+bPW9On3aHgvWGNyxcI3NSuW3dvVHfE2aoO2poeVIQj3Cezsn1ctZseXYsT05CQvVlWXBhT1XZBU8lA1TlTUWlq1YvAVKzvkzeTwpwW2lfDykv1VcqQ1D6xS758NPuuWd\/vyMXJfN2zVNXEQFEH5dpIIt3BNFXJBN2LZsK87dVrONuLfN0swdXaslFMgVWtSd3GstuiqMwB9sV+VLWp1sJhUFVWdNW93NXb5rJ86aXXqVW39b0O612NStVeD9UpfTWswd3JPlsHYk3fd0WMbFUsctFuG9W+LtueZt3egxXzk00PI5W0V1WtvFXcq13hRlteyt0PV1qx753uLdnlb6wsvAqvz11FMkWyMbz\/8lTgPuT1t13y+DX3HMzpCxwyzc2MC9XxDtXYMdLF6anYat3Qx22+lp1g724IjVYBsM4QZzo49D3qMV3BTMPynEXpGdXvut4M\/VoQQW3zLKYRHW\/rzYpUoPk2DFHF\/RM106hVgYhmLOoFQaBrMP7qomdsHZ6mHmo14NBFyP9U6ZkSadXVbW4WAvLjAwjjQxBlnX7a1ArBwENk1yslJ95OPHimEc+1nIMeLu5GJ7muJl22JGlV4AvuFnW1w5TlkbHuSLs+O\/C1ss\/ivPUcGjmOJILsMX9jCmrdpDHrJCZuQl7kZN3S3heF29QeX6vWRAZmUBflxTLhBV3ssSTmNNlI0znimCdUA1rmXKC2QfjWNKLiw6rrhMjl7WLWbSOyVB40xHWuTzFWAMLuW13eVjJtVG3uFbxuRNlub6Zc9u1r5pibBzzmbRJUdSduZTJjtmlqV5\/n5Fa52emnS8jQumUAZnBkzmVQxoT9S7PBvoLiTmaa7FbfG8N3ydX3ZXURZWebZkcV7lAS7o1ZXLN9ZZaF6ROXrnjL7S0D0jj67eOWQahCZnoXOgaQJplU4XhBtp2i1ip1HflhbJ9rVn18Ln43tofTYkE249fs5Be2vO5cNocBVmnwTNNU7os21cSN7oDW5qLc4Vlt5eb2XNmC4nHMywB648MnbjFCbXpzo\/Xb7pL6bqpdbQeu5pMPpp5zRMr360yZTBjNzVq5bhjmJhwCrPrYbUSY7rZr5ovj5PEpJcdCaiwPzn08tlKnXrdYVnfntRUMxidaZogCXswm6puX6h\/lkOXl06ymtOz9Je6MCtamUO4tKV7KeuzckebLjF02X27FgC7Y82Z9GeF4x1vzIWRAxst02mqpouargWbG2+GV5O6cO+7RzK7ZhyZdsqXzRGVFFM6gyM1lNjvVRGab9F27ZGbJLGP9eoF+Y+b5iebidWvxG+042i4vRmY62e7UktYkft7Oe+Z+e2JaWKPPA11EV8bKW+zWidbyXm7bv87r4e7zOkU3RBb2Gz6wM63uTrQT20bmxR3gQXoLUk4EbL6eSWUZ7W7\/0e39Ue7d2ecPRwWey27rKxTW\/2Nw83nlT9qgUv7znsWS\/9XRGXRqGm169F0xGrLCI36kU58gYP\/ulJumb61myo1mkFj2rmmeESD6PoZuL1xt\/UK+O+zWMMJ2rVpt\/uBHHXjq7v3Ox4pu3BVuml0eo1N+TUUm8gd+x+tnPiPvIMD96K4nCDZhxHpmsf76DbiT\/elOSVRnA4D+0VN+5ZRGubxuxnFe8FBG4993MrtnIcwnIJN7bFfspG59ruHtEgHEOUvW8t2+PlGzLkznQ3529g1nJQd24cR2LsU+Cmte9J39+5VXJzeetEN+sf6vNGkfUWTSHqm\/Sy8N9cx2oY17kFFfCjxCoUn9kVjXKxSaQ5V9diHxj6E3Vcl3Fhk0mTzlgKO+K4a3XofnXpXmDG5nYO5XBT13Xv\/qbaiDZ0yrbqYdfSNBdVS3dnWH\/3QOdsRcd0MD119NUrHldUmT70Nw\/2OA\/qbQ94zZZqfY9v5NZieF89tfbnfXNhVk\/3l9l0Q44uRpf1S7W1bz\/xPx7SQN\/48Ubhc4\/CkJegkS\/naP\/XQ+3fbFaUnrd4CrZh8FbbAGa0zLb5L81xlUoch+f4qxRLoj3UTeL5MnfyOqM5lKf2ERf0tBzwCfT6VVf6a5c8pg\/35QbzPAd4LW3y\/OXhn1\/MFePSaWVbST14I3K09yMyEqf5ml93RDT5id\/UalZcJJXt2jbAFgwx0u3ivefZle\/1wJlwfpfFKQ\/p1yZ4fUV8Ip539I2+\/l93fMaHzr4n5MRUCWl1e\/C8+OxG8LSN9Lk3etGnaWdJejOv9x6\/\/CyncyQvUZ0f21iLU5VvsQs+fe29\/VLi4ioH\/aiFfX4kfZwG6LsIucI\/4Md3VW4++qz11YLL+\/xOfkT\/\/E935Sei\/k\/s\/NVHWOtffqFH9\/w7an9P\/XA+QHaidZeOdSdb5PEP3+HnXvNctem03LIHiH8ABg78Z\/AgwoMEFzJs6PAhxIgSJ1KsaPEixowaMSbsaNCix5AiR5IsafIkypQqV7JkCaAlzJgyZ9KsaZPky5oFb\/Ls6fMn0KBCBUIcavQozoVIl6Lc6PQpVI0qQSbdOVIp06EMTUbt\/ur1K9iwYqlWnZj1LNq0J3Oqbev2rUe2CK02lQv3Lt68eok+3Ot3q1+jYwcTLpqSrEiCXOmGVCyYJuDACp8ijSx5KeLLmjfP5ez589W4TkGTLm36quXTPlOrbq06s+jBMO3ihIxVs0S4DV3zhM37d0m2jtcCL+6WtvHkys8ynlxxuc7b0FEXrl546vOyNodvZh3bOvjw4sfnDp59OvSccpHHRe\/+J\/v38udjp0i\/t3Tq8e\/z11+etGW7RcddYuQZeCCChC1mX3\/JERhagxFyJSGFEuZX4XYXNpaggANy+KFhdTGI2YPEdVTifiI295eGurUYoW8YdtfehDLaKNCN\/jnquGOBJX4HIo9qxRjTRbMJd+GKK3l3IohNOvnkkgkNGeRvKVI5HXIPmnUll11yFqWUPsrEUYZQPlnflmhmJuZeYDpnJpxxirdgml4CZ6WdxWXJWJIf4ZknoIEG5SZ8RQIlZ5NqRlRWnWyO2ReTtjnK5aI3TikoZjQGhyl6e0I6F6Gcijooj6E+auioTF1a6YZ\/KpnUZJL2aeNolp6XKnOmfoSrg7z6KtiL\/pUabEsZ\/YrWpYw61KORs\/IlK56ISjutWHT+dyywYZqIbWuucvutebYNO6l5yapKLYKKhtjTiN0Re6eBOZoLrpD0nuatvak66ye+TPYrn678zpuv\/lAD30TuXaGiuzDDxpZbJ8H48dtUxKD9WzG9unaoo6kGo3lww+Op++mgJOP2bl4i\/+oxxpsSpdC2LV92scwwoqykVFd2fGaZIYM38rLK7ltVsRtqC627YPU4dJ4s17za0zNH7SW+NK98M5RTtwpxbFsH3bVLmp6I9MM+m222taxqHfbYNa6d8ttUVs1uwDYjfDPdTGOc7KTkItysh1ZXthHOf1N9a9xHCZ54b4zvqPdhubUrL95tVV722bJFPvmPYX2mcOahN5z2uo4X7bbp9aZuZ+Vismk4fXUjeznBfCv42EyyW1yrmpRzvrrYMKMOfFaLE88be1ouBitq40Je\/jDip4o+FtAbtwoyzd4arzu8hP\/oO9fHSzl+zOJXZr6FdvkY7VfOG68iZT1P7\/nm4T+O8vz5I0q6yejv2rbL\/Kc4AfrqeaJxH368EiYD5stp\/QGd\/iLIM6H1z3+0Ydr7CBhADXJwPrKrVgffdC250S5I1quQA9+mlLmF8FAtfCGW8Mc7f2Uwaik8Totg57Wr6bBT0YNh+YAIGSGmJz9fWxsES7eWHjruhshqXqxyV0Iikuh3VEzMFXWSReN4KnhP4x6ZFljDL\/5QjCcUmBILt58pmtEzYaye2khoxS2Sj46zsSO8nGM0JLLRP\/ajIfYk2BU4EkuG1uPe7PwmyEVy\/oh\/R8QjACE5FUlSUi+IbFa7+khDRs7QkWcEVYoqqEeXaI9sMxMl\/OgHvhFWEketpNgrAWTER9pQk3mLo\/Q46b1UptGM60HlKF\/lxf\/lMmlMBOWUcEkhJ4ZwjEJ0Ziy1MknFQRN5tqQmA+01MCsq05O97B3mdCnO21GQlpWs5gvRGU0XBtGPOTQnhi65zs59c5XeHCc+o3LPY6ZznrXx52qq+cfvIROYtrpbGZc40FrO8U6mdGc+I6rPcBrUjupsJkChRrS0OIuf6VNkRYkU0pbZTpQN3ecnwVlOibLUYSuVJ0YzOkyZBrJYLoXoLu1ZtkRmE1yrAmlqEKm37Rmy\/qVGzenSWHlOmkaSqdJrp0JJqcD7AVVIHsXWT0MJz4m5sahH\/aq5mNnBi47VqVo8jEKJKkUE7jRXVz1WSblTT65+yatgvWs3fTlXi5pVeH0FVkdvmkCYLmdnb61fT32a0E2adK94Iexf6TnSLJKVg5Vd2edSei7JJu+ysvzbZKUKWbgulkW\/JFBiRYhSvIJ1tfP0rABhiyvtyVZgdeTlQv0Exd3qFLdgzC1DgQu3SM1UpZENpFIpWVvzLVdULEyYY5Y7q32ltohMVBnx4jpFzdKpoBlMImvDC968QrK5xzMvpkYrGWgqjarV5Uv7YlvaZ3G2T4dtauBWK96Wunad\/ugF3n8D9d5DCRa\/vC3QWt170eRqsKTlWhDgiivS+x5XhOTFY4BTl+GmPfgt250mo7il3tfOt29DO+xw2HvNCnvXsVvccBPTSWGtFHLFL0Mjd01oY39qV5UgCyhQ97vf\/kYTxowzcpewxtOeBjXHNg3tfUbs3xIPmK6Feu94hcxaIscSyXHzss5AjE1UNQZst4XWVpep5TU\/R6yFQ7NAd8xiNzc4smCWI\/uW\/KhgHo15b9SZnKd8UiBbzYhXrjKL4cvg8trZbncu80xlmyRETzjNTQt0kedr4TMu+qmuLCZF2XxULr\/y0VMz9cE6c+bAJA\/S58PiqtV4YlR3613H\/pwxKCMMZGY9mcDxCWuTFdPp9dpV1F8ldStpXTNlD5bS0kRrpqCtLL8S8sK0qnF07bsTwLhO2+opIWSzjSKsIFTcvG4rY\/dqa1zjkN121vSLG\/2e20iZnbBkNfyIiR1M6thRW\/HOv1cocGEPvCDgJfRLAh5k0Xpq1uujMvus5O5DR9zYd0X2Uv\/K7NyBKtZtEjNHA+QhbLKVOmn99q+9reu88breANcQt72d2+uEzdYPTXQurU3Hje\/NspYeXKtBvsGS8byK0z3kbgge7Mv9XK\/qgvCVFW1wlZszrmU6XRtVDWqcS3HQO5e3e+BtOQiZ1uPU1rrZOy5rZ1dpx01H\/iyfkF63t\/Py6S2GM5Q9\/CLCZtni\/A21k+Otcf5sG0BkP\/sBw9U4tj05fv0++ogfKXm5Mz3wmz7X0lHLabFLne6fZfu7vS74vhb9jsgTetol3PmFBt3AxP1WwJaldEN2\/lmehzN9hQbhps9e6bUHfN+HHe2t49TvEcW4csH+QEwTenn7HBPWoQr8iTtIkzFPOcq3rX1zX6\/7Zg6xpNBoZWFtcvzFJxTWJl7Krjvc+KOePvWzq\/wYgv7VrifqdS0JFTxrdeHlL7\/CTV3vKRoBBiD+tV\/DVVwCFuA7DZrhdBvP1VvoCRdlzd\/yMVvrpd6kqU\/\/kRnQTVjJnRv4ZV2H\/n3fAolf7rEcAcpaVK2guG1fUlkbzdVVkLkfSyGfJJVe7QCMDroerP1g81BaB77PgNXfawQL71Gd5eFYxP3e5d1dCb5ZOKXgCVYdxFFPV9WgDR4f\/Bmh\/A3eBcYf9kBddDCP9Onb8JggKYUg+83Y5GVe3MHhGN3e7TXesFGYGCIX1+FdHT6TBRaWcPjgcN3b2p2h6uUMRUHU460R5WmeHDodFNZdJJ7c8\/ShO0GiXlUUHhahIx6gAm4hF74U84lPD2pTg+XZP\/VZ6umWyaWir9EZ\/VGXEj7iJDohE9reEorgK\/peEmbPFSZWLlpOsYHiOOEgo4FhIsEX2hWMadBh\/mNxnZtcHwreGidyn1ShIObBYPf9lgNaBZiI3glSW5zlIU3BYmz9of2h4XdRoDBCnhfSmAl+ookFIw\/6W8Et4MsNIN\/d4\/cYoN6N2wAynM6d3ywRoW3dUikSkDlaEDoCWOIJ4qdlInP4i6shWIJxzLpl3wLSlzS64PatSD5qY0d2JLq1IybdYXOwY6WhofzoFzHmjzFiWEPiDhAiXuxU5DIa2K+NXHf9XyuKFBs6HQTqYq5dj+ypnPdRZK+9oZwxJUDO3O9sDIot41VJoMZxHhUlpE+NHU7aZE5GpCpKjbR5DZI8YDAioVep0SIiVxwWpFt2IjlK4hPKJSXKoyb2\/qEl6tke5pyLVSAyZqFN3WTxoJYwhaVXkqUHYuTrNGJbwmVjVuIJgdBc3iLcSRfEjWEWviNTLST6aCXsWZVSJRzKsSRpfqVpRcbOdIZcLQ65uaJpCk7eoVDrMGYTJmUMJmBVvl3vCaCv1R4EqqSjeWZnYiURCSdWgeYKWiRhIqZmFmU4dmVpDp1XShrqvZ6I0c5QbiPMpR8HDiMCYh9IcmfLkdtHdlY30qPU2aFE3txerl1fXpFxwlVhchxVbodrEp0athhwLabEFZhhtuH+KViI+SOB8mMbpmd9JSaO+SRiMWBAkqAoziNzZud8piHDueRLTg8OemN8xpMFeuON\/i0eyf3nlyFm5NRlXJYG+iHlSJKnMy0Jen5SsGHjRpHkCEaoLPZnbTKedKpnF2YoTP4odKpPTJFeuqFn8NilVfJlXqbjEI2M\/Cxp9fEn7RklbeabL02oeWoJWoomBNmibw7VZW4UmZ5kkzLobQIpIyFftBSpWdHWOt7hyfxJiq5fTfZoQSGclPrQJtIiQqLpgloYQeVp250nFtJgc8pUjKQoSX3omXXWQyZVhKYMbd3pIBqitaAozgRlLTrj3AkIa4RqA6ZkWe5m1SCpiR7pz\/WpHRLnoLanQPYlo27lXzLh5lmkBubnU76nWi7N4SnejTrZcxkNr25aJ12bhPaa\/m0SX6DqZ\/9E5nYqHOA45XcWK7Gp2KySGDjmJynOJKpaKis+6iqGKNA51rAOE4qYIbBCp4twKqF2WIuW242qVgySH4QqpWFNY5Vx5pgBVqJm1KJyYHE66q+Ga+59132unlXCVLgdCZfOKzJl1rdaV2AtXIH6n73WIum8KsfuUEgSoau2o4KyIKy2ai9lybiuTocWkKo2YKSeijIe5uyc6A5pLE1iqtHxq2usqEa2INh8LCWmaUIJq3iyp5buaaH+K0Dp7HnNJI156Xokqcel3C4OSRdB5O+lmMTRLKzZUpEorTXpkKmGn5V+48SmqoiA6RRGIY6WHiJW2soCWMjC\/lDczpYPTlpOomx9nhW4ikuG8JnaWSrePsx3WOibVCbVAkrsXWmnMu5kOmu\/KBO1nqqfwq0M1tNAptqBlmysxiYQ1a2+4Cr02afodizCtQmo\/tJgVqcnvSyyuiPsTC4m1qXQOpCnvuVj\/ktW5ejczqMncm7nnqmbOtUFJWzhsuvopuzJjGW2EOIpna1y8KzaXmPZDtz0Ep319uK0Ei14dprv8mcZShnSlmMZSQf0ftGHCmDURlLxQqTeVtuXsGt\/Ol\/Blub8ruuBraGAZuxPQqxH9izZbi68Fq2NhiOMXqFkEe6moqvRAm\/bIq9pMhfBnl2cBi\/aZautBu+FnWvL\/s4VByco2HJRU6blTu3jg74rCqvWwQEtoB4td+5n\/jGvjzqwb6WUtrUQ6I5KnKpvBjovIHnXByqlyFqr4Xaws2VucBoXllIjAN+rvgJwdhbw5tAo9gofk\/rijsItDSOu8JZVreKISEIwWEan\/ZJqV65vQJWufVWt7tqpFuspBs8p7PKm9gKolzLLUWLf9T7nJbIt2nLx+TopnirxFhPkw21rjH2xNspsfdxsNo7sGOdv2o3mIIvxBpJoWELyQSGa7NpsFefu7G4sW3andwben6Ux\/p5kIaMo3cWxfH6xyW6eFT\/fjMgwiZqxunJrBHdctY5vLDJi5eKeJ5sp5Y7w\/qfqDrBRqWd1cQuvshEfsvFKMCxHn\/sWUpb6LBvPkS93Ff1ep4Rqbx6vXCNP4diOrR+nbTj3IlTCqW40sDND7jYf2QR3Xd+S5goJYp1W6ju7VcUyEAsPsDX6b1u9IJ2W54VypIvWsPSm7bJa7i5j6T678CEDZ+LksHO5r9S+ZukSSTRfZDdH9JjBZrSG5646KA9nKgv6Y0lKKgDyo0o\/M+9K5jhj7QyDdCbipSvrcPq2scOKqGoW9MK+rU0\/LWQGNB8bcEI3NEGV2yLj64pFcVLrsoNdXQIpL\/8OtcKiqkV3iqOG8XjGcLqtmlxZFVa32xzfcSdfnhbuHveK8x+7\/jUxe+7nuHNEBywiy7MiU7JNqu5XIrLYStpWL63bOS7tNu4x424xx24uqjNK9iCWjSLpuSpkm+I0KzX1HrU9qwePNhvTljW9UhwoV2aUETaYWqGhtldgjg\/oxTOPzW0kd+Y8gyWkWufeHuZONlVzQk4I77P0hrOy8mX4pXPS8bDDiTLR+DYIJ6usUPN00jVvl69ra01gC8oFhc8NY7Qh3nVLenZI+2++\/i9RUjULE3QLNiwUG3RyhzC4sW6DcndWs3aJ5vUyy\/UUl8yg5nQhR+NIK6BJ4yO4ufR+J2d7C3QbvfQDZ2NNQw9+n1P5FnG3yrfktsfg3imRxlqFMzII\/lKxwbr3n5YpZjP0ZUuhVO82Fda3BvMsFscoe0O0Z3vMZDdQbNPlGGvzyVI0IcN3Xb94Dv7iVMX1LF\/1UC8qfk13YTkth1OWjpfXmHoYPxM5H3FTdJ+akR95ViY5hkV5PZJ4l2G5ZU05lT+TlVsUl4ddmAu2dn+ul3853Zb5i405n2p5qbn5OVa2mlf5gsuYjYehk0u3nDMkndc5mN85Dvc5IAq6kp853aY5oI8VmyM5oo+2oV\/5o+Owoi\/6KUa6z026BzW6oOV5P\/25pQ86pl+6p8cOp2eapnuxkYZ6m4+6QhJ69J76lqd6l4M6q2c6nH8urE9prjM4rdeZrd\/6\/qu7unz9+pvv+antetMGu7BbkKwHeqlvOrHDp7J\/4apLTLPLDI7bebRnObIH149nZaUvUbZr+7PrurH\/Mod3tkPaOlKVewOd+5qnO8V+OxnRO2y7u1DDuzbJO553+7z5+47juzRfu4dvNL8r1rQPJ8Hzur0vW7W3u8HnMsInvDf3+r+HexK7N7ur7Lhb\/JEJfDNFfNI+vLk3\/LJPPMgXO8aLOsCT+cIXJ8nzEB1+\/MqrkMgzOsrrSc6L+c5jVR+ZvNzcPK4LPa90fNi2\/KG\/\/MnHrs0TfbLHPCnO\/M72\/M5RPdAz3dND\/b0rvc4zvbpzPNbPVtBvPdc3vdGT\/c+X\/vy6j72+8GraPw5Knz3ES\/15uX0zWn2rgz2MP6nKv2wg0727tifSV73dzzvf9zuUxT3HfPSGCz7s6T3La3yDbPusJ37GwP2Uh6frQj6nWD60U74doxroJxveX7TfvymGer3n34vkO\/vaH+nzsv7Vx77pML68rD7ut\/4by\/Ht4z19++vuZ77tQ3q84GyROb4k877ivn7ENhHwM\/Mutn3xm\/qB+HA5Mr\/KOv\/hQn\/1Z\/C10v7eiz6lmKX5u8rwy0j6a\/8\/iv8Ph\/z3r97sr\/\/Fkz+g6fZsDlWlYz77G7+SpgtA\/BM4kGBBgwcRJlS4kGFDhw8hNgQwkWJFixExIrRI\/jFjx44XPYYUOZJkSZMnURLcuHJiSpcvYQqsCBGkw5k2Y+bUuZNnRgAPWbLsOZRoUaNHkSY9WlNhUKdPoT5VOpWqwagtiwqtqvHmVq9fwWK8+jNsWZocgXaViFaiWbdvSZJlyDYhXbh38ebVu1el2rpjAQf2y5fw3KtGtZplWphxY5+HHZcd3HTyX6xtI2f+KpfyWc2fQYcWLbOyVcGnIY9mPBbxyreLVcfWy1o20tIHYVO+PLd275ec\/3r2PZx48Zy5caNW7tT4XdpEE0u+3Zx6z+fVYU4viJzr7oXAsYfHvVa4yI3i0afPy9209pPs1WdNPTR6WPjx8X+cn9+8\/t3v7gcC8B\/w+KOOwPZsOjCt5DhTsMAHIQzpvr4EjMu\/CHm6zjrX3JoQww9JiwrEx7z770LLHNxuRONSDHAyD7n6L8AVaayRwRJ1O\/E3HW00SUPDlgtSxB157BHCH41sr0UKcUQRqCRlW9JFqMxbq0kosYwPxhCvdKnCLBMcMi0hyQwquy\/BrA5JMCvcUkAp01yPRDTrwizOO9Xbkks4R6ITTyWlOqvMQfUUtMs\/w1szyzYZPVQlRCPjM0MFHYXU0tEKHbDIS71StDtCQT1zU06J8xTKRiudEk5JSa2K1Uk5bFXW2DKdFS9Tiax1w1FtpXW\/OFHl881ebyXWWGJ1\/j3Wvl93qg+sZJUlDFcjgzX0yWgl6xBabLmFzs9ut5o2JWc3+xbc9Zhlk9c9rcXp3HCXZfDRd+m1zdxIQc1X33RRDNTb87Rdt969xLWx2jFXHXiqV2M69DKGFY5YrHsd29fiiwFG2F\/6YpVOYInhKrjGg8NMGGTEvGR4SYpPbvlGiDPDWOaLIxLZx46X\/djlnKlElGQrTd45w5Q\/slPoo\/vTOUfUkN6TOfky9jjVpssVE8\/BsK6sxGGpbhhowDy6cuquyWZXQoubnVntUA3deNdtj2O5bFh7\/lMtM81mEjiu50Zp5dOSjrrvwV\/WT+2G106czJr5RVzwZ+UmXNS6\/q9mi8rFYONb8j7DTHDzz+PWWXGlZ7W5JHI7jRz09xo\/FS2mntb0xXVhXn3ABcmbU17bB3dzdLi3+134wBi3+m3VUx51+OWZb16wr2OvHCvMteJOc95r3sxo7KmG0e3Ace7T+fH1NN3Cx6uulPz12W8eerztttwvodi7nnt34eUtZybv1xLA8HNFuk+1j3nFo9zxBEi3vxGQgQ2kGZAOCCy6UA9+TsJf\/y5IlZVBTlVyGRsGMeUe4E0sgcFz4PAM+L0HjRCEc1KhuryTsehZcHstrFO5gvMsq+zQhgYSYQkDd7MTCi+FMzwS8npYshcu6kJgA9q1knhDyAHQVR7c\/loUWfTDD\/oNiNKL4Aq1OEQxjvF5EFwilmbimn1BEYs8TNNN0NdGXymvi2GrowSNd8Q7ytFEX4Th6NjIR5kIkpCnC+MWxYdENLbOf3ssJKCM+EYiZlCQtXskIT1ExXHFMVrm8yEdyRhKUUYSkhW80+zySEP9PdKSNGrlJXm2KlIaDnV2HOXMimhKParvlr3s5ftqucitgWSW\/KMkH1+5SUVyMZWwxJfA3MdMX6KtbcXEz4SmmU0yAlOTwmzQ\/Kwpu6AVMpmG3JumOrRKZ36mUJNUpjbzlctgXvOQ8LTn+rjJSW920IRntB8ytTcedNpnnc2pVeJO5kmDLvOSCsUQ\/hzBySHr0Q6W5bSQaeZVUGxB64Etc2gVHak3jQrRj0yc3t3gh75\/ytGi52OhTro50sKwUEjdY2TIGPrSdX50l05TY0SHObWW9m2oaqJUUWUKNUSy8qavySlDmdpMk1oxMZkDaiArmb7dBfQ7SX3mUsnZ1ICB1YxeBV84qeWfrDUxqOPEJFebkrxvlsZhSDVr2kI6m3uyTWNodWpe87a0vQ52efnUaZ6giSqsArRTNYwLRjP6Mn3e1TlQ7Rdg+0jYIMkzpn99Kig1G1pAmtGvBkvsad2a1caq00fBcyNli3NY0pLVlqJVDmc5+csAGta2vSUUbzErnp9BcLEs5WCM\/gJIIAddFbZ8kW1mg8spRelWrnYNq1T3qbF2Oda4sbRsjrozJRU1l2DflSxtaelb4lVTlx3c5m5nq175lgm46AXj2Hwn1Iq+Ebm3I69eozvAAJ93vmcksCap+84FFpjBNY1vZ9OKX8Ues7taNaZcnSbF5Pj3v7cybymtK+AGt1ewJPbpECcXYnaut5Elza4St8ta1YbrYTH8VD8746LXmjCHHa7sgEHcmhG7+MCTHWWKPSxWEvI0NEwu0HD7WNw2qpgm\/T1QDB+m4UGON8X29fGSqdzPD4t5yPMEcUzNzLHPehmmTr5saYfj5vxAGbwUnjJcMXplyM5IoJHd8iZ7\/vzlNgOZzGxGFiMhrGZDi7m+ZXY0aA2cJDqrsqsNnWKg+yJeLhc6zWLhrqClGWa9EXrUj\/7StBKtQCT\/uNN4XfRXIx1hYU3401gUNd1wjMMcg9pxrwawqSd75mCLk9RlhS9OUQu4FM5Zya5Mdowrzcqq3fhfej7rc3kt0g6La9jHWzWyJXzbZdMTu64L97mlbGu4ws6AnCsytrMNvkQBO9UnTjW8Y5nkcyu7bcwut6SfjbB0R\/HWMgbPUaNGVmtvNd75JmmrEUhvSRWs2ysudm0tWe+l+ZvIAN83tONq6dX6mcOb\/jOfd6yRMbW24dU923IWJvHyNRs7+DanfUdo\/vNfx7pHk6Z2rQmevhcePOX2NvIH5dxyfoKZvkKWOdJpblRIP53ejYaUz2808CQWPNohF\/Zhi0QpGSs9kVDvqAJljludw7rRVJ+v1X0W8JJpvYdczw7Q0ztLu7fcewjdWdLnyEu3Sxzu8fu4wO2s7jhfnOxSkxKcjV5xjKedvRCfN+Nd6NJkrl3fPDft7+huw73bZikww\/xdM5msmkBe7Y5u\/enLC\/t+l33zY+4860eEwsQHnUW6ubB2IZblxsvb2MR3r68j7\/rKa7zm9Ry88qFrYuyNPmLUL1qfve7avNW1JdYf\/gCfqHkRVz\/qnxT8801d+BZ6v17sz967tZby\/ivbOJffV3D4aY9w2e\/S88J1PvpHTP1AyP3ehQCJjZQ2aMNCpOiUBHcU0P5oD\/9e7jYkr+0Y7PWQTzSwCQDT78EqkHAMEFxCsEWQCqL8pPtUbuwgcNwyK\/9IUHWeDwND0PFuT4w4rv8kZwa5RQdVY\/5kZAUn8PEOKs1ybvBkMPdsLwjH6AZxj6j2i01cMAl9rO+6zfOAJwaX7wOl7vw4cMgEEIN4sJOm6KSksL6AMCnyi6++5lwArwf\/rwvfzgM5rwCfMH8yjeROLsN+A+\/O8NiUyMFYcKPKb6GmDg4L7Av7JwyVxQD3huiwb6B0bCkkpA\/Ty4XEjagGMYsK0RDl\/gsR70cRj2UEL+KbUhDl8JDHKER34G\/\/vEr1+A0EMzG2ylAVFYMVU+ffVgcUjUUXxWnjDm4GSZASM+\/mtFBo2jCEbJF7jjGh6jBkxIfShkYY76\/53O4IQWQDObHBPFEZm1GDAI8XpVG7ti0WS+UNs9G2tnH6utEbH3Fcao25DCccYWwccTE9sPEc4zD6LA8E15HGTvHhELDGzkk\/TFEeC4caqc4aP2QOZ+oV7ZEcF3ESRa4W89AdVdAHK9IgXY4eOw6xkpHV6rEcQ7L9IjH01s\/DBAUVGTDxUDD6NDIQm2sZm2wWkfEjvXEk6UW5ElDanAvDSATT7vABX3LjOBIH\/hFywfBRvdKRd8DRVppSkfZuJ4cS\/IqyCQmRC5Oyt5bSdpqydMaqQX6ummiRS\/qrLKcSUKYQIn3jHrNSK+WQJqcqk\/oRDSdo92zJ9xbwHw+QIYvy8hIyC\/lSWuBSAwdzDI2SDduxFMmJZzJyFfdN7B6wK8krMEHqL\/tK+sgNK9sytLYyF+dy2hpTKiEp3VryLKdxC59OIR\/KHDfznjqT\/NrkMykyMVPyJ83y\/UwTLasSM1uMFymz+DyyIxVGueyy7kBDbrBNJrPtN2OuGgGzMDsvOmkwMw9TBBuxOEXvGpcpGHNTN1GT8i5zH1FTOh2uN62ybCSzVdITKK+lGD2t\/jvBzC9T8zltshbrU8RQjDrPcwdrDDtPkp1y7QfhkzwnTy2tEyePsgbz0zx5s\/rm5fFkUynsQmmgc0Aj0BI3i2yU0+IyMNSWUD8bdDj3rOveyg3fJEQntEOHsp2oCWk2VDPYsjU16zU\/Zz2l6zjpRGxsFAjTEGMiruroU0U51DePDETFkw1VJkIltLbobkchkAqtqYxCxzL\/METRgznD84SY0EpBZuKUVNH+LONORDQ1Lc+ARCXj0knLUx9pKfKmdD6z1D01UUiJ8UMZ9EjJjw+z0z7Vp9CyT8tMkd26ZT97E3rKjtNK0AiDVE1V7S1lNJtodHMY1W5uEeV+Qkcq\/nBNHPEUK7Q3iAlLK+aQxI\/TkovwFhUJN\/FR7SlSc3Ig9fQ\/x7AxTY4+5E8x1ROo7hPcFowY32w4DbQ2YlRVXdNR6fTqaHMlFS9byNK7SIxMPU5HQZVAoTHvBGtgXjRmOrUF+XRL8XRQ3eRLSU9WsRVB+c9QVxPSXBC62u9XoyRbmZJd\/w5cF5JCX3VeP0ZO25VXXDHY8LXUgDROo1VXLVBY30sfma9L\/XMADfMxZ817JLJ0TtBdbzJVmM+vAvYhydX8kJJgV5VYJ9VAjnVWGcsfg1JAScNzSrbEUEdiTVRXPvbhAPbNJO9i\/S9jr3JjOVabWJUOw0Zeo1FkExNC\/pFVLwuyaKXrYMsVYJlm9rzVZucUZ3N2mna2d3y2WR5x4fwMawtSa4vIQoGzSi+RaQXRaWUxV1V2cS7lWklyIitz6NJFUx3JbJ1pCGEOFslWJIsVINXQ8IQzXusVDJ1SLCXoGZ+MYpzoFql0ajV259bo6uB1F0uTRGfMVbjLWUsOUCVwNC0lgeSWLjv3TcETbJH2Zgc2ah1Icb3VaP90cifWbZsJ1e7GMmTltwr3c3sNTkW3XxcvVU23SA1Wd\/lTXIl26\/Dsco23Ijd1VpP394KPZUO16fiDZptGbZ83b6Pw2qwXb6vTQf82EZ2xZ8EX8cTUdlGSPbUvep0X7UxV\/mnJtzmzt0D1Nu7utpO+lW2V9frwNx5DUw\/jbtfM90phMEMVDXdR92lvz0Nftm0JNSKHVnXvbOSKlmuXN4Ib2HzfN0IueEixF3oT6nFrEmp713fPFngh93wld2QVuFnf1oNb1dyWyu8khnobQ3qp8jRhEoDnd3qr1l4hbIGdzYVZxZ2slYVnknxli24zmE+3Fz13eEoDNOt+rwGjeERNmIpTdpH89zaDs2F1b11z2FNZM4TtdIRpWD2bGHFU8qjSGNMsB3MZ0HJ7blDuS6h82E1ZxznZN4ljTzPFWJQKuAD1y34Xhool2FWV15CH93gVGWjjmIOps0rV944T12NR\/pWP+7hgyTh9F\/JkhdeBk7WKylR1BfKNqeqNK7d7+U+Ab3ANnS6BYa2OgVWT\/VVLjXR0dzBkE3lPLUxV6oyXKU1rVviLAZhw0Re0PNeVq3eJ7eVTi9CIRRhj+1ZSz9hrs\/gx5nhXlxmZZ5iIdwRBqrgSQXKMoVmZxxbpppmaQzGMjllv\/zV3y3h1IZGRxVZmL1mc8dOWN+pRUguF0bmDp06p9Lh2o5lyq+xCf7eeafmgZRmDSxKOP7mf2VGghVDn8Fl+O+4jKbCLghWhbZCSjVOQIZourzlm2TluFTWPX1Ay2WyjOTqhM7l9r+acQzr5WGyVUbpFS7oDUXq2FpfV\/r6SWyu6e2R6pve2UGWwqOt0fd1ZO2C5TiWZSANaW+80qEMxlFXwgWdaCeu2mF94bW43dLdygjL1hc3Sy975iQ0TqEkYWU5OaHkyq1\/ubEZaq+XYZXBlTFMvSa24k1lZoVu6ff5YDEvOrRcTrpPGjuY6qWvaGNVyad+TkVuJpf+agQJbqEHasBnHorXZKQ3UIbNUi+PTYyfbeSp7UHGzsDHbi6P6mAnYo+mam+vorLVtTce5qXvFg067RFO7VWFawcDatWV3lsNutcVRYKdzqte6qr30snebfnsbgds5rMkQRbv61mR76Wgbhweae01SYZu7y7QTiMRThsP7oreb\/nTIwrwke7TZp7QhV6\/f+rs\/+\/gWmrXzjufIm4cjzbYpac1AmL3bG7jRc58rTL55ay+TG0dFJ2y5SbX3O8FzG60N+qUBPJr8mriFqaDj28CJkiybpL5beVH7r1sd99+ScaLRa70rnLQFnLHDF7Vv2EIxtUueu1FL12Kp+pQQDcPN2fgofMW7+Me7xvT6UXC4VB7rymQf+cbNe62xcKdBF8QD6yvtuWa3GzFTEZW5ca8PMC+9NsmreYvBdqlV9ql\/+8JDjL+\/7ceBHPRafHqXe8M5mdG+OTdpl6txFkNn3MlPeqkZb4+OvMPZvM0Vx71L2CeK\/BfZiprv3KalukBx\/oTENVvNTQTRuRznQFxKq22z71vSF7HTOF3S7lmNv7yu8Txz6TrIcvrRVHNX8ldcIzuMCV2I6RnCPeoz6yPHGy\/FQx3jUB17\/dXMlVq6y0mAdmO5RhXNZx2Ghfyj5VxwS52YHV3Qk5q+HTycAJ220sibJ7zWl53WR\/26jZW5OZyz9RUqz8PT6RvYWt0xHft6n5rJv71x0Zx4yb3cSRqD\/8ehfvXJ\/dxRzs64lX3eZcbQjVE2cbXG647GuTmZofy1sx2P\/z2l9WXn5J3gkfrrpDymL9tMKJ3X9lytNn7TMTAKI36S6z3KzMnia\/nKn\/bjYzjRj32tZPzD6Sixlbak\/oU9ut8cTROJ5VM5vz2LnC372SPd5ktdJydaoiEduq+dNyMe6Acd43Ha20ceWBIdtDFcoyIKZU99N9W9eGw42aee6iu+57fc6BkcPmEH4LcecXudVPKbXoVyzn3c6s2+4NFeHUF6q5O+vWx9XN9+08+82cH0sfUy1nk373Fp75ky6zM7pNd+yb9z2B0fUVMk0O1+kTm\/uPM14CUa5rkbxkvSAYm64QU\/7vHeC0\/VDNddvK0ItGP8lem9koleh++dtBhd9UtP4QEZF2nD5cN9pWWd8at++H0fjWQ68JeT90P8KAt\/9Sle\/8I+m9PzcHRcmA8+902f7Zm\/pyuf51O+\/pfHT4PD+ew3F\/WtdahL3\/tvP0Gh3\/LHP7hVnqDvHvmNv\/al397VfmJ2X9gA4p\/AgQQLGjyIMKHChQwbOkwIIGLEhxQrWrwIUaLGjRw7evwIMqTIkSQnUizJUGJDlQtZYjz5kuDGmDQrlgxZM6XGnDx70kTpM6jQoUSLyjSKNKnSpRcBHLzJkanUqVSrWm368apWmzu3aoUKNqzYsSC5jtTpFK1arFBzzvS6MizVt3DrAq2LN2\/RtHr7+kXKV+bYv4QLG66a9TDiroobO\/Z5NyPZshgDp3TL2DDJrVEfJ43sObRey6JLa35KWqfp1awdJ24tlC7s2aFBo5782mJq\/oiYXSrEDTy48OHEi9u+LZK2cod80+5+ujy61dQmTz6Xjj277s3aX8ruDv7q8YLGfR\/+jrC8+vXs26+Peza8dOdHV8q\/z\/M6\/v38DVYXeFN\/25m3n3sGFmdWci39VxOBhaGH3IESTkihgfApKCBrjDHIW4YetvRhiAKCJWKC+g2UWYkhjifYida5yBaMzKWYXoU23ogjcBfipCJ+MvYI3o9ADvkYhkTO6CByR3rIolFJ7miSSxxWRmOEOV6JZZYQ+sfdkg9ORB9zXmYo5Jhm4tXRmS9OGSFtWr7JpmRGMvXkglxS11uco1VpF59kdqlmXs2hKGag95VpaKJS6ano\/p2Moqhlo4ABOumWl3GZXp6ILlYnZ36OSKmk01n2KICiarfpqarml+qZlpIX6apBNfnTnA8xmGSrkHaK5qee8lpgqLIqpuuwfSH6qrHKLisnjG8y26Cw3rVF5Vv\/lbojlHBuy2172noErXjOhqvhbY6mSW664Sa7K7YD2hpTt1iaSFm1Af4DbIyQ+QqgvP7+S9y36KrrV7EEI2Zui7i6e3DDS7LbL8MC56YpwBLSS\/GC1N5ZJL\/4WgxyyBv\/Jq3DsRVqMrEJ71qjwSm\/LB\/EH0vcbHyxiXzxmjzWfFa+0+ZKc5urgtsjrTDfCp19Rz+4cr8kLw01kTL3RKKTOB+I\/jHRPA\/MMlELkxb0uZLaXKLRUf8W79kFN\/3x02q\/zaTHFe\/82dUW6lxvy+z6bJPbTkfL94dVq2g23JAZjqaV302NeH9a8\/yw3D+X3DisZG\/tYOBI29k24GGHhxuQhVeO6+aVfwX46VI\/rrfkwWqOJOWqK0z3rWXBHjvJn9M+sd2+\/9u764jjqfTsCBvPrPCWH8l48M2rPrrurEccL6O4W17q79rj7PzuZ3eGMvKLir+s938P+bzitX+
  ```
  
</details>

<a name="ListResponseExamples"></a>
<details>
  <summary>List Response</summary>
  
  ```json
  {
    "shipments": [
        {
            "id": 0,
            "shipment_id": 21201,
            "service": "UPS Standard",
            "created_at": "2021-09-01 13:58:53",
            "tracking_number": "1Z0596VE2093587321",
            "status": "Voided",
            "rates": {
                "dates": {
                    "Pickup": {
                        "Time": "6:30 PM Friday",
                        "Date": "10 September 2021"
                    },
                    "Arrival": {
                        "Time": "11:30 PM Monday",
                        "Date": "13 September 2021"
                    }
                },
                "disclaimers": {
                    "Code": "01",
                    "Description": "Taxes are included in the shipping cost and apply to the transportation charges but additional duties/taxes may apply and are not reflected in the total amount due."
                },
                "billing_weight": "1.0",
                "billing_weight_unit": "LBS",
                "accessorials": [
                    {
                        "Code": "375",
                        "CurrencyCode": "CAD",
                        "MonetaryValue": "2.98",
                        "Name": "Fuel Surcharge"
                    }
                ],
                "service_code": "11",
                "service_name": "UPS Standard",
                "zone_number": "200",
                "base_service_charge": {
                    "value": "8.00",
                    "currency": "CAD"
                },
                "fuel_surchage": "1.36",
                "pre_tax_subtotal": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "rated_shipment_warnings": "Your invoice may vary from the displayed reference rates",
                "discountType": null,
                "total_charges": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "tax_charges": {
                    "MonetaryValue": "1.22",
                    "Type": "HST"
                },
                "total_charges_with_taxes": {
                    "value": "10.58",
                    "currency": "CAD"
                },
                "user_rate_id": "2649804"
            },
            "order": {
                "sender_name": "Ben Balandan",
                "recepient_name": "Polynova Industries Inc"
            }
        },
        {
            "id": 1,
            "shipment_id": 21200,
            "service": "UPS Standard",
            "created_at": "2021-09-01 13:56:33",
            "tracking_number": "1Z0596VE2090867319",
            "status": "Voided",
            "rates": {
                "dates": {
                    "Pickup": {
                        "Time": "6:30 PM Friday",
                        "Date": "10 September 2021"
                    },
                    "Arrival": {
                        "Time": "11:30 PM Monday",
                        "Date": "13 September 2021"
                    }
                },
                "disclaimers": {
                    "Code": "01",
                    "Description": "Taxes are included in the shipping cost and apply to the transportation charges but additional duties/taxes may apply and are not reflected in the total amount due."
                },
                "billing_weight": "1.0",
                "billing_weight_unit": "LBS",
                "accessorials": [
                    {
                        "Code": "375",
                        "CurrencyCode": "CAD",
                        "MonetaryValue": "2.98",
                        "Name": "Fuel Surcharge"
                    }
                ],
                "service_code": "11",
                "service_name": "UPS Standard",
                "zone_number": "200",
                "base_service_charge": {
                    "value": "8.00",
                    "currency": "CAD"
                },
                "fuel_surchage": "1.36",
                "pre_tax_subtotal": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "rated_shipment_warnings": "Your invoice may vary from the displayed reference rates",
                "discountType": null,
                "total_charges": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "tax_charges": {
                    "MonetaryValue": "1.22",
                    "Type": "HST"
                },
                "total_charges_with_taxes": {
                    "value": "10.58",
                    "currency": "CAD"
                },
                "user_rate_id": "2649804"
            },
            "order": {
                "sender_name": "Ben Balandan",
                "recepient_name": "Polynova Industries Inc"
            }
        },
        {
            "id": 2,
            "shipment_id": 21197,
            "service": "UPS Standard",
            "created_at": "2021-09-01 13:43:48",
            "tracking_number": "1Z0596VE2094563309",
            "status": "Voided",
            "rates": {
                "dates": {
                    "Pickup": {
                        "Time": "6:30 PM Friday",
                        "Date": "10 September 2021"
                    },
                    "Arrival": {
                        "Time": "11:30 PM Monday",
                        "Date": "13 September 2021"
                    }
                },
                "disclaimers": {
                    "Code": "01",
                    "Description": "Taxes are included in the shipping cost and apply to the transportation charges but additional duties/taxes may apply and are not reflected in the total amount due."
                },
                "billing_weight": "1.0",
                "billing_weight_unit": "LBS",
                "accessorials": [
                    {
                        "Code": "375",
                        "CurrencyCode": "CAD",
                        "MonetaryValue": "2.98",
                        "Name": "Fuel Surcharge"
                    }
                ],
                "service_code": "11",
                "service_name": "UPS Standard",
                "zone_number": "200",
                "base_service_charge": {
                    "value": "8.00",
                    "currency": "CAD"
                },
                "fuel_surchage": "1.36",
                "pre_tax_subtotal": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "rated_shipment_warnings": "Your invoice may vary from the displayed reference rates",
                "discountType": null,
                "total_charges": {
                    "value": "9.36",
                    "currency": "CAD"
                },
                "tax_charges": {
                    "MonetaryValue": "1.22",
                    "Type": "HST"
                },
                "total_charges_with_taxes": {
                    "value": "10.58",
                    "currency": "CAD"
                },
                "user_rate_id": "2649804"
            },
            "order": {
                "sender_name": "Ben Balandan",
                "recepient_name": "Polynova Industries Inc"
            }
        }
    ]
}
  ```
  
</details>

<a name="TrackingResponseExamples"></a>
<details>
  <summary>Tracking response</summary>
  
  ```json
  ** Currently being refactored. Please check again later. **
  ```
  
</details>