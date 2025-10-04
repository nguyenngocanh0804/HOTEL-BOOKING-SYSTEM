# HOTEL-BOOKING-SYSTEM
LINK JIRA:https://student-team-dycpkdi5.atlassian.net/jira/software/projects/ANH123/boards/37  
Hotel Booking System – Lab 02
Mục tiêu dự án

Dự án Hotel Booking System nhằm mục đích:

Giúp sinh viên học cách phân tích yêu cầu và thiết kế hệ thống quản lý đặt phòng khách sạn.

Áp dụng UML (Use Case, Sequence Diagram) để mô tả chức năng và luồng nghiệp vụ.

Thiết kế cơ sở dữ liệu (ERD) với các quan hệ rõ ràng giữa các thực thể.

Triển khai quy trình Agile-Scrum trên Jira, đồng bộ với GitHub để quản lý tiến độ và code.

1. Thiết kế Mini Project
1.1 Các bảng dữ liệu chính (Entities)
Entity	Thuộc tính	Mối quan hệ
Guest	GuestID, Name, Phone, Email, Address	1 Guest – N Reservation
RoomType	TypeID, Name, Price, Capacity, Description	1 RoomType – N Room
Room	RoomID, TypeID, Status, Floor	1 Room – N Reservation
Reservation	ResvID, GuestID, RoomID, StaffID, CheckInDate, CheckOutDate, Status	1 Reservation – N Payment
Payment	PaymentID, ResvID, Amount, Method, Status, Date	N Payment – 1 Reservation
Staff	StaffID, Name, Role, Username, PasswordHash	1 Staff – N Reservation

Mối quan hệ tổng quan:

Guest 1–N Reservation

Reservation 1–N Payment

RoomType 1–N Room

Room 1–N Reservation

Staff 1–N Reservation (lễ tân quản lý)

1.2 Use Case UML

Actors (Tác nhân):

Guest (Khách hàng)

Receptionist (Lễ tân)

Manager (Quản lý)

Payment Gateway

Housekeeping (Buồng phòng)

Use Case chính:

Tìm phòng & Xem chi tiết phòng

Đặt phòng online (Booking)

Thanh toán online

Check-in / Check-out

Quản lý phòng & giá (Manager)

Quản lý đặt phòng (Receptionist)

Công việc buồng phòng (Housekeeping)

Báo cáo doanh thu (Manager)

(Biểu đồ Use Case vẽ bằng PlantUML hoặc draw.io và upload lên GitHub)

1.3 Sequence Diagram

a) Luồng Đặt phòng online:

Guest chọn phòng → Hệ thống giữ phòng (hold)

Guest nhập thông tin → Thực hiện thanh toán

Cổng thanh toán trả kết quả → Xác nhận & gửi email

b) Luồng Check-in / Check-out (Lễ tân):

Receptionist tra cứu mã đặt phòng

Check-in: gán phòng thực tế, cập nhật trạng thái

Check-out: tổng hợp chi phí, thu tiền, cập nhật buồng phòng

(Vẽ Sequence Diagram bằng PlantUML hoặc draw.io)

1.4 Thiết kế cơ sở dữ liệu (ERD)

Bảng và thuộc tính:

Guest(GuestID, Name, Phone, Email, Address)

RoomType(TypeID, Name, Price, Capacity, Description)

Room(RoomID, TypeID, Status, Floor)

Reservation(ResvID, GuestID, RoomID, StaffID, CheckInDate, CheckOutDate, Status)

Payment(PaymentID, ResvID, Amount, Method, Status, Date)

Staff(StaffID, Name, Role, Username, PasswordHash)

Yêu cầu ERD:

Thể hiện quan hệ 1–N, PK, FK rõ ràng giữa các bảng.

2. Triển khai Agile-Scrum trên Jira
2.1 Product Backlog (ví dụ)

Đăng ký / Đăng nhập khách hàng

Tìm phòng & Xem chi tiết phòng

Đặt phòng & Thanh toán online

Check-in / Check-out (Receptionist)

Quản lý phòng & giá (Manager)

Báo cáo doanh thu

Công việc buồng phòng (Housekeeping)

2.2 Sprint Plan
Sprint	Mục tiêu	User Stories chính
Sprint 1	Auth, Tìm phòng, Xem chi tiết phòng	Register/Login, Search & View Room Details
Sprint 2	Đặt phòng & giữ chỗ	Hold Room, Confirm Booking, Receptionist Views
Sprint 3	Thanh toán & Check-in/out	Online Payment, Check-in Guest, Check-out Guest
Sprint 4	Báo cáo, Housekeeping, Release	Revenue Reports, Housekeeping Tasks, Adjust Room Prices
2.3 Board Workflow
To Do → In Progress → Code Review → Testing → Done


Các card (user story) được di chuyển theo tiến độ phát triển.

Smart Commit từ GitHub có thể cập nhật trạng thái tự động trên Jira.

2.4 User Story Format
As a [role], I want [function], so that [benefit].


Ví dụ:

As a Guest, I want to search rooms, so that I can find available options for my stay.
As a Receptionist, I want to check-in a guest, so that I can assign a room efficiently.

3. Đồng bộ GitHub với Jira

Mỗi commit nên gắn Issue Key, ví dụ:

#HB-101 Add: Booking use case diagram


Tên branch nên chứa Issue Key:

feature/HB-101-booking-usecase


Pull request liên kết với issue → Jira tự động hiển thị commit và PR trong panel Development.
