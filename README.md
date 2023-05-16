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
Hãy chú ý đến yêu cầu của project trước khi submit dù là nhỏ nhất, để tránh phải submit lại và tốn time review
Project Rubric là công cụ tốt nhất để base theo đó tự đánh giá project đã meet requirement hay chưa
```

### 01. Project 1: Image Processing API
+ Description: Ở project này, bạn sẽ bước đầu xây dựng một NodeJS project cơ bản (sử dụng TypeScript).
Đây là project backend cung cấp xử lý API với NodeJS. Cụ thể bạn sẽ tạo API crop ảnh, cho phép người dùng nhập thông tin trên URL trình duyệt (gồm tên ảnh, size) và trả về ảnh kết quả
+ Starter code: Không (bạn sẽ phải xây dựng project từ đầu)
+ Đánh giá: Mặc dù xử lý Back-end không có gì phức tạp, nhưng cần lưu ý đến những thành phần nhỏ nhất cấu thành
nên project (vì đây là mục tiêu của project) như: project dependencies, npm scripts, kiểu dữ liệu trong TypeScript...
+ Tips:
:white_check_mark: Bạn cần lưu ý đến npm script, bao gồm `start`, `build`, `test`, `lint`, `format`. Trong đó `lint` là script sử dụng `eslint` và `format` là script sử dụng `prettier` để tối ưu code convention.
Thiếu một trong các thành phần này thì project sẽ phải submit lại để review
<br/>
:white_check_mark: Khi nhập cùng tham số (tên ảnh, size) với ảnh đã được tạo thì sẽ lấy ảnh trực tiếp từ storage mà không xử lý resize ảnh lại từ đầu (cache image)
<br/>
:white_check_mark: Sử dụng `nodemon` để serve trực tiếp `.ts` file và reload browser khi có thay đổi
