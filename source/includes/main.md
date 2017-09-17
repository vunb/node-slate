# Giới thiệu

**YEU.AI** là một nền tảng dịch vụ cung cấp các api cho các tác vụ xử lý và hiểu ngôn ngữ tự nhiên tiếng Việt. Cung cấp hai dịch vụ chính của nền tảng nhận thức:

* **Chatbot**: Trợ lý ảo hỗ trợ giao tiếp với khách hàng, **tổng hợp thông tin [1]** về khách hàng
* **NLP Sdk**: Cung cấp các công cụ và thư viện cho developers để có thể tùy biến ứng dụng ở mức `'thấp'` hơn.

Các api / thư viện hỗ trợ phát triển được tích hợp:

* **API NLP**: Cung cấp api cho các bài toán nền tảng của xử lý ngôn ngữ tự nhiên, như: Part-of-Speech tagging, Word segment, Chunking, ...
* **API NLU**: Cung cấp các công cụ cho bài toán HIỂU ngôn ngữ tự nhiên, như: Phân lớp ý định người dùng, phân lớp câu hỏi (type & domain), bóc tách các chủ đề & thực thể được đề cập đến trong văn bản và câu hội thoại
* **API Speech**: Cung cấp công cụ tổng hợp giọng nói (TTS) và nhận dạng giọng nói (ASR).

**Đặc biệt (*)**: Cá nhân là các developers được sử dụng API và dịch vụ miễn phí của nền tảng dịch vụ Yeu.AI.

Phiên bản hiện tại `0.9` đã có thể sử dụng được các api sau đây:

* Tách từ (Tokenization)
* Tách câu (Chunking)
* Dán nhãn từ loại (POS tagging)
* Phân lớp câu hỏi, nhãn: `WHAT`, `WHEN`, `WHO`

Tính năng sắp tới:

* Phân lớp văn bản (Text classsifcation): `Du lịch`, `thể thao`, `kinh doanh`, ...
* Phân lớp câu hỏi (Question classification), nhãn: `WHERE`, `YESNO`, `HOW`
* Phân tích cảm xúc (Sentiment analysis)
* Phân tích phụ thuộc ngữ pháp (Dependency parsing)
* Phát hiện ý định người dùng (Intent classification)
* Nhận dạng thực thể có tên (Named entity recognition)

# Xác thực

Phiên bản hiện tại `0.9` không yêu cầu xác thực!

# NLP API

> Cài đặt thư viện:

```bash
# Sử dụng chương trình curl, mặc định đã được cài trên Linux.
# Nếu chưa tồn tại hãy dùng lệnh sau đây để cài đặt

# Ubuntu:
sudo apt-get install curl

# CentOS:
sudo yum install curl

# Windows:
Tải ở đây -> https://curl.haxx.se/download.html

```

```javascript
// Cài đặt sử dụng npm
npm install yeuai --save
```

Hiện tại yeu.ai đã cung cấp cho developer sử dụng bằng ngôn ngữ javascript/nodejs thông qua gói thư viện npm:  [npmjs.com/package/yeuai](https://npmjs.com/package/yeuai).

Yeu.ai cũng cung cấp giao diện truy cập api thông qua đặc tả Swagger, hoặc có thể sử dụng `curl` để thử nghiệm trước kết quả, trước khi tích hợp vào mã chương trình của bạn.

* https://nlp.api.ai/api/swagger

`Authorization: None`

<aside class="notice">
Phiên bản `v0.9` chưa yêu cầu mã xác thực và sẽ được cập nhật trong phiên bản sau.
</aside>

## Tách từ tiếng Việt

```bash
curl -G "https://nlp.yeu.ai/api/v1/tok" --data-urlencode "text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ."
```

```javascript
const yeuai = require('yeuai')

// ES6
yeuai.word_tokenize('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
  .then((tokens) => {
    console.log('Result:', tokens)
  })

// ES7
await tokens = yeuai.word_tokenize('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
console.log('Result:', tokens)
```

> Lệnh trên trả về cấu trúc JSON như thế này:

```json
{
  "response": [
    "Ngoài",
    "thương hiệu",
    ",",
    "giá cả",
    ",",
    "thời điểm",
    "mua hàng",
    "cũng",
    "là",
    "một",
    "yếu tố",
    "để",
    "có",
    "được",
    "sản phẩm",
    "tốt",
    "với",
    "giá",
    "rẻ",
    "."
  ]
}
```

Api này sẽ nhận input là câu văn hoặc đoạn văn bản cần tách từ.

### HTTP Request

`GET https://nlp.yeu.ai/api/v1/tok?text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.`

### Query Parameters

Parameter | Default | Mandatory | Description
--------- | ------- | ------- | -----------
text | false | yes | Đoạn văn bản cần tách từ
isToken | true | no | Nếu giá trị được set là `false`, output trả về là 1 đoạn văn bản

<aside class="success">
Tham khảo bảng nhãn dán từ loại [tại đây](#pos_tags)
</aside>

## Gán nhãn từ loại

```bash
curl -G "https://nlp.yeu.ai/api/v1/tag" --data-urlencode "text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ."
```

```javascript
const yeuai = require('yeuai')

// ES6
yeuai.pos_tag('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
  .then((tokens) => {
    console.log('Result:', tokens)
  })

// ES7
await tokens = yeuai.pos_tag('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
console.log('Result:', tokens)
```

> The above command returns JSON structured like this:

```json
{
   "response":[
      [
         "Ngoài",
         "E"
      ],
      [
         "thương hiệu",
         "N"
      ],
      [
         ",",
         "CH"
      ],
      [
         "giá cả",
         "N"
      ],
      [
         ",",
         "CH"
      ],
      [
         "thời điểm",
         "N"
      ],
      [
         "mua hàng",
         "N"
      ],
      [
         "cũng",
         "R"
      ],
      [
         "là",
         "V"
      ],
      [
         "một",
         "M"
      ],
      [
         "yếu tố",
         "N"
      ],
      [
         "để",
         "E"
      ],
      [
         "có",
         "V"
      ],
      [
         "được",
         "R"
      ],
      [
         "sản phẩm",
         "N"
      ],
      [
         "tốt",
         "A"
      ],
      [
         "với",
         "E"
      ],
      [
         "giá",
         "N"
      ],
      [
         "rẻ",
         "A"
      ],
      [
         ".",
         "CH"
      ]
   ]
}
```

Api này sẽ nhận input là câu hoặc đoạn văn cần gán nhãn.

### HTTP Request

`GET https://nlp.yeu.ai/api/v1/tag?text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.`

### Query Parameters

Parameter | Default | Mandatory | Description
--------- | ------- | ------- | -----------
text | false | yes | Đoạn văn bản cần gán nhãn

<aside class="success">
Tham khảo bảng nhãn dán từ loại [tại đây](#pos_tags)
</aside>

## Chunking

```bash
curl -G "https://nlp.yeu.ai/api/v1/chunk" --data-urlencode "text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ."
```

```javascript
const yeuai = require('yeuai')

// ES6
yeuai.chunk('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
  .then((tokens) => {
    console.log('Result:', tokens)
  })

// ES7
await tokens = yeuai.chunk('Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.')
console.log('Result:', tokens)
```

> Lệnh trên trả về cấu trúc JSON như thế này:

```json
{
   "response":[
      [
         "Ngoài",
         "E",
         "B-PP"
      ],
      [
         "thương hiệu",
         "N",
         "B-NP"
      ],
      [
         ",",
         "CH",
         "I-NP"
      ],
      [
         "giá cả",
         "N",
         "I-NP"
      ],
      [
         ",",
         "CH",
         "I-NP"
      ],
      [
         "thời điểm",
         "N",
         "I-NP"
      ],
      [
         "mua hàng",
         "N",
         "I-NP"
      ],
      [
         "cũng",
         "R",
         "B-VP"
      ],
      [
         "là",
         "V",
         "I-VP"
      ],
      [
         "một",
         "M",
         "B-NP"
      ],
      [
         "yếu tố",
         "N",
         "I-NP"
      ],
      [
         "để",
         "E",
         "B-PP"
      ],
      [
         "có",
         "V",
         "B-VP"
      ],
      [
         "được",
         "R",
         "I-VP"
      ],
      [
         "sản phẩm",
         "N",
         "B-NP"
      ],
      [
         "tốt",
         "A",
         "I-NP"
      ],
      [
         "với",
         "E",
         "B-PP"
      ],
      [
         "giá",
         "N",
         "B-NP"
      ],
      [
         "rẻ",
         "A",
         "I-NP"
      ],
      [
         ".",
         "CH",
         "O"
      ]
   ]
}
```

Api này sẽ nhận input là câu hoặc đoạn văn cần phân tích.

### HTTP Request

`GET https://nlp.yeu.ai/api/v1/chunk?text=Ngoài thương hiệu, giá cả, thời điểm mua hàng cũng là một yếu tố để có được sản phẩm tốt với giá rẻ.`

### Query Parameters

Parameter | Default | Mandatory | Description
--------- | ------- | ------- | -----------
text | false | yes | Đoạn văn bản cần phân tích

<aside class="success">
Tham khảo bảng nhãn dán từ loại [tại đây](#pos_tags)
</aside>

# NLU API

## Phân tích câu hỏi

```bash
curl -G "https://nlp.yeu.ai/api/v1/qtype" --data-urlencode "text=khi nào chương trình diễn ra?"
```

```javascript
const yeuai = require('yeuai')

// ES6
yeuai.classify_qtype('khi nào chương trình diễn ra?')
  .then((tokens) => {
    console.log('Result:', tokens)
  })

// ES7
await tokens = yeuai.classify_qtype('khi nào chương trình diễn ra?')
console.log('Result:', tokens)
```

> Lệnh trên trả về cấu trúc JSON như thế này:

```json
{
   "success":true,
   "response":{
      "classes":[
         {
            "confidence":"0.948622",
            "label":"WHEN"
         }
      ],
      "text":"khi nào chương trình diễn ra?"
   }
}
```

Api này sẽ nhận input là câu hỏi cần phân tích.

### HTTP Request

`GET https://nlp.yeu.ai/api/v1/qtype?text=khi nào chương trình diễn ra?`

### Query Parameters

Parameter | Default | Mandatory | Description
--------- | ------- | ------- | -----------
text | false | yes | Câu hỏi cần phân tích

<aside class="warning">
Phiên bản tiếp theo sẽ phân tích câu hỏi với nhiều thông tin hơn và cấu trúc có thể sẽ thay đổi (gợi ý) như này:

```json
{
   "success":true,
   "response":{
      "qSubtype":[
         {
            "confidence":"0.948622",
            "label":"WHEN"
         }
      ],
      "qType":[
         {
            "confidence":"0.971889",
            "label":"NUM:date"
         }
      ],
      "text":"khi nào chương trình diễn ra?"
   }
}
```
</aside>
