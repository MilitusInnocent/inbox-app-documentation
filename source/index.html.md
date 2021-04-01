---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - nodejs

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Inbox App

Welcome to the Inbox App API!

This API documentation page was created with [Slate](https://github.com/slatedocs/slate). 

# Login

## POST login

```shell
curl "https://manifest-inbox-app.herokuapp.com/login" \
  -X DELETE \
  -H "Authorization: token"
```

```javascript
{
    "public_key": "rJqbI7JgyCklbimFVgRig4SEUmyHD3",
    "private_key": "U2FsdGVkX19B9J/DsCcq7aU5ko0s++QUlPLp/CDXxsPYck87D35OluI6DCTyPjHa",
    "module_id": "544"
}
```

> The above command returns JSON structured like this:

```json
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7Im1vZHVsZV9pZCI6IjU0NCIsInVybCI6Imh0dHBzOi8vbWFuaWZlc3QtaW5ib3gtcmVhY3QuaGVyb2t1YXBwLmNvbSIsInBlcm1pc3Npb24iOiJjcmVhdGUsIHJlYWQsIHVwZGF0ZSwgZGVsZXRlLCByZWFkYWxsLCBtb2RpZnlhbGwiLCJ1c2VyX2RldGFpbCI6eyJhY2NvdW50X2lkIjoiNjE3ZTM4YmUtNDlkMS00YTY2LWEwZjYtNzA0NzU2MzgzODEyIiwidXNlcl9uYW1lIjoic2FtdWVsIiwibmFtZSI6Ik1yc2FtIHNhbW1pZSIsImVtYWlsIjoibGF5emllMmVAZ21haWwuY29tIn0sIm1vZHVsZV9uYW1lIjoiSW5ib3gtcmVhY3QtYXBwIiwiY3VycmVudF9idXNpbmVzcyI6IlJlYWN0IERlbW8iLCJidXNpbmVzc2VzIjpbeyJpZCI6NjQsIm5hbWUiOiJQcmlkaWN0LWJ1c2luZXNzIn0seyJpZCI6NjgsIm5hbWUiOiJOZXctQnVzaW5lc3MgSW5jIn0seyJpZCI6MTkwLCJuYW1lIjoiUmVhY3QgRGVtbyJ9XSwicHJvZmlsZSI6Im1lbWJlciIsInJvbGVfZGV0YWlscyI6eyJyb2xlX2xldmVsIjo0LCJyb2xlX25hbWUiOiJNYW5hZ2VyIn0sImRlcGFydG1lbnRfbmFtZSI6ImZpbmFuY2UifSwiaWF0IjoxNjE3Mjc3MzQzLCJleHAiOjE2MTcyODA5NDN9.QmdqNKsxBI9sLAHumTr9FkrkcieIbGpCO4rpyMU1fbM",
    "tokenData": {
        "user": {
            "module_id": "544",
            "url": "https://manifest-inbox-react.herokuapp.com",
            "permission": "create, read, update, delete, readall, modifyall",
            "user_detail": {
                "account_id": "617e38be-49d1-4a66-a0f6-704756383812",
                "user_name": "samuel",
                "name": "Mrsam sammie",
                "email": "layzie2e@gmail.com"
            },
            "module_name": "Inbox-react-app",
            "current_business": "React Demo",
            "businesses": [
                {
                    "id": 64,
                    "name": "Pridict-business"
                },
                {
                    "id": 68,
                    "name": "New-Business Inc"
                },
                {
                    "id": 190,
                    "name": "React Demo"
                }
            ],
            "profile": "member",
            "role_details": {
                "role_level": 4,
                "role_name": "Manager"
            },
            "department_name": "finance"
        },
        "iat": 1617277343,
        "exp": 1617280943
    }
}
```

This is the login endpoint.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/login`

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://manifest-inbox-app.herokuapp.com/login" \
  -H "Authorization: token"
```

```javascript
const token = require('token');

let api = token.authorize('eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7Im1vZHVsZV9pZCI6IjU0NCIsInVybCI6Imh0dHBzOi8vbWFuaWZlc3QtaW5ib3gtcmVhY3QuaGVyb2t1YXBwLmNvbSIsInBlcm1pc3Npb24iOiJjcmVhdGUsIHJlYWQsIHVwZGF0ZSwgZGVsZXRlLCByZWFkYWxsLCBtb2RpZnlhbGwiLCJ1c2VyX2RldGFpbCI6eyJhY2NvdW50X2lkIjoiNjE3ZTM4YmUtNDlkMS00YTY2LWEwZjYtNzA0NzU2MzgzODEyIiwidXNlcl9uYW1lIjoic2FtdWVsIiwibmFtZSI6Ik1yc2FtIHNhbW1pZSIsImVtYWlsIjoibGF5emllMmVAZ21haWwuY29tIn0sIm1vZHVsZV9uYW1lIjoiSW5ib3gtcmVhY3QtYXBwIiwiY3VycmVudF9idXNpbmVzcyI6IlJlYWN0IERlbW8iLCJidXNpbmVzc2VzIjpbeyJpZCI6NjQsIm5hbWUiOiJQcmlkaWN0LWJ1c2luZXNzIn0seyJpZCI6NjgsIm5hbWUiOiJOZXctQnVzaW5lc3MgSW5jIn0seyJpZCI6MTkwLCJuYW1lIjoiUmVhY3QgRGVtbyJ9XSwicHJvZmlsZSI6Im1lbWJlciIsInJvbGVfZGV0YWlscyI6eyJyb2xlX2xldmVsIjo0LCJyb2xlX25hbWUiOiJNYW5hZ2VyIn0sImRlcGFydG1lbnRfbmFtZSI6ImZpbmFuY2UifSwiaWF0IjoxNjE3Mjc3MzQzLCJleHAiOjE2MTcyODA5NDN9.QmdqNKsxBI9sLAHumTr9FkrkcieIbGpCO4rpyMU1fbM');
```

<!-- > Make sure to replace `token` with your API key. -->

<!-- Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following: -->

`Authorization: token`

# Messages

## GET All Messages

```shell
curl "https://manifest-inbox-app.herokuapp.com/messages" \
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/messages
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": [
        {
            "id": 35,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 35,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:35:56.307Z",
            "updatedAt": "2021-03-15T19:35:56.307Z",
            "message": {
                "id": 35,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:56.295Z",
                "updatedAt": "2021-03-15T19:35:56.295Z"
            }
        },
        {
            "id": 30,
            "receiverId": "61588387-8fe6-4bc4-ba2e-4ee8a8cb5684",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 30,
            "receiver_userName": "Samuel Nwoko",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:28:23.537Z",
            "updatedAt": "2021-03-15T19:48:04.194Z",
            "message": {
                "id": 30,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:28:23.516Z",
                "updatedAt": "2021-03-15T19:28:23.516Z"
            }
        },
        {
            "id": 29,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 29,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:28:21.991Z",
            "updatedAt": "2021-03-15T19:48:04.219Z",
            "message": {
                "id": 29,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:28:21.960Z",
                "updatedAt": "2021-03-15T19:28:21.960Z"
            }
        },
        {
            "id": 36,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 36,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:35:58.455Z",
            "updatedAt": "2021-03-15T19:55:18.333Z",
            "message": {
                "id": 36,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:58.423Z",
                "updatedAt": "2021-03-15T19:35:58.423Z"
            }
        },
        {
            "id": 34,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 34,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:35:23.591Z",
            "updatedAt": "2021-03-15T19:55:18.344Z",
            "message": {
                "id": 34,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:23.559Z",
                "updatedAt": "2021-03-15T19:35:23.559Z"
            }
        },
        {
            "id": 43,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 43,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T20:13:03.432Z",
            "updatedAt": "2021-03-29T15:10:31.822Z",
            "message": {
                "id": 43,
                "subject": "Hello Test",
                "body": "<p><strong>Hello Test </strong></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T20:13:03.419Z",
                "updatedAt": "2021-03-15T20:13:03.419Z"
            }
        },
        {
            "id": 40,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "businessId": 190,
            "messageId": 40,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "chuks sahmie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:53:10.455Z",
            "updatedAt": "2021-03-29T16:08:57.996Z",
            "message": {
                "id": 40,
                "subject": "test post",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:53:10.446Z",
                "updatedAt": "2021-03-15T19:53:10.446Z"
            }
        },
        {
            "id": 37,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "businessId": 190,
            "messageId": 37,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "chuks sahmie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:36:14.972Z",
            "updatedAt": "2021-03-29T17:49:00.857Z",
            "message": {
                "id": 37,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:36:14.956Z",
                "updatedAt": "2021-03-15T19:36:14.956Z"
            }
        },
        {
            "id": 32,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 32,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:34:31.646Z",
            "updatedAt": "2021-03-29T17:49:19.966Z",
            "message": {
                "id": 32,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:34:31.613Z",
                "updatedAt": "2021-03-15T19:34:31.613Z"
            }
        },
        {
            "id": 38,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 38,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:48:59.528Z",
            "updatedAt": "2021-03-29T18:33:10.305Z",
            "message": {
                "id": 38,
                "subject": "test tags from react",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:48:59.516Z",
                "updatedAt": "2021-03-15T19:48:59.516Z"
            }
        },
        {
            "id": 39,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 39,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:49:36.254Z",
            "updatedAt": "2021-03-29T18:33:25.361Z",
            "message": {
                "id": 39,
                "subject": "okay this is from react",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:49:36.215Z",
                "updatedAt": "2021-03-15T19:49:36.215Z"
            }
        },
        {
            "id": 42,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 42,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T20:13:02.504Z",
            "updatedAt": "2021-03-29T18:33:36.000Z",
            "message": {
                "id": 42,
                "subject": "Hello Test",
                "body": "<p><strong>Hello Test </strong></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T20:13:02.494Z",
                "updatedAt": "2021-03-15T20:13:02.494Z"
            }
        },
        {
            "id": 45,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 45,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-31T19:47:21.772Z",
            "updatedAt": "2021-03-31T19:47:21.772Z",
            "message": {
                "id": 45,
                "subject": "this is another story entirely",
                "body": "<p>Nulla imperdiet ornare mauris vel varius. Morbi tincidunt ornare efficitur. Praesent dapibus eros et felis blandit molestie. Aliquam at fringilla nisi, eget scelerisque magna. Suspendisse tempus ipsum dui.</p><p>Vivamus at euismod dui. Ut nec enim varius, accumsan sapien a, interdum orci. Donec et ligula tempus, viverra massa sit amet, lacinia turpis.</p><p>Praesent viverra, est ac lobortis feugiat, augue nibh tincidunt mi, sed malesuada neque metus a est. Quisque malesuada nibh in sem consequat, ut facilisis est elementum. Fusce nec eleifend tortor.</p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-31T19:47:21.672Z",
                "updatedAt": "2021-03-31T19:47:21.672Z"
            }
        },
        {
            "id": 46,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 46,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-04-01T07:39:20.785Z",
            "updatedAt": "2021-04-01T07:46:06.315Z",
            "message": {
                "id": 46,
                "subject": "hello world1",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T07:39:20.646Z",
                "updatedAt": "2021-04-01T07:39:20.646Z"
            }
        },
        {
            "id": 31,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 31,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:29:33.524Z",
            "updatedAt": "2021-03-15T19:34:42.237Z",
            "message": {
                "id": 31,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:29:33.505Z",
                "updatedAt": "2021-03-15T19:29:33.505Z"
            }
        },
        {
            "id": 33,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 33,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:35:22.289Z",
            "updatedAt": "2021-03-15T19:35:22.289Z",
            "message": {
                "id": 33,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:22.241Z",
                "updatedAt": "2021-03-15T19:35:22.241Z"
            }
        }
    ]
}
```

This endpoint retrieves all messages.

### HTTP Request

`GET https://manifest-inbox-app.herokuapp.com/messages`

## POST Get One Message

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/get" \
  -H "Authorization: token"
```

```javascript
{
    "id": 30
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": {
        "id": 30,
        "receiverId": "61588387-8fe6-4bc4-ba2e-4ee8a8cb5684",
        "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
        "businessId": 190,
        "messageId": 30,
        "receiver_userName": "Samuel Nwoko",
        "sender_userName": "Mrsam sammie",
        "status": "unread",
        "type": "receiver",
        "deleted_by_sender": true,
        "deleted_by_receiver": false,
        "createdAt": "2021-03-15T19:28:23.537Z",
        "updatedAt": "2021-03-15T19:48:04.194Z",
        "message": {
            "id": 30,
            "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
            "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
            "businessId": 190,
            "starred": null,
            "is_forwarded": null,
            "createdAt": "2021-03-15T19:28:23.516Z",
            "updatedAt": "2021-03-15T19:28:23.516Z",
            "replies": [
                {
                    "id": 16,
                    "body": "What is Lorem Ipsum?\nLorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the",
                    "businessId": 190,
                    "messageId": 30,
                    "sender_userName": "Mrsam sammie",
                    "starred": null,
                    "is_forwarded": null,
                    "createdAt": "2021-03-15T19:41:52.216Z",
                    "updatedAt": "2021-03-15T19:41:52.216Z"
                }
            ]
        }
    }
}
```

This endpoint retrieves a specific message.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/get`

## POST Send Message
```shell
curl "https://manifest-inbox-app.herokuapp.com/message/create"
  -H "Authorization: token"
```

```javascript
{
    "subject": "hello world1",
    "body": "message body",
    "receiverId": "617e38be-49d1-4a66-a0f6-704756383812"
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "message sent successfully!",
    "data": {
        "id": 47,
        "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
        "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
        "businessId": 190,
        "messageId": 47,
        "receiver_userName": "Mrsam sammie",
        "sender_userName": "Mrsam sammie",
        "status": "unread",
        "type": "receiver",
        "deleted_by_sender": false,
        "deleted_by_receiver": false,
        "createdAt": "2021-04-01T14:13:23.835Z",
        "updatedAt": "2021-04-01T14:13:23.835Z",
        "message": {
            "id": 47,
            "subject": "hello world1",
            "body": "message body",
            "businessId": 190,
            "starred": null,
            "is_forwarded": null,
            "createdAt": "2021-04-01T14:13:23.684Z",
            "updatedAt": "2021-04-01T14:13:23.684Z"
        }
    }
}
```

This endpoint sends a message.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/create`


## POST Send Multiple Messages

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/createMultiple" \
  -X DELETE \
  -H "Authorization: token"
```

```javascript
{
    "subject": "hello world",
    "body": "message body",
    "receivers": ["617e38be-49d1-4a66-a0f6-704756383812", "7b544312-82d1-482d-982b-370f9d3e2fdf", "7b544312-82d1-482d-982b-370f9d3e2fdf"]
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "Operation complete!",
    "data": {
        "totalRecords": 3,
        "successful": 3,
        "failed": 0,
        "failedRows": []
    }
}
```

This endpoint sends multiple messages.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/createMultiple`


## POST Create Draft Message

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/draft/create" \
  -H "Authorization: token"
```

```javascript
{
    "body": "i want to leave this message to send later",
    "subject": "not sure i want to send this yet",
    "receiverId": ""
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "draft saved successfully!"
}
```

This endpoint saves a draft message.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/draft/create`

## POST Delete Message

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/delete" \
  -H "Authorization: token"
```

```javascript
{
    "id": 46
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "message deleted successfully!"
}
```

This endpoint deletes a message.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/delete`

## POST Delete Multiple Messages

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/deleteMultiple" \
  -H "Authorization: token"
```

```javascript
{
    "ids": [ 38, 39, 42]
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "Operation complete!",
    "data": {
        "totalRecords": 3,
        "successful": 3,
        "failed": 0,
        "failedRows": []
    }
}
```

This endpoint deletes multiple messages.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/deleteMultiple`

## Get All Inbox Messages

```shell
curl "https://manifest-inbox-app.herokuapp.com/messages/inbox" \
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/messages/inbox
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": [
        {
            "id": 54,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 54,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:14:40.161Z",
            "updatedAt": "2021-04-01T17:14:40.161Z",
            "message": {
                "id": 54,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:14:40.152Z",
                "updatedAt": "2021-04-01T17:14:40.152Z"
            }
        },
        {
            "id": 52,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 52,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:12:52.714Z",
            "updatedAt": "2021-04-01T17:12:52.714Z",
            "message": {
                "id": 52,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:12:52.696Z",
                "updatedAt": "2021-04-01T17:12:52.696Z"
            }
        },
        {
            "id": 51,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 51,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:12:51.683Z",
            "updatedAt": "2021-04-01T17:12:51.683Z",
            "message": {
                "id": 51,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:12:51.669Z",
                "updatedAt": "2021-04-01T17:12:51.669Z"
            }
        },
        {
            "id": 50,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 50,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:11:46.580Z",
            "updatedAt": "2021-04-01T17:11:46.580Z",
            "message": {
                "id": 50,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:11:46.557Z",
                "updatedAt": "2021-04-01T17:11:46.557Z"
            }
        },
        {
            "id": 49,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 49,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:11:44.920Z",
            "updatedAt": "2021-04-01T17:11:44.920Z",
            "message": {
                "id": 49,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:11:44.904Z",
                "updatedAt": "2021-04-01T17:11:44.904Z"
            }
        },
        {
            "id": 48,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 48,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:07:50.209Z",
            "updatedAt": "2021-04-01T17:07:50.209Z",
            "message": {
                "id": 48,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:07:50.189Z",
                "updatedAt": "2021-04-01T17:07:50.189Z"
            }
        },
        {
            "id": 47,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 47,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T14:13:23.835Z",
            "updatedAt": "2021-04-01T14:13:23.835Z",
            "message": {
                "id": 47,
                "subject": "hello world1",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T14:13:23.684Z",
                "updatedAt": "2021-04-01T14:13:23.684Z"
            }
        },
        {
            "id": 45,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 45,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-31T19:47:21.772Z",
            "updatedAt": "2021-03-31T19:47:21.772Z",
            "message": {
                "id": 45,
                "subject": "this is another story entirely",
                "body": "<p>Nulla imperdiet ornare mauris vel varius. Morbi tincidunt ornare efficitur. Praesent dapibus eros et felis blandit molestie. Aliquam at fringilla nisi, eget scelerisque magna. Suspendisse tempus ipsum dui.</p><p>Vivamus at euismod dui. Ut nec enim varius, accumsan sapien a, interdum orci. Donec et ligula tempus, viverra massa sit amet, lacinia turpis.</p><p>Praesent viverra, est ac lobortis feugiat, augue nibh tincidunt mi, sed malesuada neque metus a est. Quisque malesuada nibh in sem consequat, ut facilisis est elementum. Fusce nec eleifend tortor.</p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-31T19:47:21.672Z",
                "updatedAt": "2021-03-31T19:47:21.672Z"
            }
        },
        {
            "id": 32,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 32,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:34:31.646Z",
            "updatedAt": "2021-03-29T17:49:19.966Z",
            "message": {
                "id": 32,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:34:31.613Z",
                "updatedAt": "2021-03-15T19:34:31.613Z"
            }
        },
        {
            "id": 37,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "businessId": 190,
            "messageId": 37,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "chuks sahmie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:36:14.972Z",
            "updatedAt": "2021-03-29T17:49:00.857Z",
            "message": {
                "id": 37,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:36:14.956Z",
                "updatedAt": "2021-03-15T19:36:14.956Z"
            }
        },
        {
            "id": 40,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "businessId": 190,
            "messageId": 40,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "chuks sahmie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:53:10.455Z",
            "updatedAt": "2021-03-29T16:08:57.996Z",
            "message": {
                "id": 40,
                "subject": "test post",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:53:10.446Z",
                "updatedAt": "2021-03-15T19:53:10.446Z"
            }
        },
        {
            "id": 35,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 35,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:35:56.307Z",
            "updatedAt": "2021-03-15T19:35:56.307Z",
            "message": {
                "id": 35,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:56.295Z",
                "updatedAt": "2021-03-15T19:35:56.295Z"
            }
        }
    ]
}
```

This endpoint retrieves all inbox messages.

### HTTP Request

`GET https://manifest-inbox-app.herokuapp.com/messages/inbox`

## GET All Sent Messages
```shell
curl "https://manifest-inbox-app.herokuapp.com/messages/sent"
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/messages/sent
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": [
        {
            "id": 56,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 56,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:14:43.231Z",
            "updatedAt": "2021-04-01T17:14:43.231Z",
            "message": {
                "id": 56,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:14:43.223Z",
                "updatedAt": "2021-04-01T17:14:43.223Z"
            }
        },
        {
            "id": 55,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 55,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:14:41.360Z",
            "updatedAt": "2021-04-01T17:14:41.360Z",
            "message": {
                "id": 55,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:14:41.348Z",
                "updatedAt": "2021-04-01T17:14:41.348Z"
            }
        },
        {
            "id": 54,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 54,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:14:40.161Z",
            "updatedAt": "2021-04-01T17:14:40.161Z",
            "message": {
                "id": 54,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:14:40.152Z",
                "updatedAt": "2021-04-01T17:14:40.152Z"
            }
        },
        {
            "id": 53,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 53,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:12:53.969Z",
            "updatedAt": "2021-04-01T17:12:53.969Z",
            "message": {
                "id": 53,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:12:53.961Z",
                "updatedAt": "2021-04-01T17:12:53.961Z"
            }
        },
        {
            "id": 52,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 52,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:12:52.714Z",
            "updatedAt": "2021-04-01T17:12:52.714Z",
            "message": {
                "id": 52,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:12:52.696Z",
                "updatedAt": "2021-04-01T17:12:52.696Z"
            }
        },
        {
            "id": 51,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 51,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:12:51.683Z",
            "updatedAt": "2021-04-01T17:12:51.683Z",
            "message": {
                "id": 51,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:12:51.669Z",
                "updatedAt": "2021-04-01T17:12:51.669Z"
            }
        },
        {
            "id": 50,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 50,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:11:46.580Z",
            "updatedAt": "2021-04-01T17:11:46.580Z",
            "message": {
                "id": 50,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:11:46.557Z",
                "updatedAt": "2021-04-01T17:11:46.557Z"
            }
        },
        {
            "id": 49,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 49,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:11:44.920Z",
            "updatedAt": "2021-04-01T17:11:44.920Z",
            "message": {
                "id": 49,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:11:44.904Z",
                "updatedAt": "2021-04-01T17:11:44.904Z"
            }
        },
        {
            "id": 48,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 48,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T17:07:50.209Z",
            "updatedAt": "2021-04-01T17:07:50.209Z",
            "message": {
                "id": 48,
                "subject": "hello world",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T17:07:50.189Z",
                "updatedAt": "2021-04-01T17:07:50.189Z"
            }
        },
        {
            "id": 47,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 47,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-04-01T14:13:23.835Z",
            "updatedAt": "2021-04-01T14:13:23.835Z",
            "message": {
                "id": 47,
                "subject": "hello world1",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T14:13:23.684Z",
                "updatedAt": "2021-04-01T14:13:23.684Z"
            }
        },
        {
            "id": 45,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 45,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-31T19:47:21.772Z",
            "updatedAt": "2021-03-31T19:47:21.772Z",
            "message": {
                "id": 45,
                "subject": "this is another story entirely",
                "body": "<p>Nulla imperdiet ornare mauris vel varius. Morbi tincidunt ornare efficitur. Praesent dapibus eros et felis blandit molestie. Aliquam at fringilla nisi, eget scelerisque magna. Suspendisse tempus ipsum dui.</p><p>Vivamus at euismod dui. Ut nec enim varius, accumsan sapien a, interdum orci. Donec et ligula tempus, viverra massa sit amet, lacinia turpis.</p><p>Praesent viverra, est ac lobortis feugiat, augue nibh tincidunt mi, sed malesuada neque metus a est. Quisque malesuada nibh in sem consequat, ut facilisis est elementum. Fusce nec eleifend tortor.</p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-31T19:47:21.672Z",
                "updatedAt": "2021-03-31T19:47:21.672Z"
            }
        },
        {
            "id": 32,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 32,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:34:31.646Z",
            "updatedAt": "2021-03-29T17:49:19.966Z",
            "message": {
                "id": 32,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:34:31.613Z",
                "updatedAt": "2021-03-15T19:34:31.613Z"
            }
        },
        {
            "id": 34,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 34,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:35:23.591Z",
            "updatedAt": "2021-03-15T19:55:18.344Z",
            "message": {
                "id": 34,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:23.559Z",
                "updatedAt": "2021-03-15T19:35:23.559Z"
            }
        },
        {
            "id": 36,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 36,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:35:58.455Z",
            "updatedAt": "2021-03-15T19:55:18.333Z",
            "message": {
                "id": 36,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:58.423Z",
                "updatedAt": "2021-03-15T19:35:58.423Z"
            }
        },
        {
            "id": 35,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 35,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": false,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:35:56.307Z",
            "updatedAt": "2021-03-15T19:35:56.307Z",
            "message": {
                "id": 35,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:56.295Z",
                "updatedAt": "2021-03-15T19:35:56.295Z"
            }
        }
    ]
}
```

This endpoint gets all sent messages.

### HTTP Request

`GET https://manifest-inbox-app.herokuapp.com/messages/sent`

## GET All Trash Messages
```shell
curl "https://manifest-inbox-app.herokuapp.com/messages/trash"
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/messages/trash
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": [
        {
            "id": 42,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 42,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T20:13:02.504Z",
            "updatedAt": "2021-04-01T17:27:02.684Z",
            "message": {
                "id": 42,
                "subject": "Hello Test",
                "body": "<p><strong>Hello Test </strong></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T20:13:02.494Z",
                "updatedAt": "2021-03-15T20:13:02.494Z"
            }
        },
        {
            "id": 39,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 39,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:49:36.254Z",
            "updatedAt": "2021-04-01T17:27:02.673Z",
            "message": {
                "id": 39,
                "subject": "okay this is from react",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:49:36.215Z",
                "updatedAt": "2021-03-15T19:49:36.215Z"
            }
        },
        {
            "id": 38,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 38,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:48:59.528Z",
            "updatedAt": "2021-04-01T17:27:02.660Z",
            "message": {
                "id": 38,
                "subject": "test tags from react",
                "body": "<p class=\"ql-align-justify\">Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:48:59.516Z",
                "updatedAt": "2021-03-15T19:48:59.516Z"
            }
        },
        {
            "id": 33,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 33,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:35:22.289Z",
            "updatedAt": "2021-04-01T17:26:07.364Z",
            "message": {
                "id": 33,
                "subject": "receivers",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:35:22.241Z",
                "updatedAt": "2021-03-15T19:35:22.241Z"
            }
        },
        {
            "id": 31,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 31,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T19:29:33.524Z",
            "updatedAt": "2021-04-01T17:26:07.332Z",
            "message": {
                "id": 31,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:29:33.505Z",
                "updatedAt": "2021-03-15T19:29:33.505Z"
            }
        },
        {
            "id": 46,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 46,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "read",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-04-01T07:39:20.785Z",
            "updatedAt": "2021-04-01T17:23:21.389Z",
            "message": {
                "id": 46,
                "subject": "hello world1",
                "body": "message body",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-04-01T07:39:20.646Z",
                "updatedAt": "2021-04-01T07:39:20.646Z"
            }
        },
        {
            "id": 43,
            "receiverId": "617e38be-49d1-4a66-a0f6-704756383812",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 43,
            "receiver_userName": "Mrsam sammie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": true,
            "createdAt": "2021-03-15T20:13:03.432Z",
            "updatedAt": "2021-03-29T15:10:31.822Z",
            "message": {
                "id": 43,
                "subject": "Hello Test",
                "body": "<p><strong>Hello Test </strong></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T20:13:03.419Z",
                "updatedAt": "2021-03-15T20:13:03.419Z"
            }
        },
        {
            "id": 29,
            "receiverId": "7b544312-82d1-482d-982b-370f9d3e2fdf",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 29,
            "receiver_userName": "chuks sahmie",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:28:21.991Z",
            "updatedAt": "2021-03-15T19:48:04.219Z",
            "message": {
                "id": 29,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:28:21.960Z",
                "updatedAt": "2021-03-15T19:28:21.960Z"
            }
        },
        {
            "id": 30,
            "receiverId": "61588387-8fe6-4bc4-ba2e-4ee8a8cb5684",
            "senderId": "617e38be-49d1-4a66-a0f6-704756383812",
            "businessId": 190,
            "messageId": 30,
            "receiver_userName": "Samuel Nwoko",
            "sender_userName": "Mrsam sammie",
            "status": "unread",
            "type": "receiver",
            "deleted_by_sender": true,
            "deleted_by_receiver": false,
            "createdAt": "2021-03-15T19:28:23.537Z",
            "updatedAt": "2021-03-15T19:48:04.194Z",
            "message": {
                "id": 30,
                "subject": "welcome to my blog, i'll be hosting a live webinar soon!",
                "body": "<h2>What is Lorem Ipsum?</h2><p class=\"ql-align-justify\"><strong>Lorem Ipsum</strong>&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p><h2>Why do we use it?</h2><p class=\"ql-align-justify\">It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).</p><p><br></p>",
                "businessId": 190,
                "starred": null,
                "is_forwarded": null,
                "createdAt": "2021-03-15T19:28:23.516Z",
                "updatedAt": "2021-03-15T19:28:23.516Z"
            }
        }
    ]
}
```

This endpoint gets all trash messages.

### HTTP Request

`GET https://manifest-inbox-app.herokuapp.com/messages/trash`

## GET All Drafts

```shell
curl "https://manifest-inbox-app.herokuapp.com/messages/draft/all" \
  -X DELETE \
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/messages/draft/all
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": [
        {
            "id": 10,
            "subject": "not sure i want to send this yet",
            "body": "i want to leave this message to send later",
            "businessId": 190,
            "receivers": null,
            "receiverId": "",
            "userId": "617e38be-49d1-4a66-a0f6-704756383812",
            "createdAt": "2021-04-01T17:18:36.900Z",
            "updatedAt": "2021-04-01T17:18:36.900Z"
        },
        {
            "id": 9,
            "subject": "not sure i want to send this yet",
            "body": "i want to leave this message to send later",
            "businessId": 190,
            "receivers": null,
            "receiverId": "",
            "userId": "617e38be-49d1-4a66-a0f6-704756383812",
            "createdAt": "2021-04-01T07:50:33.576Z",
            "updatedAt": "2021-04-01T07:50:33.576Z"
        }
    ]
}
```

This endpoint gets all drafts.

### HTTP Request

`GET https://manifest-inbox-app.herokuapp.com/messages/draft/all`

## POST Reply Message

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/reply" \
  -H "Authorization: token"
```

```javascript
{
    "body": "I am replying to your initial business proposal",
    "id": 46
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "message sent successfully!"
}
```

This endpoint replies a message.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/reply`


## POST Mark Message as Read

```shell
curl "https://manifest-inbox-app.herokuapp.com/message/status/update" \
  -H "Authorization: token"
```

```javascript
{
    "id": 46
}
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "message": "message sent successfully!"
}
```

This endpoint marks a message as read.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/message/status/update`

# Users

## POST All Users

```shell
curl "https://manifest-inbox-app.herokuapp.com/users" \
  -H "Authorization: token"
```

```javascript
https://manifest-inbox-app.herokuapp.com/users 
```

> The above command returns JSON structured like this:

```json
{
    "status": true,
    "data": {
        "users": [
            {
                "id": "617e38be-49d1-4a66-a0f6-704756383812",
                "email": "layzie2e@gmail.com",
                "name": "Mrsam sammie",
                "role_id": 5,
                "role_level": 4,
                "role_name": "Manager",
                "profile_id": "78",
                "profile_name": "member",
                "accepted": 1,
                "department_name": "finance",
                "department_id": 162,
                "status": 1
            },
            {
                "id": "7b544312-82d1-482d-982b-370f9d3e2fdf",
                "email": "samuelchuksahmie@gmail.com",
                "name": "chuks sahmie",
                "role_id": 7,
                "role_level": 6,
                "role_name": "Team Lead",
                "profile_id": "79",
                "profile_name": "staff",
                "accepted": 1,
                "department_name": "chef",
                "department_id": 163,
                "status": 1
            }
        ]
    }
}
```

This endpoint retrieves all users.

### HTTP Request

`POST https://manifest-inbox-app.herokuapp.com/users`


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

