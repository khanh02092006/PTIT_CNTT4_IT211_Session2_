1. Lấy danh sách sách (có phân trang và lọc theo tác giả)

Method: GET
URL: /books
Query params: ?page=1&limit=10&author=...
Status thành công: 200 OK
Status lỗi: 400 nếu sai tham số (ví dụ page=-1)


2. Thêm sách mới

Method: POST
URL: /books
Query params: không có
Status thành công: 201 Created
Status lỗi: 400 nếu thiếu trường bắt buộc như title hay author


3. Cập nhật số lượng sách (chỉ một trường)

Method: PATCH
URL: /books/{id}
Query params: không có
Status thành công: 200 OK
Status lỗi: 404 nếu không tìm thấy sách, 400 nếu giá trị quantity không hợp lệ


4. Xóa sách

Method: DELETE
URL: /books/{id}
Query params: không có
Status thành công: 204 No Content
Status lỗi: 404 nếu sách không tồn tại


5. Lấy danh sách thẻ mượn của một sách (sub-resource)

Method: GET
URL: /books/{id}/loans
Query params: ?page=1&limit=10 nếu muốn phân trang
Status thành công: 200 OK
Status lỗi: 404 nếu sách không tồn tại


6. Tạo thẻ mượn mới

Method: POST
URL: /loans
Query params: không có
Status thành công: 201 Created
Status lỗi: 400 nếu thiếu bookId hoặc borrowerName, 404 nếu bookId không tồn tại


7. Trả sách (cập nhật ngày trả)

Method: PATCH
URL: /loans/{id}
Query params: không có
Status thành công: 200 OK
Status lỗi: 404 nếu không tìm thấy thẻ mượn, 400 nếu ngày trả không hợp lệ