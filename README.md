# BÁO CÁO KIỂM THỬ HIỆU NĂNG VỚI APACHE JMETER

## 1. Giới thiệu về Apache JMeter
**Apache JMeter** là một phần mềm mã nguồn mở được viết bằng Java, chuyên sử dụng để kiểm thử hiệu năng (Performance Testing), kiểm thử sức tải (Load Testing) và đo lường khả năng chịu tải của các ứng dụng Web và API.

JMeter cho phép giả lập hàng loạt người dùng đồng thời (Virtual Users) gửi yêu cầu tới máy chủ nhằm đo lường các chỉ số quan trọng như thời gian phản hồi (Response Time), băng thông xử lý (Throughput) và tỷ lệ lỗi (Error Rate).

---

## 2. Kịch bản Kiểm thử (Test Scenario)

- **Target API:** `https://reqres.in/api/login`
- **Phương thức HTTP:** `POST`
- **Tham số truyền vào (Parameters):**
  - `email`: `eve.holt@reqres.in`
  - `password`: `cityslicka`
- **Số lượng người dùng giả lập (Threads):** `10 users`
- **Thời gian khởi tạo (Ramp-up Period):** `1 second`
- **Số vòng lặp (Loop Count):** `1`
- **Tổng số Request thực hiện:** `10 requests`

---

## 3. Kết quả Thực hành Kiểm thử

<img width="1212" height="681" alt="image" src="https://github.com/user-attachments/assets/a3ef4255-ae6c-4a0f-9c31-25d5f0a00397" />

### 3.1. Cấu hình HTTP Request
Thực hiện cấu hình phương thức `POST`, thiết lập Server Name `reqres.in`, đường dẫn Path `api/login` và truyền các tham số đăng nhập.

<img width="1215" height="681" alt="image" src="https://github.com/user-attachments/assets/958a1c1a-97d5-4840-a273-c069dd513028" />

### 3.2. Cấu hình kịch bản chịu tải (Thread Group)
Thực hiện thiết lập giả lập 10 người dùng gửi yêu cầu đồng thời tới server trong thời gian 1 giây.

<img width="1212" height="682" alt="image" src="https://github.com/user-attachments/assets/ce9ef998-d574-475b-9d9e-e00fd1dfb5d3" />

### 3.3. Kết quả Kiểm thử (View Results Tree)
Thực hiện chạy kịch bản. Tất cả 10/10 request gửi đi đều phản hồi thành công xuất sắc với **Status Code 200 OK** và không phát sinh lỗi.

<img width="1213" height="682" alt="image" src="https://github.com/user-attachments/assets/b633b6b6-ce2d-4df5-a79d-6abd7e59e460" />
