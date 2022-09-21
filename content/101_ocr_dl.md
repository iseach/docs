---
weight: 101
title: Driver's License OCR

search: true
---

# Driver License OCR

## German Drivers Licence OCR

Card Field Recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/de_dl_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "CardId": "B905 KODO168",
        "Surname": "Smith",
        "GivenNames": "John",
        "DateOfBirth": "15.10.90",
        "PlaceOfBirth": "Berlin",
        "DateOfIssue": "25.04.17",
        "DateOfExpiry": "24.04.32",
        "Address": "Landratsamt",
        "Class": "AM/B/L"
    }
}
```

> Response for recognition fail

```json
{
    "status": "FAIL",
    "message": "check input image and retry"
}
```

> Response for invalid request parameters

```json
{
    "status": "INVALID_REQUEST",
    "message": "check request params"
}
```

> Response for invalid image format

```json
{
    "status": "IMAGE_INVALID_FORMAT",
    "message": "image format not support"
}
```

> Response for image size larger than 2M

```json
{
    "status": "IMAGE_INVALID_SIZE",
    "message": "image larger than 2M"
}
```

> Response for server error

```json
{
    "status": "RETRY_LATER",
    "message": "Service is not available right now, please try again later"
}
```

### HTTP request

`POST https://api.aisolution.credit/v1/de_dl_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `CardNumber`: card number
 | `Surname`: surname
 | `GivenNames`: given names
 | `DateOfBirth`: date of birth
 | `PlaceOfBirth`: place of birth
 | `DateOfExpiry`: date of expiry
 | `Nationality`: nationality 
 | `Address`: address 
 | `Class`: drivers licence class

### Status code

status | description
--------- | -------
`OK` | `charge`, success
`FAIL` | `free`, image recognition error, please check input image
`IMAGE_RECOGNIZE_ERROR` | `free`, image recognition error
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_FORMAT` | `free`, invalid image format, image format should be one of jpeg/jpg/png/bmp
`IMAGE_INVALID_SIZE` | `free`, invalid image size, should be less than 2M
`RETRY_LATER` | `free`, server error

## Thailand Drivers License OCR

license number + name recognition + id number

> Code example:

```curl
import speedin

api = speedin.client('YOUR_ACCESS_KEY', 'YOUR_SECRET_KEY')
data = {"img": "BASE64_ENCODE_VALUE"}
url = "https://api.aisolution.credit/v1/th_ocr/general"
response = api.request(url, data)
print(response)
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "cardTypeTh":"ใบอนุญาตขับรถ",
        "cardTypeEn":"Driving License",
        "licenseNumber":"61002614",
        "idNumber":"1102652247328",
        "nameTh":"นาย  อนิรุต ทองรักอยู่",
        "nameEn":"MR. ANIRUT THONGRAKYU",
        "birthTh":"27 พฤษภาคม 2538",
        "birthEn":"27 May 1995",
        "issueDate":"24 December 2018",
        "expiryDate":"24 December 2020"
    }
}
```

> Response for recognition fail

```json
{
    "status": "FAIL",
    "message": "check input image and retry"
}
```

> Response for recognition fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no number or name found"
}
```

> Response for invalid request parameters

```json
{
    "status": "INVALID_REQUEST",
    "message": "check request params"
}
```

> Response for invalid image format

```json
{
    "status": "IMAGE_INVALID_FORMAT",
    "message": "image format not support"
}
```

> Response for image size larger than 2M

```json
{
    "status": "IMAGE_INVALID_SIZE",
    "message": "image larger than 2M"
}
```

> Response for server error

```json
{
    "status": "RETRY_LATER",
    "message": "Service is not available right now, please try again later"
}
```

### HTTP request

`POST https://api.aisolution.credit/v1/th_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `cardTypeTh`: th card type
 | `cardTypeEn`: en card type
 | `licenseNumber`: license number
 | `idNumber`: id number
 | `nameTH`: th name
 | `nameEn`: en name
 | `birthTh`: birth day of th
 | `birthEn`: birth day of en
 | `issueDate`: issuse date
 | `expiryDate`: expiry date

### Status code

status | description
--------- | -------
`OK` | `charge`, success
`FAIL` | `free`, image recognition error, please check input image
`IMAGE_RECOGNIZE_ERROR` | `free`, image recognition error
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_FORMAT` | `free`, invalid image format, image format should be one of jpeg/jpg/png/bmp
`IMAGE_INVALID_SIZE` | `free`, invalid image size, should be less than 2M
`RETRY_LATER` | `free`, server error

