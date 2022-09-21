---
weight: 102
title: Identity Card OCR

search: true
---

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

