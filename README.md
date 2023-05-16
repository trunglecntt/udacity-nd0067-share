# udacity-nd0067-share
My thoughts on working with udacity project (nd0067 course)

## Một vài thông tin cơ bản về khóa học
+ Tên khóa học: Full Stack JavaScript Developer
+ Category: Nanodegree
+ Số project: 4
+ Thời lượng: 4 tháng


## Đánh giá cơ bản
+ Khóa học tương tác nhiều với JavaScript (TypeScript) và tập trung các kiến thức liên quan đến việc phát triển
ứng dụng web dạng fullstack (đi từ Front-End, Back-End đến Deployment / CICD).
+ Mức độ khó: Intermediate.
+ Độ khó của mỗi project sẽ tăng dần (theo quan điểm cá nhân).
+ Riêng project cuối liên quan đến devops nên có thể
bước đầu hơi khó tiếp cận đối với các bạn developer

## Project
Overall tips:
```
- Hãy chú ý đến yêu cầu của project trước khi submit dù là nhỏ nhất, để tránh phải rework
- Project Rubric là công cụ tốt nhất để tự đánh giá project đã meet requirements hay chưa
```

### 01. Project 1: Image Processing API
:white_check_mark: **Description:**
Ở project này, bạn sẽ bước đầu xây dựng một NodeJS project cơ bản (sử dụng TypeScript).
Đây là project backend cung cấp xử lý API với NodeJS. Cụ thể bạn sẽ tạo API crop ảnh, cho phép người dùng nhập thông tin trên URL trình duyệt (gồm tên ảnh, size) và trả về ảnh kết quả
<br/>
:white_check_mark: **Starter code:**
Không (bạn sẽ phải xây dựng project từ đầu)
<br/>
:white_check_mark: **Đánh giá:**
Mặc dù xử lý Back-end không có gì phức tạp, nhưng cần lưu ý đến những thành phần nhỏ nhất cấu thành nên project (vì đây là mục tiêu của project) như: project dependencies, npm scripts, kiểu dữ liệu trong TypeScript...
<br/>
:white_check_mark: **Tips:**
- Bạn cần lưu ý đến npm script, bao gồm `start`, `build`, `test`, `lint`, `format`. Trong đó `lint` là script sử dụng `eslint` và `format` là script sử dụng `prettier` để tối ưu code convention.
Thiếu một trong các thành phần này thì project sẽ phải submit lại để review
- Khi nhập cùng tham số (tên ảnh, size) với ảnh đã được tạo thì sẽ lấy ảnh trực tiếp từ storage mà không xử lý resize ảnh lại từ đầu (cache image)
- Sử dụng `nodemon` để serve trực tiếp `.ts` file và reload browser khi có thay đổi. Không cần compile TypeScript rồi mới chạy
<br/>

### 02. Project 2: Storefront Backend
:white_check_mark: **Description:**
Ở project này, bạn sẽ thực hiện hoàn chỉnh các task liên quan đến Back-End development. Cá nhân mình thấy khá đầy đủ các công việc cần implement trong dự án thực tế (từ create database & schema đến migration, tạo API phục vụ client)
<br/>
:white_check_mark: **Starter code:**
Không (bạn sẽ phải xây dựng project từ đầu)
<br/>
:white_check_mark: **Đánh giá:**
Việc xử lý Back-End từ tạo database đến API khá quen thuộc với các developer, nhưng ở phần viết test sẽ hơi khó tiếp cận vì phải đảm bảo dữ liệu test được tách riêng ra database và không ảnh hưởng đến phần khác
<br/>
:white_check_mark: **Tips:**
- Cần chú ý đến việc thiết kế kiểu dữ liệu cho mỗi column trong table. Ví dụ như kiểu dữ liệu về giá, mặc dù đã thiết kế dạng decimal/numberic nhưng khi API get dữ liệu về sẽ convert giá trị về string
- Có một số npm script phức tạp mà các exercise đưa ra khi run thực tế sẽ không chạy.
Như npm script phục vụ test thì bạn nên migrate database trước, sau đó chạy test và cuối cùng là roll back database (dù test pass hay fail). Tham khảo:
```
export APP_ENV=test && db-migrate --env test up && npm run jasmine; db-migrate --env test reset
```
- Nên phân biệt rõ ràng package nào nằm trong `dependencies` và `devDependencies` để xác định chỉ dependency nào
được include trong môi trường production
<br/>

### 03. Project 3: MyStore
:white_check_mark: **Description:**
Sau project về Back-End, bạn sẽ được triển khai một project Front-End dạng e-commerce dựa trên Angular framework. Ứng dụng cho phép user xem các mặt hàng, chọn mỗi mặt hàng theo số lượng và đưa vào giỏ hàng để tiến hành thanh toán. Bạn chỉ cần implement logic trên UI, unit testing có thể impelement hoặc không
<br/>
:white_check_mark: **Starter code:**
Có (base trên Angular framework, tuy nhiên chỉ cung cấp folder chứa các component và CSS tương ứng)
<br/>
:white_check_mark: **Đánh giá:**
Project sẽ hơi tốn time ở bước xây dựng UI, nhưng ở bước implement xử lý các sự kiện sẽ đỡ tốn effort hơn. Project cũng check tuân thủ code convention chặt chẽ hơn các project trước, nên bạn cần follow udacity frontend code ngay từ đầu để giảm thiểu thời gian re-work
<br/>
:white_check_mark: **Tips:**
- Sử dụng (change) và (ngOnChange) event binding trong cả project, vì đây là yêu cầu trước khi submit
- Cần chú ý đến project description, không để nguyên file README.md của Angular để tránh phải submit lại
- Bạn có thể sử dụng các class trong CSS có sẵn mà Udacity cung cấp để phát triển (sẽ tối ưu thời gian hơn).
Nhưng để hiển thị layout giống với example thì phải cài thêm cả Bootstrap, mà trong starter code chưa install dependency này
<br/>

### 04. Project 4: Udagram
:white_check_mark: **Description:**
Một project về CI/CD cho ứng dụng fullstack. Nghĩa là trong repository sẽ bao gồm cả code Front-End và Back-End. Nhiệm vụ của bạn là xây dựng CI/CD workflow trên project có sẵn (kết hợp với Circle CI) để có thể build, deploy source code lên AWS resource (RDS, S3, Elastic Beanstalk)
<br/>
:white_check_mark: **Starter code:**
Có (cần thêm, sửa project hiện tại để đáp ứng requirement)
<br/>
:white_check_mark: **Đánh giá:**
Nếu chưa tiếp xúc với CICD/devops thì quá trình implement project sẽ gặp khá nhiều khó khăn, phải research thường xuyên mỗi khi deploy ứng dụng fail. Việc hoàn thiện config trên CircleCI thì dễ dàng hơn vì các script build, deploy
đã được cung cấp từ trước
<br/>
:white_check_mark: **Tips:**
- Project description cần đầy đủ các thành phần mô tả CICD workflow của bạn hoạt động chính xác (thư mục `docs` và `screenshots`)
- Nên tuân thủ về security đối với các environment variable. Ví dụ như đã setup trên CircleCI project config rồi thì bên trong Elastic Beanstalk không cần config nữa, mà sẽ set thông qua EB CLI (ở npm `deploy` script)
- Về các sơ đồ bên mà project yêu cầu, bạn có thể sử dụng draw.io để vẽ trực tiếp trên web `https://app.diagrams.net` hoặc các app khác như Cacoo, Lucidchart...
- Bên trong npm script project cung cấp không phải đã chính xác hoàn toàn. Bạn cần sửa đổi script `start` để khi run trên Elastic Beanstalk không gặp lỗi. Các script khác về cơ bản đã deploy được ứng dụng.
