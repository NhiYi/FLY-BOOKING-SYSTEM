# ✈️ Fly Booking System – Dự án kiểm thử phần mềm

> **Dự án Manual Testing / QA – Hệ thống đặt vé máy bay**

![Testing](https://img.shields.io/badge/Testing-Manual%20Testing-blue)
![Project](https://img.shields.io/badge/Project-Fly%20Booking-orange)
![Test Cases](https://img.shields.io/badge/Test%20Cases-51-green)
![Coverage](https://img.shields.io/badge/Test%20Coverage-98.04%25-success)
![Status](https://img.shields.io/badge/Status-Test%20Completed-yellow)

---

## 📌 Tổng quan dự án

**Fly Booking System** là dự án thực hành **Kiểm thử phần mềm (Software Testing)** tập trung vào việc kiểm tra chức năng và luồng đặt vé máy bay của hệ thống.

Dự án kiểm thử toàn bộ luồng chính của người dùng từ:

**Tra cứu chuyến bay → Chọn chuyến bay → Nhập thông tin hành khách → Xác nhận đặt vé → Invoice → Thanh toán**

Hệ thống được xây dựng dựa trên tài liệu yêu cầu **Fly Booking Requirements V6** và tham khảo hệ thống PHPTRAVELS.

### 🎯 Mục tiêu kiểm thử

* Kiểm tra chức năng hệ thống theo đúng tài liệu yêu cầu.
* Kiểm tra các điều kiện và quy tắc nghiệp vụ.
* Phát hiện và ghi nhận lỗi phần mềm.
* Kiểm tra tính hợp lệ của dữ liệu đầu vào.
* Kiểm tra toàn bộ luồng đặt vé từ đầu đến cuối.
* Kiểm tra thông tin hóa đơn và thanh toán.
* Đánh giá chất lượng hệ thống trước khi release.

---

# 🧪 Phạm vi kiểm thử

Dự án tập trung vào **4 màn hình/chức năng chính**:

## 1. 🔎 Search – Tra cứu chuyến bay

Kiểm thử các chức năng:

* Nơi đi
* Nơi đến
* One Way / Round Trip
* Ngày đi
* Ngày về
* Số lượng người lớn
* Số lượng trẻ em
* Số lượng em bé
* Hạng vé:

  * Economy
  * Business
  * First
* Nút Search
* Kiểm tra trường bắt buộc
* Kiểm tra ngày đi/ngày về

Theo yêu cầu, khi chọn Round Trip thì **ngày về phải sau ngày đi**.

---

## 2. ✈️ Search Results – Danh sách chuyến bay

Kiểm thử:

* Hiển thị danh sách chuyến bay.
* Mã chuyến bay.
* Hãng hàng không.
* Điểm đi.
* Điểm đến.
* Thời gian khởi hành.
* Thời gian đến.
* Non-stop / Transit.
* Giá vé.
* Filter Route Stops.
* Filter Airlines.
* Nút Search.
* Nút Book Now.

Người dùng có thể lọc chuyến bay theo số trạm dừng hoặc hãng hàng không.

---

## 3. 👤 Personal Details – Thông tin khách hàng & hành khách

Kiểm thử:

* First Name
* Last Name
* Email
* Mobile
* Address
* Country
* Coupon Code
* Thông tin hành khách.
* Tên hành khách.
* Tuổi.
* Passport Number.
* Nút Confirm This Booking.

Số lượng form Passenger phải tương ứng với số lượng hành khách đã chọn ở màn hình Search.

### Phân loại hành khách

| Loại hành khách |    Độ tuổi |
| --------------- | ---------: |
| Adult           | Từ 12 tuổi |
| Child           |  4–11 tuổi |
| Infant          |   0–3 tuổi |

---

## 4. 💳 Confirm & Payment – Xác nhận và thanh toán

Kiểm thử:

* Booking Summary.
* Invoice.
* Invoice Number.
* Invoice Date.
* Due Date.
* Customer Details.
* Flight Details.
* Deposit.
* Tax & VAT.
* Total Amount.
* Countdown thanh toán.
* Pay on Arrival.
* Pay Now.
* Bank Transfer.
* Credit Card.
* Visa.
* PayPal.
* Trạng thái thanh toán.

Theo yêu cầu, khi thanh toán thành công, trạng thái Invoice thay đổi:

```text
UNPAID → PAID
```

---

# 🔄 Luồng kiểm thử End-to-End

Luồng chính được kiểm thử:

```text
Search
   ↓
Search Results
   ↓
Chọn chuyến bay
   ↓
Personal Details
   ↓
Passenger Information
   ↓
Confirm Booking
   ↓
Invoice
   ↓
Payment
   ↓
Booking Status
```

Luồng End-to-End từ Search đến Payment được xác định trong Test Plan của dự án.

---

# 🧩 Các loại kiểm thử

## Functional Testing

Kiểm tra chức năng hoạt động đúng theo yêu cầu.

Ví dụ:

* Tìm kiếm chuyến bay.
* Lọc chuyến bay.
* Nhập thông tin hành khách.
* Áp dụng Coupon.
* Xác nhận booking.
* Thanh toán.

## Boundary Value Testing

Kiểm tra các giá trị tại giới hạn cho phép.

Ví dụ:

* Số lượng hành khách tối thiểu/tối đa.
* Độ dài trường nhập liệu.
* Độ tuổi hành khách.
* Số thẻ thanh toán.
* Số CVV.

## Negative Testing

Kiểm tra dữ liệu không hợp lệ.

Ví dụ:

* Email sai định dạng.
* Bỏ trống trường bắt buộc.
* Ngày không hợp lệ.
* Số thẻ không đủ ký tự.
* CVV không đủ ký tự.
* Thông tin hành khách không hợp lệ.

## UI Testing

Kiểm tra:

* Giao diện form.
* Màu sắc.
* Ngày giờ.
* Giá tiền.
* Error message.
* Button.
* Cách hiển thị thông tin.

## End-to-End Testing

Kiểm tra toàn bộ quy trình:

```text
Search
→ Chọn chuyến bay
→ Nhập thông tin
→ Confirm
→ Invoice
→ Payment
```

## Regression Testing

Sau khi Developer sửa lỗi, thực hiện kiểm thử lại các Test Case liên quan để đảm bảo chức năng hoạt động đúng và không phát sinh lỗi mới.

Các phương pháp kiểm thử trên được xác định trong Test Plan của dự án.

---

# 🛠️ Môi trường & công cụ kiểm thử

| Hạng mục            | Chi tiết                                                |
| ------------------- | ------------------------------------------------------- |
| Trình duyệt chính   | Google Chrome                                           |
| Trình duyệt bổ sung | Firefox, Edge                                           |
| Môi trường          | Staging / UAT                                           |
| Quản lý Test Case   | Microsoft Excel                                         |
| Bug Tracking        | Jira *(nếu có)*                                         |
| Test Data           | Sân bay mẫu, tài khoản test, dữ liệu thanh toán sandbox |

---

# 📋 Tài liệu của dự án

Dự án bao gồm các tài liệu kiểm thử:

| Tài liệu                                  | Nội dung                      |
| ----------------------------------------- | ----------------------------- |
| `Fly_Booking_Requirements_V6.docx`        | Tài liệu yêu cầu hệ thống     |
| `FB_Requirement_Clarification_Log.xlsx`   | Requirement Clarification Log |
| `FB_Test_Plan.docx`                       | Kế hoạch kiểm thử             |
| `FB_TestCase_Sprint01_v1.1_executed.xlsx` | Test Case & kết quả thực thi  |
| `FB_Bug_Report.xlsx`                      | Báo cáo lỗi                   |
| `FB_Test_Summary_Report.docx`             | Báo cáo tổng kết kiểm thử     |
| `FB_User_Guide.docx`                      | Hướng dẫn sử dụng             |
| `README.md`                               | Tài liệu giới thiệu dự án     |

---

# 🐞 Tổng hợp lỗi

Trong quá trình kiểm thử, phát hiện tổng cộng **6 lỗi**:

| Mức độ    | Số lượng | Bug ID                 |
| --------- | -------: | ---------------------- |
| 🔴 High   |        2 | BUG-01, BUG-06         |
| 🟠 Medium |        3 | BUG-02, BUG-03, BUG-05 |
| 🟢 Low    |        1 | BUG-04                 |
| **Tổng**  |    **6** |                        |

### 🔴 BUG-01 – Kiểm tra ngày về

Hệ thống chưa validate đúng điều kiện **Ngày về phải sau Ngày đi**, có thể tạo ra lịch trình Round Trip không hợp lệ.

### 🔴 BUG-06 – Kiểm tra thẻ hết hạn

Hệ thống chưa validate thẻ thanh toán đã hết hạn, có thể gây lỗi khi thực hiện giao dịch thanh toán thực tế.

Hai lỗi trên được đánh giá là **High Severity** và cần ưu tiên xử lý trước khi release.

---

# 📊 Kết quả kiểm thử

| Chỉ số                               |    Kết quả |
| ------------------------------------ | ---------: |
| Tổng số Test Case                    |     **51** |
| Pass                                 |     **44** |
| Fail                                 |      **6** |
| Untested                             |      **1** |
| Test Coverage                        | **98.04%** |
| Pass Rate trên Test Case đã thực thi |  **88.0%** |

### Kết quả theo từng màn hình

| Màn hình          | Test Case |   Pass |  Fail | Untested |
| ----------------- | --------: | -----: | ----: | -------: |
| Search            |        18 |     16 |     1 |        1 |
| Search Results    |         7 |      6 |     1 |        0 |
| Personal Details  |        12 |     10 |     2 |        0 |
| Confirm & Payment |        14 |     12 |     2 |        0 |
| **Tổng**          |    **51** | **44** | **6** |    **1** |

---

# 🔍 Các vấn đề chính phát hiện

Các lỗi trong quá trình kiểm thử tập trung chủ yếu vào:

* Validation dữ liệu đầu vào.
* Logic ngày tháng.
* Điều kiện biên về số lượng hành khách.
* Validation thông tin thẻ thanh toán.
* Business Logic.
* Các trường hợp dữ liệu không hợp lệ.

Luồng chính của hệ thống gồm tìm kiếm chuyến bay, đặt vé, xem Invoice và thanh toán với dữ liệu hợp lệ hoạt động tương đối tốt theo Specification.

---

# 🚦 Đánh giá & đề xuất Release

### ❌ Chưa nên Release

Dựa trên kết quả kiểm thử, hệ thống **chưa nên release** cho đến khi:

1. Fix **BUG-01 – High**.
2. Fix **BUG-06 – High**.
3. Retest các lỗi đã fix.
4. Thực hiện Regression Testing các chức năng liên quan.

Đặc biệt cần Regression Test lại:

* Search – Date Validation.
* Search – Passenger Quantity.
* Payment.

---

# 📅 Kế hoạch thực hiện

| Giai đoạn                       | Công việc                                    | Thời gian |
| ------------------------------- | -------------------------------------------- | --------- |
| 1. Phân tích yêu cầu            | Đọc Specification, Requirement Clarification | Ngày 1    |
| 2. Lập kế hoạch & thiết kế Test | Test Plan, Test Case, Test Data              | Ngày 2–3  |
| 3. Thực thi Test                | Chạy Test Case trên Staging                  | Ngày 4–5  |
| 4. Báo cáo & Log Bug            | Bug Report, theo dõi Fix, Retest             | Ngày 5–6  |
| 5. Tổng kết                     | Test Summary Report, User Guide              | Ngày 6    |

---

# 👩‍💻 Vai trò & công việc thực hiện

**Vai trò:** Manual Tester / QA

Các công việc thực hiện trong dự án:

* Phân tích tài liệu yêu cầu.
* Xác định Test Scenario.
* Làm rõ các yêu cầu chưa rõ ràng.
* Lập Test Plan.
* Thiết kế Test Case.
* Chuẩn bị Test Data.
* Thực thi Test Case.
* Kiểm thử Functional.
* Kiểm thử Boundary Value.
* Kiểm thử Negative.
* Kiểm thử UI.
* Kiểm thử End-to-End.
* Kiểm thử Regression.
* Ghi nhận và phân loại Bug.
* Theo dõi kết quả Fix Bug.
* Retest.
* Tổng hợp Test Result.
* Lập Test Summary Report.
* Viết User Guide.

---

# 📚 Kỹ năng đạt được

### Software Testing

* Manual Testing
* Requirement Analysis
* Requirement Clarification
* Test Scenario
* Test Case Design
* Test Execution
* Functional Testing
* Negative Testing
* Boundary Value Testing
* UI Testing
* End-to-End Testing
* Regression Testing
* Bug Reporting
* Defect Classification
* Test Reporting

### Documentation

* Test Plan
* Test Case
* Bug Report
* Requirement Clarification Log
* Test Summary Report
* User Guide

### Tools

* Microsoft Excel
* Google Chrome
* Firefox
* Microsoft Edge
* Jira *(nếu có sử dụng)*

---

# 📁 Cấu trúc thư mục GitHub

```text
fly-booking-testing/
│
├── requirements/
│   └── Fly_Booking_Requirements_V6.docx
│
├── test-plan/
│   └── FB_Test_Plan.docx
│
├── test-cases/
│   └── FB_TestCase_Sprint01_v1.1_executed.xlsx
│
├── requirement-clarification/
│   └── FB_Requirement_Clarification_Log.xlsx
│
├── bug-report/
│   └── FB_Bug_Report.xlsx
│
├── test-summary/
│   └── FB_Test_Summary_Report.docx
│
├── user-guide/
│   └── FB_User_Guide.docx
│
└── README.md
```

---

# 🔄 Quy trình kiểm thử

Dự án mô phỏng một quy trình Manual Testing tương đối đầy đủ:

```text
Requirements
      ↓
Requirement Clarification
      ↓
Test Plan
      ↓
Test Case Design
      ↓
Test Execution
      ↓
Bug Report
      ↓
Retest / Regression
      ↓
Test Summary Report
      ↓
Release Recommendation
```

Kết quả cuối cùng đạt **98.04% Test Coverage**, với **51 Test Case**, phát hiện **6 Bug**, trong đó có **2 Bug High Severity** cần ưu tiên xử lý trước Release.

---

# 🎯 Mục đích sử dụng Project

Project phù hợp để xây dựng Portfolio và ứng tuyển các vị trí:

* **Manual Tester**
* **Software Tester**
* **QA Tester**
* **Junior Tester**
* **QA Intern**
* **Manual QA Intern**

---

# 👤 Tác giả

**Nguyễn Thị Tuyết Nhi**

**Vai trò:** Manual Tester / QA

**Dự án:** Fly Booking System – Software Testing Project

---

> 📌 **Lưu ý:** Phạm vi dự án tập trung vào Functional Testing, UI Testing và kiểm thử luồng nghiệp vụ. Performance Testing, Penetration Testing, tích hợp thanh toán thực tế và Responsive Testing trên Mobile nằm ngoài phạm vi kiểm thử được xác định.
