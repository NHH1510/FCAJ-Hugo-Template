---
title : "Worklog"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
## 1.2. Worklog (Nhật ký theo tuần)

### Week 1
**Công việc đã làm:**
- Làm quen với đề tài và cùng nhóm phân chia công việc
- Phân tích yêu cầu hệ thống (music streaming web)
- Tìm hiểu kiến trúc tổng thể: Frontend – Backend – AWS
- Setup môi trường:
  - Node.js
  - AWS account (Lambda, API Gateway, DynamoDB)
- Nghiên cứu cách tổ chức API theo RESTful

**Kết quả đạt được:**
- Hiểu rõ vai trò cá nhân: phụ trách module Artists + Albums
- Nắm được luồng dữ liệu hệ thống
- Sẵn sàng bắt đầu phát triển backend

---

### Week 2
**Công việc đã làm:**
- Thiết kế schema cho Artists:
  - id, name, image, genre
- Tạo DynamoDB table (partition key: artist_id)
- Viết Lambda function:
  - getArtists
  - getArtistById
- Kết nối với API Gateway
- Test API bằng Postman

**Kết quả đạt được:**
- Hoàn thành API:
  - GET /artists
  - GET /artists/{id}
- API trả dữ liệu đúng format JSON
- Backend Artists hoạt động ổn định

---

### Week 3
**Công việc đã làm:**
- Thiết kế schema cho Albums:
  - id, title, artist_id, release_date, image
- Tạo DynamoDB table Albums
- Implement API:
  - GET /albums
  - GET /artists/{id}/albums
- Tối ưu query theo artist_id
- Test integration với Artists

**Kết quả đạt được:**
- Hoàn thành module Albums backend
- Query theo artist hoạt động chính xác
- Liên kết dữ liệu Artists – Albums thành công

---

### Week 4
**Công việc đã làm:**
- Setup frontend (React)
- Xây dựng trang danh sách Artists
- Gọi API từ backend (fetch /artists)
- Hiển thị:
  - Tên artist
  - Hình ảnh
- Thiết lập routing `/artists/:id`

**Kết quả đạt được:**
- Hiển thị danh sách Artists trên UI
- Kết nối frontend – backend thành công
- Luồng dữ liệu hoạt động đúng

---

### Week 5
**Công việc đã làm:**
- Xây dựng UI hiển thị Albums theo Artist
- Gọi API `/artists/{id}/albums`
- Render danh sách Albums:
  - Cover image
  - Title
- Cải thiện UI/UX (layout, spacing)

**Kết quả đạt được:**
- Hiển thị Albums theo Artist chính xác
- UI rõ ràng, dễ sử dụng hơn
- Đồng bộ dữ liệu với backend

---

### Week 6
**Công việc đã làm:**
- Xây dựng trang chi tiết Artist:
  - Thông tin + danh sách album
- Xây dựng trang chi tiết Album
- Xử lý routing động:
  - `/artists/:id`
  - `/albums/:id`
- Xử lý loading state

**Kết quả đạt được:**
- Hoàn thiện chức năng xem chi tiết
- Trải nghiệm người dùng tốt hơn
- Luồng điều hướng hoàn chỉnh

---

### Week 7
**Công việc đã làm:**
- Debug và xử lý lỗi:
  - CORS
  - API error
  - undefined data
- Refactor code:
  - Tách component
  - Clean code
- Tối ưu performance:
  - Giảm số lần gọi API
  - Xử lý state hợp lý

**Kết quả đạt được:**
- Hệ thống ổn định hơn
- Giảm lỗi runtime
- Code dễ maintain hơn

---

### Week 8
**Công việc đã làm:**
- Deploy backend:
  - AWS Lambda + API Gateway
- Deploy frontend:
  - S3 / GitHub Pages
- Test end-to-end:
  - Frontend ↔ Backend
- Fix lỗi production (CORS, endpoint)
- Làm project với Hugo và báo cáo thực tập

**Kết quả đạt được:**
- Module Artists + Albums chạy trên môi trường production
- Tích hợp thành công với hệ thống nhóm
- Hoàn thành đầy đủ phần cá nhân trong project