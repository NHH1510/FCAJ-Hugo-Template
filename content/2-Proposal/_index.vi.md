---
title: "Đề xuất dự án"
date : "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### MUSIC STREAMING WEB

###  1.Tóm tắt điều hành

Dự án này tập trung xây dựng một hệ thống web nghe nhạc trực tuyến dựa trên kiến trúc serverless sử dụng các dịch vụ của AWS. Hệ thống cho phép người dùng truy cập và nghe nhạc trực tuyến, quản lý danh sách phát (playlist), đồng thời hỗ trợ nghệ sĩ và quản trị viên trong việc quản lý nội dung và vận hành nền tảng. Giải pháp được triển khai dựa trên các dịch vụ cốt lõi của AWS như Amazon S3 cho lưu trữ dữ liệu media, DynamoDB cho quản lý dữ liệu NoSQL, AWS Lambda cho xử lý logic backend, API Gateway cho việc tiếp nhận và định tuyến yêu cầu, và Cognito cho xác thực và phân quyền người dùng. Kiến trúc này giúp loại bỏ nhu cầu quản lý hạ tầng máy chủ truyền thống, đồng thời cung cấp khả năng mở rộng tự động và tối ưu hóa tài nguyên theo nhu cầu sử dụng. Việc áp dụng mô hình serverless không chỉ đảm bảo hiệu năng và khả năng mở rộng của hệ thống mà còn giúp tối ưu chi phí vận hành, đặc biệt trong phạm vi sử dụng của AWS Free Tier. Bên cạnh đó, hệ thống được thiết kế theo hướng tách biệt rõ ràng giữa frontend và backend, góp phần nâng cao khả năng bảo trì, mở rộng và tích hợp trong tương lai.Tổng thể, dự án thể hiện việc vận dụng hiệu quả các nguyên lý thiết kế hệ thống hiện đại trên nền tảng điện toán đám mây, hướng tới xây dựng một ứng dụng web có tính mở rộng cao, hiệu quả và phù hợp với nhu cầu thực tiễn.

###  2.Tuyên bố vấn đề

#### Vấn đề hiện tại

Trong bối cảnh nhu cầu chia sẻ và tiếp cận các sản phẩm âm nhạc cá nhân ngày càng gia tăng, các nền tảng hiện có vẫn chưa thực sự đáp ứng tốt nhu cầu của người dùng ở mức độ linh hoạt và cá nhân hóa cao. Đặc biệt, đối với các nghệ sĩ độc lập hoặc người dùng phổ thông, việc đăng tải và chia sẻ các nhạc phẩm cá nhân thường gặp nhiều rào cản liên quan đến quy trình phức tạp, hạn chế về quyền kiểm soát nội dung và khả năng tiếp cận người nghe. Bên cạnh đó, nhiều hệ thống hiện tại tập trung chủ yếu vào việc phân phối nội dung từ các nhà sản xuất lớn, dẫn đến việc các sản phẩm âm nhạc cá nhân khó được tiếp cận rộng rãi. Điều này làm giảm cơ hội phát triển và lan tỏa của các nghệ sĩ mới hoặc nội dung sáng tạo độc lập. Ngoài ra, việc quản lý nội dung và tương tác người dùng trong các nền tảng hiện có còn tồn tại một số hạn chế như thiếu công cụ hỗ trợ quản lý hiệu quả, khả năng mở rộng hệ thống chưa tối ưu, và chi phí vận hành cao khi số lượng người dùng tăng lên. Các vấn đề liên quan đến bảo mật, xác thực người dùng và kiểm duyệt nội dung cũng đặt ra nhiều thách thức trong quá trình xây dựng hệ thống. Do đó, cần thiết phải xây dựng một nền tảng web cho phép người dùng dễ dàng đăng tải, chia sẻ và quản lý các nhạc phẩm cá nhân, đồng thời đảm bảo hiệu năng, khả năng mở rộng và tối ưu chi phí. Hệ thống cần hướng đến việc hỗ trợ tốt cho cả người dùng phổ thông và nghệ sĩ độc lập, tạo ra một môi trường mở, linh hoạt và dễ tiếp cận.

#### Giải pháp

Để giải quyết các vấn đề đã đặt ra, hệ thống được xây dựng dựa trên mô hình kiến trúc serverless, sử dụng các dịch vụ cốt lõi của AWS nhằm đảm bảo khả năng mở rộng, tính linh hoạt và tối ưu chi phí vận hành. Cụ thể, hệ thống sử dụng Amazon S3 làm nền tảng lưu trữ media, audio, cho phép truy xuất nội dung một cách nhanh chóng và ổn định thông qua cơ chế lưu trữ dạng object. Dữ liệu nghiệp vụ của hệ thống, bao gồm thông tin người dùng, bài hát và danh sách phát được lưu trữ trong DynamoDB, sử dụng DynamoDB làm hệ thống có khả năng mở rộng tốt, linh hoạt trong tương lai. Về mặt xử lý logic, AWS Lambda được sử dụng để triển khai các chức năng backend đồng thời đóng vai trò trung gian tiếp nhận các yêu cầu từ phía người dùng đến các Lambda function trả kết quả về cho người dùng. Để đảm bảo tính bảo mật và quản lý người dùng, hệ thống sử dụng AWS Cognito cho việc xác thực và phân quyền, cung cấp cơ chế đăng ký, đăng nhập, cũng như quản lý phiên làm việc của người dùng một cách an toàn và hiệu quả. Kiến trúc tổng thể của hệ thống được thiết kế theo hướng tách biệt rõ ràng giữa các thành phần lưu trữ, xử lý và giao tiếp, giúp tăng khả năng bảo trì và mở rộng trong tương lai. Việc áp dụng các dịch vụ managed của AWS giúp giảm thiểu gánh nặng quản lý hạ tầng, đồng thời tận dụng được khả năng tự động mở rộng và tính sẵn sàng cao của nền tảng.

###  3.Kiến trúc giải pháp

Kiến trúc hệ thống được xây dựng trên nền tảng AWS Cloud theo mô hình serverless, bao gồm các thành phần chính: phân phối nội dung, xử lý nghiệp vụ, lưu trữ dữ liệu và xác thực người dùng. Các thành phần này được tổ chức theo từng lớp nhằm đảm bảo tính mở rộng, bảo mật và hiệu năng.

![ConnectPrivate](/images/aws_architec.png)

- Người dùng truy cập hệ thống thông qua Domain được quản lý bởi Route 53, kết hợp với Certificate Manager để ապահով kết nối HTTPS an toàn. Toàn bộ nội dung frontend được phân phối thông qua CloudFront, giúp tăng tốc độ truy cập nhờ cơ chế CDN và caching.
- AWS WAF được tích hợp nhằm bảo vệ hệ thống khỏi các tấn công phổ biến như SQL Injection hoặc DDoS. Nội dung web tĩnh (frontend) được lưu trữ trên S3 (S3 Web/App) và được CloudFront phân phối đến người dùng.
- Hệ thống sử dụng Cognito để xử lý các chức năng xác thực bao gồm đăng ký (Register), đăng nhập (Login) và cấp lại token (Refresh Token). API Gateway tích hợp Authorizer để kiểm tra token hợp lệ trước khi cho phép truy cập vào các dịch vụ backend.
- Toàn bộ logic nghiệp vụ được triển khai thông qua các Lambda function, được tổ chức theo từng nhóm chức năng riêng biệt:
  - Lambda song services: xử lý các chức năng liên quan đến bài hát
  - Lambda user services: quản lý thông tin người dùng
  - Lambda artist services: xử lý thông tin nghệ sĩ
  - Lambda account services: xử lý tài khoản và xác thực
  - Lambda history services: lưu trữ lịch sử hoạt động
- API Gateway đóng vai trò trung gian nhận request từ client và định tuyến đến Lambda tương ứng. Điều này giúp hệ thống dễ dàng mở rộng và tách biệt rõ ràng các module chức năng.
- DynamoDB: lưu trữ metadata của hệ thống như thông tin người dùng, bài hát, playlist, lịch sử
- S3 Media: lưu trữ các file audio và hình ảnh
- CloudWatch được sử dụng để theo dõi hoạt động của hệ thống, bao gồm log từ Lambda, API Gateway và các dịch vụ khác. Điều này hỗ trợ việc phát hiện lỗi, debug và tối ưu hệ thống trong quá trình vận hành.
- Amazon OpenSearch Service là một dịch vụ quản lý (managed service) tìm kiếm và phân tích dữ liệu phân tán, được phát triển dựa trên mã nguồn mở Elasticsearch. Dịch vụ này cho phép thu thập, lưu trữ, tìm kiếm và phân tích khối lượng dữ liệu khổng lồ theo thời gian thực (Real-time).

###  4.Triển khai kỹ thuật

#### Các giai đoạn triển khai

Dự án gồm 2 phần — xây dựng giao diện người dùng (Frontend) và phát triển hệ thống backend serverless — mỗi phần trải qua 4 giai đoạn:

*Nghiên cứu và vẽ kiến trúc:*  
Tìm hiểu các dịch vụ AWS (S3, DynamoDB, Lambda, API Gateway, Cognito, Amazon OpenSearch Service) và thiết kế kiến trúc hệ thống serverless phù hợp với bài toán chia sẻ nhạc phẩm cá nhân (trước khi triển khai dự án).

*Tính toán chi phí và kiểm tra tính khả thi:*  
Ước tính chi phí sử dụng AWS Free Tier, đánh giá khả năng vận hành với số lượng người dùng nhỏ và điều chỉnh thiết kế để phù hợp với tài nguyên miễn phí (Tuần 1–2).

*Điều chỉnh kiến trúc để tối ưu chi phí/giải pháp:*  
Tối ưu cách sử dụng Lambda, thiết kế DynamoDB theo query-first, giảm số lượng request và tối ưu luồng dữ liệu giữa các dịch vụ (Tuần 2–3).

*Phát triển, kiểm thử, triển khai:*  
Xây dựng frontend, triển khai các Lambda function, thiết lập API Gateway và tích hợp Cognito. Sau đó thực hiện kiểm thử giao diện, chức năng và triển khai hệ thống lên AWS (Tuần 3–7).

---

#### Yêu cầu kỹ thuật

*Frontend (Client):*  
Giao diện web cho phép người dùng nghe nhạc, quản lý nội dung và tương tác với hệ thống. Frontend được triển khai dưới dạng static web, lưu trữ trên S3 và phân phối thông qua CloudFront để tối ưu tốc độ truy cập.

*Backend (Serverless):*

- Hệ thống sử dụng AWS Lambda để xử lý logic nghiệp vụ, bao gồm:
  - Quản lý người dùng
  - Quản lý nội dung
  - Quản lý nghệ sĩ
  - Lưu trữ lịch sử hoạt động
- API Gateway đóng vai trò gateway trung gian, tiếp nhận request từ client và định tuyến đến Lambda tương ứng.
- Amazon OpenSearch Service hỗ trợ thu thập, lưu trữ, tìm kiếm và phân tích khối lượng dữ liệu khổng lồ theo thời gian thực.

*Lưu trữ dữ liệu:*

- DynamoDB: lưu trữ metadata (user, song, playlist, artist, history)
- S3: lưu trữ file audio và hình ảnh

*Xác thực và phân quyền:*

- Cognito được sử dụng để quản lý đăng ký, đăng nhập và phân quyền người dùng
- API Gateway tích hợp Authorizer để kiểm tra token trước khi xử lý request

*Triển khai và công cụ:*

- Sử dụng AWS SAM để triển khai các Lambda function và API Gateway
- Sử dụng GitHub để quản lý source code
- Sử dụng HTTP/REST API để kết nối frontend và backend

###  5. Ước tính chi phí AWS (Free Tier Usage)

Hệ thống được thiết kế dựa trên mô hình serverless và tận dụng tối đa AWS Free Tier nhằm giảm thiểu chi phí vận hành trong giai đoạn đầu.

Với quy mô người dùng nhỏ và tần suất truy cập trung bình, các dịch vụ AWS được ước tính chi phí như sau:

- *AWS Lambda:*  
  Nằm trong Free Tier (1 triệu request/tháng và 400,000 GB-seconds), đáp ứng đủ nhu cầu xử lý backend cơ bản → chi phí ≈ 0 USD.

- *Amazon API Gateway:*  
  Free Tier hỗ trợ 1 triệu request/tháng → chi phí ≈ 0 USD trong giai đoạn đầu.

- *Amazon DynamoDB:*  
  Free Tier cung cấp dung lượng lưu trữ và read/write capacity phù hợp với hệ thống nhỏ → chi phí ≈ 0 USD.

- *Amazon S3:*  
  Lưu trữ file audio và frontend (5GB miễn phí). Nếu dung lượng audio tăng, chi phí sẽ phát sinh nhưng vẫn ở mức thấp.

- *Amazon Cognito:*  
  Hỗ trợ 50,000 Monthly Active Users (MAU) miễn phí → phù hợp với hệ thống quy mô nhỏ.

- *CloudFront:*  
  Free Tier cung cấp 1TB data transfer/tháng → đủ cho nhu cầu streaming cơ bản.

- *Amazon OpenSearch Service:*
  Hỗ trợ 750 giờ/tháng cho instance loại *t2.micro.search* hoặc *t3.small.search*, 10 GB lưu trữ EBS (gp2 hoặc gp3). Chi phí lưu trữ (≤10GB) = 0 USD

Tổng chi phí ước tính trong giai đoạn đầu gần như bằng *0 USD/tháng* nếu nằm trong giới hạn Free Tier. Khi hệ thống mở rộng, chi phí sẽ tăng theo mức sử dụng nhưng vẫn được tối ưu nhờ mô hình pay-as-you-go.

---

###  6. Đánh giá rủi ro (Risk Assessment)

Trong quá trình triển khai và vận hành hệ thống, một số rủi ro có thể phát sinh bao gồm:

- *Rủi ro về hiệu năng:*  
  Khi số lượng người dùng tăng nhanh, hệ thống có thể gặp độ trễ trong truy xuất dữ liệu hoặc streaming nếu không tối ưu tốt.

- *Rủi ro về chi phí:*  
  Nếu vượt quá giới hạn Free Tier, chi phí AWS có thể tăng nhanh do số lượng request và dung lượng lưu trữ lớn.

- *Rủi ro về bảo mật:*  
  Các vấn đề liên quan đến token, phân quyền hoặc truy cập trái phép nếu cấu hình Cognito và IAM không chặt chẽ.

- *Rủi ro về thiết kế dữ liệu:*  
  Thiết kế DynamoDB không tối ưu có thể dẫn đến truy vấn kém hiệu quả và khó mở rộng.

- *Rủi ro về phụ thuộc dịch vụ cloud:*  
  Hệ thống phụ thuộc hoàn toàn vào AWS, có thể bị ảnh hưởng nếu xảy ra sự cố dịch vụ.

*Biện pháp giảm thiểu:*

- Tối ưu thiết kế dữ liệu và caching
- Thiết lập giới hạn chi phí (billing alerts)
- Áp dụng best practices về bảo mật (IAM, Cognito)
- Giám sát hệ thống qua CloudWatch

---

###  7. Kết quả kỳ vọng (Expected Outcomes)

Sau khi hoàn thành, hệ thống dự kiến đạt được các kết quả sau:

- *Xây dựng thành công nền tảng chia sẻ nhạc phẩm cá nhân:*  
  Cho phép người dùng đăng tải, quản lý và nghe nhạc trực tuyến một cách dễ dàng.

- *Hệ thống hoạt động ổn định và có khả năng mở rộng:*  
  Đáp ứng nhu cầu tăng trưởng người dùng nhờ kiến trúc serverless.

- *Tối ưu chi phí vận hành:*  
  Khai thác hiệu quả AWS Free Tier và mô hình pay-as-you-go.

- *Đảm bảo bảo mật và quản lý người dùng:*  
  Thông qua cơ chế xác thực và phân quyền bằng Cognito.

- *Nâng cao trải nghiệm người dùng:*  
  Giao diện thân thiện, tốc độ tải nhanh nhờ CloudFront và tối ưu frontend.

- *Tạo nền tảng phát triển trong tương lai:*  
  Dễ dàng mở rộng thêm các tính năng như gợi ý nhạc, AI recommendation, hoặc social features.