# Vital Logistics v1 API Documentation

Endpoints:

1. [Rating](#Rating)
2. [Shipment](#Shipment)
3. [List](#List)
4. [Tracking](#Tracking)
5. [Void](#Void)

<details>
  <summary>Show JSON request</summary>
  
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

## <a name="Rating"></a>Rating

| Authorization | Bearer Token |
| ------------- | ------------ |
| Endpoint | /api/v1/orders/ship |
| Request Example |  |
| Response Example |  |

## <a name="Shipment"></a>Shipment

## <a name="List"></a>List

## <a name="Tracking"></a>Tracking

## <a name="Void"></a>Void