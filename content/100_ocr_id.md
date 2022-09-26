---
weight: 100
title: Identity Card OCR

search: true
---

# Identity Card OCR

## German Identity Card OCR

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

## Netherlands Identity Card OCR

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

## Norway Identity Card OCR

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

## Sweden Identity Card OCR

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

## India Aadhaar OCR

Card Field Recognition

### Front OCR
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

#### HTTP request

`POST https://api.aisolution.credit/v1/in_ocr_front/general`

#### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

#### Response format

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

### Back OCR

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

#### HTTP request

`POST https://api.aisolution.credit/v1/in_ocr_back/general`

#### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

#### Response format

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

#### Status code

status | description
--------- | -------
`OK` | `charge`, success
`FAIL` | `free`, image recognition error, please check input image
`IMAGE_RECOGNIZE_ERROR` | `free`, image recognition error
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_FORMAT` | `free`, invalid image format, image format should be one of jpeg/jpg/png/bmp
`IMAGE_INVALID_SIZE` | `free`, invalid image size, should be less than 2M
`RETRY_LATER` | `free`, server error

## India Pan OCR

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

## Indonesia Identity Card OCR

license number + name recognition + id number

> Code example:

```curl
import speedin

api = speedin.client('YOUR_ACCESS_KEY', 'YOUR_SECRET_KEY')
data = {"img": "BASE64_ENCODE_VALUE"}
url = "https://api.aisolution.credit/v1/ocr_id"
response = api.request(url, data)
print(response)
```

> Response for recognition success

```json
{
  "status": "OK",
  "message": {
    "name": "HELLO NAME",
    "id": "3171024302821001",
    "pob": "GARESSI SUPPA",
    "dob": "01-01-1961",
    "gender": "LAKI-LAKI",
    "address": "BTN UNHALU BLOK C NO. 28",
    "rt": "006",
    "rw": "003",
    "village": "KAMBU",
    "district": "KAMBU",
    "religion": "ISLAM",
    "marital_status": "KAWIN",
    "work": "PEGAWAI NEGERI SIPIL (PNS)",
    "nationnality": "WNI",
    "city": "KOTA KENDARI",
    "province": "SULAWESI TENGGARA"
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

`POST https://api.aisolution.credit/v1/ocr_id`

### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

### Response format

fields | description
--------- | -------
`status` | status code
`message` |`id`: ID card number, `NIK`
 | `name`: name
 | `pob`：place of birth，`maybe empty`
 | `dob`：date of birth，`maybe empty`
 | `gender`：gender，`maybe empty`
 | `address`：address，`maybe empty`
 | `province`：province，`maybe empty`
 | `city`：city，`maybe empty`
 | `district`：district，`maybe empty`
 | `village`：village，`maybe empty`
 | `rt`：leadership，`maybe empty`
 | `rw`：neighborhood committees，`maybe empty`
 | `religion`：religion，`maybe empty`
 | `marital_status`：marital status，`maybe empty`
 | `work`：work，`maybe empty`
 | `nationnality`：nationnality，`maybe empty`

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

## Thailand Identity Card OCR

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

## Mexico Identity Card OCR

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
        "voterId": "MLNRYR80110728M300",
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

## Colombia Identity Card OCR

Card Field Recognition

### Front OCR
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

#### HTTP request

`POST https://api.aisolution.credit/v1/co_ocr_front/general`

#### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

#### Response format

fields | description
--------- | -------
`status` | status code
`message` | `CardNumber`: card number 
 | `Surname`: surname
 | `GivenNames`: given names

### Back OCR

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

#### HTTP request

`POST https://api.aisolution.credit/v1/co_ocr_back/general`

#### Request parameters

parameter | description
--------- | -------
`img` | `string`, base64 encoded image. It is recommended that the image be less than 200KB, so it will be returned within 2 seconds, otherwise the return time will be longer.

#### Response format

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

#### Status code

status | description
--------- | -------
`OK` | `charge`, success
`FAIL` | `free`, image recognition error, please check input image
`IMAGE_RECOGNIZE_ERROR` | `free`, image recognition error
`INVALID_REQUEST` | `free`, invalid request parameters
`IMAGE_INVALID_FORMAT` | `free`, invalid image format, image format should be one of jpeg/jpg/png/bmp
`IMAGE_INVALID_SIZE` | `free`, invalid image size, should be less than 2M
`RETRY_LATER` | `free`, server error

