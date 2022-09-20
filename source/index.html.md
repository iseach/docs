---
title: API Reference

search: true
---

# German Identity Card OCR

Card Field Recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/de_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "CardNumber": "LO1X00T47",
        "Surname": "MUSTERMANN",
        "GivenNames": "ERIKA",
        "DateOfBirth": "01.08.2031",
        "PlaceOfBirth": "BERLIN",
        "DateOfExpiry": "01.08.2031",
        "Nationality": "DEUTSCH"
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

`POST https://api.aisolution.credit/v1/de_ocr/general`

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

# German Drivers Licence OCR

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

# Netherlands Identity Card OCR

Card Field Recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/nl_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "DocumentNo": "SPECI2021",
        "Surname": "De Bruijn",
        "GivenNames": "Willeke Liselotte",
        "Gender": "V/F",
        "DateOfBirth": "10 MAA/MAR 1965",
        "DateOfIssue": "02 AUG/AUG 2021",
        "DateOfExpiry": "02 AUG/AUG 2031",
        "Nationality": "Nederlandse"
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

`POST https://api.aisolution.credit/v1/nl_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `Surname`: surname 
 | `GivenNames`: given names
 | `Gender`: gender
 | `DateOfBirth`: date of birth
 | `DocumentNo`: document no
 | `DateOfIssue`: date of issue 
 | `DateOfExpiry`: date of expiry
 | `Nationality`: nationality 

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

# Norway Identity Card OCR

Card Field Recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/no_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "Surname": "STENBYEN",
        "GivenNames": "SAMUND SPECIMEN",
        "Sex": "M",
        "Nationality": "Norsk/Norwegian",
        "DateOfBirth": "23 APR/APR 56",
        "Height": "179CM",
        "DocumentNo": "GDC000001",
        "CanNo": "164745",
        "DateOfExpiry": "11 JUN/JUN 26"
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

`POST https://api.aisolution.credit/v1/no_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `Surname`: surname 
 | `GivenNames`: given names
 | `Sex`: gender
 | `Nationality`: nationality 
 | `DateOfBirth`: date of birth
 | `Height`: height
 | `DocumentNo`: document no
 | `CanNo`: can no
 | `DateOfExpiry`: date of expiry

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

# Sweden Identity Card OCR

Card Field Recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/se_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "Surname": "SPECIMEN",
        "GivenNames": "SVEA",
        "Sex": "K/F",
        "Nationality": "SVENSK/SWE",
        "DateOfBirth": "21 AUG/AUG 82",
        "PersonalId": "820821-2384",
        "Height": "170CM",
        "CardNo": "59000002",
        "DateOfIssue": "09 JUL/JUL 21",
        "DateOfExpiry": "09 JUL/JUL 26",
        "Authority": "POLISMYNDIGHETEN"
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

`POST https://api.aisolution.credit/v1/se_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `Surname`: surname 
 | `Surname`: surname
 | `GivenNames`: given names
 | `Sex`: gender
 | `Nationality`: nationality
 | `DateOfBirth`: date of birth
 | `PersonalId`: persional id
 | `Height`: height
 | `CardNo`: card number
 | `DateOfIssue`: date of issue
 | `DateOfExpiry`: date of expiry
 | `Authority`: issuing agency

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

# India Aadhaar OCR

Card Field Recognition

## Front OCR
> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/in_ocr_front/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "CardNumber":"775754348277",
        "DateOfBirth":"16/07/2000",
        "DownloadDate":"06/09/2020",
        "Gender":"FEMALE",
        "IssueDate":"04/09/2020",
        "MobileNumber":"",
        "Name":"Sinch Poonam Sagar",
        "VID":"9150912715607691"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/in_ocr_front/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `CardNumber`: card number
 | `DateOfBirth`: date of birth
 | `DownloadDate`: download date
 | `Gender`: gender
 | `IssueDate`: the issue date
 | `MobileNumber`: mobile number
 | `Name`: user name
 | `VID`: vid number

## Back OCR

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/in_ocr_back/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "City": "Sitapur",
        "Province": "Uttar Pradesh",
        "PostCode": "261131",
        "Address": "S/O: Jameel Khan, tikariya, Tikariya, Sitapur, Uttar Pradesh - 261131"
        "CardNumber":"387133213107",
        "VID":"9106098539989335"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/in_ocr_back/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `Address`: address
 | `VID`: vid number
 | `CardNumber`: card number
 | `City`: city name
 | `Province`: province name
 | `PostCode`: post code
 | `Address`: detail address info

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

# India Pan OCR

card number + name recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/in_ocr_pan/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "CardNumber":"FBVPM7951K",
        "DateOfBirth":"13/08/1998",
        "FatherName":"MAHABUB ALI MAHAMMAD",
        "Name":"IRSHAD MAHAMMAD"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/in_ocr_pan/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `CardNumber`: card number 
 | `DateOfBirth`: date of birth
 | `FatherName`: father name
 | `Name`: name


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

# Thailand Identity Card OCR

id number + name recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/th_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
        "cardTypeTh":"บัตรประจำตัวประชาชน",
        "cardTypeEn":"Thai National ID Card",
        "idNumber":"1842356782169",
        "serialNumber":"8407-03-22251350",
        "nameTh":"น.ส.  พรนภา ยิ่งเภตรา",
        "nameEn":"Miss. Ponnapa",
        "lastNameEn":"Yinthpetra",
        "birthTh":"29 ม.ค. 2540",
        "birthEn":"29 Jan. 1997",
        "issueDateEN":"12 Apr. 2017",
        "issueDateTH":"12 เม.ย. 2560",
        "expiryDateEN":"22 Jun. 2025",
        "expiryDateTH":"22 มิ.ย. 2568",
        "religion":"พุทธ",
        "address":"ที่อยู่ 125 หมู่ที่ 7 ต.ช้างขวา อ.กาญจนดิษฐ์"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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
 | `idNumber`: id number
 | `serialNumber`: serial number
 | `nameTh`: name
 | `nameEn`: name
 | `lastNameEn`: last name of En
 | `birthTh`: birth day of th
 | `birthEn`: birth day of en
 | `issueDateEN`: en issuse date
 | `issueDateTH`: th issue date
 | `expiryDateEN`: expiry date
 | `expiryDateTH`: expiry date
 | `religion`: religion
 | `address`: address

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


# Thailand Driver's License OCR

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


# Mexico Identity Card OCR

id number + name recognition

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/mx_ocr/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status": "OK",
    "message": {
        "gender": "M",
        "idNumber": "MONY801107MTSLRR07",
        "voterId": "MLNRYR80110728M300"
        "fullName": "MOLINA NORATO YURI YERANIA",
        "fatherLastName": "MOLINA",
        "motherLastName": "NORATO",
        "name": "YURI YERANIA",
        "birthday": "15/07/1987",
        "issueYear": "2011",
        "expiryYear": "2021",
        "registrationYearAndMonth": "200101",
        "municipalNumber": "041",
        "postalCode": "87040",
        "placeNumber": "0001",
        "stateNumber": "28",
        "state": "TAMPS",
        "district": "VICTORIA",
        "addressAll": "AND 8 1121 INF ALDAMA 87040 VICTORIA ,TAMPS.",
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/mx_ocr/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `idNumber`: id number
 | `fullName`: name
 | `fatherLastName`:father lastName
 | `motherLastName`: mother lastName
 | `name`: name
 | `birthday`: birthday
 | `gender`: gender 
 | `expiryYear`: expiry year
 | `issueYear` : issue year
 | `voterId`: voter id
 | `placeNumber`: place number
 | `stateNumber`: state number
 | `municipalNumber`: municipal number
 | `state`: state
 | `district`: district
 | `addressAll`: address
 | `postalCode`: postal code
 | `registrationYearAndMonth`: registration year and month

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

# Colombia Identity Card OCR

Card Field Recognition

## Front OCR
> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/co_ocr_front/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
	"CardNumber": "1.136.879.353",
	"Surname": "RUEDA PLATA",
	"GivenNames": "OSCAR FELIPE"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/co_ocr_front/general`

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

## Back OCR

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/co_ocr_back/general?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for recognition success

```json
{
    "status":"OK",
    "message":{
	"DateOfBirth": "17-ENE-1987",
	"Height": "1.72",
	"BloodType": "A+",
	"DateOfIssue": "16-FEB-2005",
	"PlaceOfIssue": "BOGOTA D.C.",
	"Gender": "M",
	"PlaceOfBirth": "BOGOTA D.C (CUNDINAMARCA)"
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

> Response for recognition id or name fail

```json
{
    "status": "IMAGE_RECOGNIZE_ERROR",
    "message": "no id or name found"
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

`POST https://api.aisolution.credit/v1/co_ocr_back/general`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `DateOfBirth`: date of birth
 | `Height`: height
 | `BloodType`: blood type
 | `DateOfIssue`: date of issue
 | `PlaceOfIssue`: place of issue
 | `Gender`: gender
 | `PlaceOfBirth`: place of birth

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


# Face Comparison

Analyze the possibility of two faces belong to the same person. Using our face matching technology, you will get our judgment about whether it is the same person as well as a similarity score.

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/facecompare?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img1=BASE64_ENCODE_VALUE' \
--data-urlencode 'img2=BASE64_ENCODE_VALUE'
```

> Response example for same person

```json
{
    "status": "OK",
    "message": {
        "similarity": 97.501,
        "result": "SAME PERSON"
    }
}
```

> Response example for not the same person

```json
{
    "status": "OK",
    "message": {
        "similarity": 27.501,
        "result": "NOT SAME PERSON"
    }
}
```

> Response example for not sure

```json
{
    "status": "OK",
    "message": {
        "similarity": 50.501,
        "result": "NOT SURE"
    }
}
```

> Response example for error request

```json
{
    "status": "INVALID_REQUEST",
    "message": "error message"
}
```

> Response example for uploaded image larger than 2M

```json
{
    "status": "IMAGE_INVALID_SIZE",
    "message": "image larger than 2M"
}
```

> Response example can not detect face

```json
{
    "status":"RETRY_LATER",
    "message":"IMAGEB_FACE_DETECT_FAILED"
}
```

### HTTP request

`POST https://api.aisolution.credit/v1/facecompare`

### Request parameters

parameter | description
--------- | -------
`img1` | `string`, first image in base64 encoded format
`img2` | `string`, second image in base64 encoded format

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `similarity`: similarity score, 0~100
 | `result`: *judgment*
 | `IMAGEB_FACE_DETECT_FAILED`: can not detect faces on the images

### Status code

status | description
--------- | -------
`OK` | `charge`, success, `message.similarity` contains the similarity score
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_SIZE` | `free`, image size larger than 2M
`RETRY_LATER` | `free`, see message for details

### Judgment description

result | description
--------- | -------
`SAME PERSON` | the two images are belong to the same person
`NOT SAME PERSON` | the two images are not belong to the same person
`NOT SURE` | not sure

# Hand-held ID Card Comparison

Analyze the possibility of the person holding the ID card and the photo of ID card belonging to the same person. Using our face matching technology, you will get our judgment about whether it is the same person as well as a similarity score.

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/idholding?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response example for same person

```json
{
    "status": "OK",
    "message": {
        "similarity": 97.501,
        "result": "SAME PERSON"
    }
}
```

> Response example for not the same person

```json
{
    "status": "OK",
    "message": {
        "similarity": 27.501,
        "result": "NOT SAME PERSON"
    }
}
```

> Response example for error request

```json
{
    "status": "INVALID_REQUEST",
    "message": "error message"
}
```

> Response example for uploaded image larger than 2M

```json
{
    "status": "IMAGE_INVALID_SIZE",
    "message": "image larger than 2M"
}
```

> Response example for wrong image, not ID holding image

```json
{
    "status": "INVALID_FACE_NUM",
    "message": "0 faces found"
}
```

### HTTP request

`POST https://api.aisolution.credit/v1/idholding`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `similarity`: similarity score, 0~100
 | `result`: *judgment*

### Status code

 status | description
--------- | -------
`OK` | `charge`, success, `message.similarity` contains the similarity score
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_SIZE` | `free`, image size larger than 2M
`INVALID_FACE_NUM` | `free`, not ID holding image
`RETRY_LATER` | `free`, server error


# Face Search

Search for the same face photos that have been added by face photos

## 1. add face image

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/addface?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for generate token success

```json
{
    "status":"OK",
    "message":{
        "group_id":"LxiKPLIMGFpXzXas",
        "person_id":"c5r7jedkujdbnasarhn0",
        "person_count":3,
    }
}
```

> Response for detecting face failed

```json
{
    "status":"FACE_DETECT_FAILED",
    "message":{
        "group_id":"LxiKPLIMGFpXzXas",
        "person_id":"c5r7jedkujdbnasarhn0",
        "person_count":0
    }
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

`POST http://api.aisolution.credit/v1/addface`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, use base64 to encode the face image

### Response format

fields | description
--------- | -------
`status` | status code, if `status` is `OK`, successfully add face image
`message` | some message of the addition result
 | `group_id`: this is the add user group, actually it's your access key
 | `person_id`: this is the unique personal id which you have added the personal face
 | `person_count`: the face count that you have added the same face

### Status code

status | description
--------- | -------
`OK` | `free`, successfully add face image, add face is free
`FACE_DETECT_FAILED` | `free`, detect face failed
`FAIL` | `free`, service inner error
`RETRY_LATER` | `free`, server error


## 2. search the same face


> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/searchface?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> Response for generate token success

```json
{
    "status":"OK",
    "message":[
        {
            "confidence":100,
            "person_id":"c5r7jedkujdbnasarhn0"
        }
    ]
}
```

> Response for detecting face failed

```json
{
    "status":"FACE_DETECT_FAILED",
    "message":[]
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

`POST http://api.aisolution.credit/v1/searchface`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, the base64 encode of the face image

### Response format

fields | description
--------- | -------
`status` | status code
`message` | some message of the face search result
 | `confidence`: this is the confidence level of the searched face and the recognized face id
 | `person_id`: this is the personal id  which you have added

### Status code

status | description
--------- | -------
`OK` | `charge`, success search the face image
`FAIL` | `free`, not pass living recognition
`RETRY_LATER` | `free`, server error
`FACE_DETECT_FAILED`| `free`, not found face in this image

## 3. delete face

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/delface?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'person_id=personId'
```

> Response for delete face success

```json
{
    "status":"OK",
    "message": null
}
```

> Response for input person id not exist

```json
{
    "status":"PERSON_ID_NOT_EXIST",
    "message":null
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

`POST http://api.aisolution.credit/v1/delface`

### Request parameters

parameter | description
--------- | -------
`person_id` | `string`, `person id

### Response format

fields | description
--------- | -------
`status` | status code
`message` | err description

### Status code

status | description
--------- | -------
`OK` | `free`, success delete face
`PERSON_ID_NOT_EXIST` | `free`, input person id not exist
`RETRY_LATER` | `free`, server error


# WhatsApp Detail Detection

Check the details of the WhatsApp of the input global number, whether it is whatsapp account, status update time, signature, whether it is a corporate account, whether there is an avatar.

> Code example:

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/gliswadetail?token=TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'callback=https://YOUR_CALLBACK_URL' \
--data-urlencode 'number=81387300008'
```

> Non-callback request (callback is empty), response for the input number have already registered whatsapp

```json
{
    "status": "OK",
    "message": {
        "number": "+6284921089722",
        "whatsapp": "yes",
        "status_update": "20180825",
        "signature": "Saya suka global",
        "business_user": "no",
        "avatar": "yes"
    }
}
```

> Non-callback request (callback is empty), response for the input number not register whatsapp

```json
{
    "status": "OK",
    "message": {
       "number": "+6284921089722",
       "whatsapp": "no"
  }
}
```

> Non-callback request (callback is empty), response for the input number is checking

```json
{
    "status": "OK",
    "message": {
        "number": "+6284921089722",
        "whatsapp": "checking"
  }
}
```

> Return by callback address (callback address) 

```shell
GET https://YOUR_CALLBACKURL/?number=%2B62813116594289&whatsapp=yes&status_update=20180825&signature=Saya+suka+global&business_user=no&avatar=yes
```

### HTTP request

`POST https://api.aisolution.credit/v1/gliswadetail`

### Request parameters

parameter | description
--------- | -------
`number` | `string`, phone number
`country` | `string`,Country abbreviation, Among them Philippines: PH, Vietnam: VN, India: IN
`callback` | `optional`, `string`, callback url
`servstatus` | `optional`, `string`, When the value is y, it will return unavailable once the service is unavailable

### Response format

fields | description
--------- | -------
`status` | status code
`message` | `number`: phone number
 | `whatsapp`: conclusion
 | `status_update`: status update
 | `signature`: signature
 | `business_user`: business user
 | `avatar`: avatar

### Callback method

When the field callback is not empty, it is returned to the callback URL once the result is queried. Please do not call back the same number multiple times. Return method is GET https://YOUR_CALLBACKURL/?number=%2B62813116594289&whatsapp=yes&status_update=20180825&signature=Saya+suka+global&business_user=no&avatar=yes

### Status code

status | description
--------- | -------
`OK` |  the whatsapp value is checking, unavailable for free else charge, `message` contains the result
`FAIL` | `free`, invalid query
`INVALID_INPUT` | `free`, invalid input
`RETRY_LATER` | `free`, server error, please try again later


