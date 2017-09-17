# Bảng mã lỗi

<aside class="notice">Phần này sẽ mô tả các mã lỗi trả về khi gọi api không đúng cách hoặc truyền sai các giá trị tham số.</aside>

**Yeu.AI API** sử dụng bảng mã lỗi sau đây:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Truyền thiếu tham số hoặc sai kiểu dữ liệu
401 | Unauthorized -- API accessToken của bạn sai hoặc hết hạn sử dụng
403 | Forbidden -- Truy nhập vào api, tài nguyên không được phép
404 | Not Found -- Không tìm thấy tài nguyên yêu cầu
405 | Method Not Allowed -- Không hỗ trợ phương thức yêu cầu
406 | Not Acceptable -- Yêu cầu không được chấp nhận
410 | Gone -- Tài nguyên truy vấn không còn tồn tại
429 | Too Many Requests -- Bạn gửi quá nhiều truy vấn vượt quá giới hạn cho phép
500 | Internal Server Error -- Máy chủ có lỗi, hãy thử lại sau 1 khoảng thời gian
503 | Service Unavailable -- Dịch vụ bạn đang truy cập không có hoặc đang được nâng cấp
