# Insta-Backend
2021.11.15 ~ 2021.12.03   
- Frontend: React
- Backend: Springboot & java
- connection: TCP/IP Socket

## π TEAM
[κΉλ―Όμ£Ό](https://github.com/MINJU-KIMmm)|[κΉμ€μ](https://github.com/ottl-seo)|[μ΄μ±μ](https://github.com/lcheun)|
|:---:|:---:|:---:|
<img src="https://github.com/MINJU-KIMmm.png" width="150" height="150">|<img src="https://github.com/ottl-seo.png" width="150" height="150" >|<img src="https://github.com/lcheun.png" width="150" height="150">|

## π API λͺμΈ
### 1. μ€μκ° νΌλ μλ‘λ
<details>
<summary>[POST] κ²μκΈ μλ‘λ</summary>
<div markdown="1">

### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| POST | api/posts | ν¬μ€νΈ κ²μ |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| image | MultipartFile | image νμΌ |
| requestDto | String | requestDto json ννλ‘ |

### request μμ

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2539e444-2219-4e4f-8087-07c6fb1c953c/Untitled.png)

requestDto μμ

```json
{
    "user":{
        "userNo":1,
        "userId":"efub",
        "fileSize":0,
        "originalFileName":"null",
        "filePath":"null"
    },
    "content":"λλ²κ²μλ¬Όνμ€νΈ!"
}
```

### Response

| postNo | String | μλ‘­κ² κ²μλ post λ²νΈλ₯Ό String ννλ‘ λ°ν |
| --- | --- | --- |


</div>
</details>

<details>
<summary>[κ²μκΈ λͺ©λ‘ λΆλ¬μ€κΈ°</summary>
<div markdown="1">
  
### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Get | /postList | λͺ¨λ  ν¬μ€νΈ λΆλ¬μ€κΈ° |

### Response

| PostList | List<PostDto> | μλ‘­κ² κ²μλ post λ²νΈλ₯Ό String ννλ‘ λ°ν |
| --- | --- | --- |

**response μμ**

```json
[
    {
        "postNo": 1,
        "userInfo": {
            "userNo": 1,
            "userId": "efub",
            "fileSize": 0,
            "originalFileName": "null",
            "filePath": null
        },
        "content": "μ²«κ²μλ¬Όνμ€νΈ!",
        "fileSize": 39366,
        "originalFileName": "review post api ex.png",
        "filePath": "https://efub-insta-bucket.s3.ap-northeast-2.amazonaws.com/review%20post%20api%20ex.png"
    },
    {
        "postNo": 2,
        "userInfo": {
            "userNo": 1,
            "userId": "efub",
            "fileSize": 0,
            "originalFileName": "null",
            "filePath": null
        },
        "content": "λλ²κ²μλ¬Όνμ€νΈ!",
        "fileSize": 39366,
        "originalFileName": "review post api ex.png",
        "filePath": "https://efub-insta-bucket.s3.ap-northeast-2.amazonaws.com/review%20post%20api%20ex.png"
    }
]
```
  </div>
</details>
  

### 2. κ²μκΈ μ’μμ
<details>
<summary>[GET] μ’μμ λλ₯Έ μ¬μ©μ λͺ©λ‘ λΆλ¬μ€κΈ° </summary>
<div markdown="1">

### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Get | /{postNo}/likeList | ν΄λΉ ν¬μ€νΈ μ’μμ ν μ μ  λͺ©λ‘ λΆλ¬μ€κΈ° |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| postNo | Long | κ²μκΈ λ²νΈ |
|  |  |  |

### request μμ

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/44191a38-13b1-44ed-8895-6562c9d39d9c/Untitled.png)

### Response

| UserLisst | List<UserDto> | ν΄λΉ κ²μκΈμ μ’μμν User μ λ³΄λ₯Ό List νμμΌλ‘ λ°ν |
| --- | --- | --- |

**response μμ**

```json
[
    {
        "userNo": 1,
        "userId": "efub",
        "fileSize": 0,
        "originalFileName": "null",
        "filePath": null
    },
    {
        "userNo": 2,
        "userId": "efub2",
        "fileSize": 0,
        "originalFileName": "null",
        "filePath": null
    }
]
```
  </div>
</details>

<details>
<summary>[GET] μ’μμ λλ₯Έ μ¬μ©μ μ λΆλ¬μ€κΈ°</summary>
<div markdown="1">
  
### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Get | /{postNo}/likeListCount | ν΄λΉ ν¬μ€νΈ μ’μμ ν μ μ  μ λΆλ¬μ€κΈ° |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| postNo | Long | κ²μκΈ λ²νΈ |
|  |  |  |

### request μμ

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1353e750-ef30-44b0-abdf-40454463d8a4/Untitled.png)

### Response

| likeUserCount | Long | ν΄λΉ κ²μκΈμ μ’μμν μ μ  μ λ°ν |
| --- | --- | --- |
  </div>
</details>

<details>
<summary>[PATCH] κ²μκΈ μ’μμ μ·¨μ</summary>
<div markdown="1">
  
### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Patch | /{postNo}/{userNo}/like | ν¬μ€νΈ μ’μμ/μ·¨μ |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| postNo | Long | κ²μκΈ λ²νΈ |
| userNo | Long | μ μ  λ²νΈ |

### request μμ

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/79dc87cd-0111-411d-a1f4-4125572422a8/Untitled.png)

### Response

| ok | String | μμμ΄ μ λλ‘ μνλλ©΄ "ok" λ¬Έμμ΄ λ°ν |
| --- | --- | --- |

  </div>
</details>

### 3. μ±ν (Direct Message)
    
<details>
<summary>[POST] μ±νλ°© μμ±</summary>
<div markdown="1">

### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| POST | http://localhost:8080/chat/room | μ±νλ°© λ§λ€κΈ° |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| name | String | μ±νλ°© μ΄λ¦ |

### Response

| roomNo | String | μ±νλ°© κ³ μ  ID μμ±νμ¬ λ°ν |
| --- | --- | --- |
| name | String | μλ ₯λ°μ κ°μΌλ‘ μ±νλ°© μ΄λ¦ μ€μ  |

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/aadc5860-0e6e-4b8c-9d47-85e9c5a08b74/Untitled.png)

μ±νλ°©μ΄ λ§λ€μ΄μ§ κ²μ. κ³ μ  ID(roomNo)λ°ν. 

μ΄μ  μ΄ roomNoλ‘ μ±νλ°©μ μμ₯ κ°λ₯.

  </div>
</details>

<details>
<summary>[MESSAGE] μ±νλ°© μμ₯ </summary>
<div markdown="1">
### Request

μ±ν λ©μλλ `@MessageMapping` μ¬μ©, URLλ [http://κ°](http://κ°) μλ ws:// μ¬μ©ν¨.

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Message | localhost:8080/pub/chat/message | μ±ν λ©μμ§ μ μ‘ |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| ChatMsgDto | JSON | ChatMsgDto json ννλ‘ |

Request μμ

```json
{
  "type":"ENTER",
  "roomNo":"5007fc94-ebbe-486c-ae00-7e21f632109b",
  "sender":"yoonseo",
  "content":""
}
```

### Response

[localhost:8080/sub/chat/room/{roomNo}](http://localhost:8081/sub/chat/room/{roomNo}) λ‘ μ±νμ΄ μ μ‘λ¨.

  </div>
</details>

<details>
<summary>[MESSAGE] λ©μμ§ μ μ‘</summary>
<div markdown="1">
  
### Request

typeμ΄ `TALK` μΈ κ²λ§ λ€λ¦.

| Method | URL | μ€λͺ |
| --- | --- | --- |
| Message | localhost:8080/pub/chat/message | μ±ν λ©μμ§ μ μ‘ |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| ChatMsgDto | JSON | ChatMsgDto json ννλ‘ |

Request μμ

```json
{
  "type":"TALK",
  "roomNo":"5007fc94-ebbe-486c-ae00-7e21f632109b",
  "sender":"yoonseo",
  "content":"hihi"
}
```

### Response

[localhost:8080/sub/chat/room/{roomNo}](http://localhost:8081/sub/chat/room/{roomNo}) λ‘ μ±νμ΄ μ μ‘λ¨.

  </div>
</details>

<details>
<summary>[GET] μ±νλ°© λͺ©λ‘ λΆλ¬μ€κΈ° </summary>
<div markdown="1">
  
### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| GET | localhost:8080/chat/rooms |  |
  </div>
</details>

<details>
<summary>[POST] μ±ν λ©μμ§ DB μ μ₯</summary>
<div markdown="1">
### Request

| Method | URL | μ€λͺ |
| --- | --- | --- |
| POST | localhost:8080/send | μ±ν λ©μμ§ DBμ μκΈ° |

### Request νμ

| Name | type | μ€λͺ |
| --- | --- | --- |
| requestDto | JSON | requestDto json ννλ‘ |

requestDto μμ

```json
{
        "messageNo": 11,
        "chatRoom": {
            "roomNo": "dfds",
            "roomName": "sdfsd",
            "sender": {
                "userNo": 1,
                "userId": "efub",
                "fileSize": 0,
                "originalFileName": "null",
                "filePath": null
            },
            "receiver": {
                "userNo": 2,
                "userId": "kimmnju",
                "fileSize": 0,
                "originalFileName": "null",
                "filePath": "null"
            }
        },
        "nickname": "ottl.seo",
        "flag": true,
        "message": "μλ"
    }
```

### Response

| Name | type | μ€λͺ |
| --- | --- | --- |
| messageNo | int | λ©μμ§ λ²νΈ λ°ν |

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e97c901a-10e0-45d8-8abc-16d30b3cbf17/Untitled.png)
  </div>
</details>


