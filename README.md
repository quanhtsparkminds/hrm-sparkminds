# HRM SYSTEM - PROJECT PLAN (DỰ ÁN HỌC JAVA SPRING BOOT)

## 🎯 Mục tiêu dự án

| Mục            | Nội dung                                               |
| -------------- | ------------------------------------------------------ |
| **Tên dự án**  | HRM System (Demo Learning Project)                     |
| **Mục đích**   | Học và nắm vững Java Spring Boot qua dự án thực tế     |
| **Thời gian**  | 2 tháng (8 tuần)                                       |
| **Ngày demo**  | **20-24/04/2026** (DEMO TOÀN BỘ HỆ THỐNG)              |
| **Tech stack** | Java Spring Boot + Flutter                             |
| **Focus**      | Chức năng hoạt động tốt + Demo ấn tượng cho Leadership |

---

## 🎓 Kiến thức Java Spring Boot sẽ học qua dự án

### Core Java & Spring Boot Concepts

- **Spring Boot Fundamentals**: Auto-configuration, Application properties, Profiles
- **Dependency Injection & IoC**: @Autowired, @Component, @Service, @Repository
- **Spring MVC**: Controllers, RequestMapping, RestController
- **Spring Data JPA**: Entities, Repositories, Relationships, Queries
- **Spring Security**: Authentication, Authorization, JWT, Filters
- **Exception Handling**: @ControllerAdvice, Custom exceptions
- **Validation**: @Valid, Custom validators
- **File Upload/Download**: MultipartFile handling
- **Email Service**: JavaMail integration
- **Scheduling**: @Scheduled tasks
- **Logging**: SLF4J, Logback

### Database & JPA

- **Entity Design**: @Entity, @Table, @Column
- **Relationships**: @OneToMany, @ManyToOne, @ManyToMany
- **Cascade Types**: CascadeType.ALL, PERSIST, MERGE
- **Fetch Types**: LAZY vs EAGER loading
- **JPQL**: Custom queries với @Query
- **Pagination**: Pageable, Page
- **Transactions**: @Transactional

### Advanced Topics

- **DTOs & Mappers**: ModelMapper, Manual mapping
- **API Documentation**: Swagger/OpenAPI integration
- **CORS Configuration**: Cross-origin setup
- **Environment Management**: application-dev.yml, application-prod.yml
- **File Storage**: Local storage, AWS S3 integration
- **PDF Generation**: iText, JasperReports
- **Excel Export**: Apache POI

---

## 📅 Timeline Chi Tiết (Học + Code + Demo)

## THÁNG 1: HỌC CƠ BẢN + XÂY DỰNG CORE FEATURES

### 🔵 Tuần 1 (Ngày 1-7): Setup & Authentication

**Mục tiêu học tập**: Spring Boot basics, Spring Security, JWT

#### Backend - Kiến thức học

- ✅ Setup project với Spring Initializr
- ✅ Hiểu Spring Boot auto-configuration
- ✅ Database configuration (PostgreSQL)
- ✅ Spring Security architecture
- ✅ JWT token generation & validation
- ✅ Password encoding với BCrypt

#### Backend - Code implementation

```
✅ User Entity (id, email, password, role, status)
✅ UserRepository extends JpaRepository
✅ UserService (business logic)
✅ AuthController (login, register, forgot password)
✅ JwtTokenProvider (generate & validate JWT)
✅ SecurityConfig (configure HTTP security)
✅ Email service (reset password link)
```

#### Mobile Tasks

- ✅ Setup Flutter project + GetX
- ✅ Login/Register/Forgot Password UI
- ✅ API integration với Dio
- ✅ Token storage với SharedPreferences

#### 🎯 Demo Checkpoint 1 (Ngày 7)

**Show Leader**: Working authentication system

- Live demo: Register → Login → Get JWT token
- Show Swagger API documentation
- Mobile app login flow
- **Kiến thức showcase**: Spring Security, JWT, REST API

---

### 🔵 Tuần 2 (Ngày 8-14): User Management & Profile

**Mục tiêu học tập**: JPA Relationships, Role-based Access Control, File Upload

#### Backend - Kiến thức học

- ✅ Entity relationships (@OneToMany, @ManyToOne)
- ✅ Role-based authorization (@PreAuthorize)
- ✅ Custom exception handling
- ✅ DTO pattern
- ✅ MultipartFile upload
- ✅ Image storage & serving

#### Backend - Code implementation

```
✅ Employee Entity (extends User, có fields: fullName, phone, address, avatar, department, position, hireDate)
✅ Department Entity
✅ Position Entity
✅ Relationships: Employee ↔ Department, Employee ↔ Position
✅ EmployeeRepository với custom queries
✅ EmployeeService (CRUD operations)
✅ EmployeeController (@PreAuthorize("hasRole('MANAGER')"))
✅ FileStorageService (save/load files)
✅ ProfileController (update profile, change password)
```

#### Mobile Tasks

- ✅ Profile screen với image picker
- ✅ Employee list (Manager only)
- ✅ Add/Edit employee form
- ✅ Role-based UI rendering

---

### 🔵 Tuần 3 (Ngày 15-21): Attendance System

**Mục tiêu học tập**: Complex business logic, Date/Time handling, Aggregation queries

#### Backend - Kiến thức học

- ✅ LocalDateTime handling
- ✅ Business logic trong Service layer
- ✅ @Scheduled tasks (auto check-out)
- ✅ Aggregate functions (COUNT, SUM)
- ✅ Custom JPQL queries
- ✅ @Transactional management

#### Backend - Code implementation

```
✅ Attendance Entity (employee, checkIn, checkOut, workDate, status, location, notes)
✅ AttendanceRepository với custom queries:
   - findByEmployeeAndDateRange
   - calculateMonthlyWorkHours
   - findLateAttendances
✅ AttendanceService:
   - checkInRemote(employeeId, location)
   - checkOutRemote(employeeId)
   - autoCheckOut() - @Scheduled
   - calculateWorkHours()
   - detectLateArrival()
✅ AttendanceController
✅ AttendanceStatisticsService (monthly reports)
```

#### Mobile Tasks

- ✅ Check-in/Check-out remote trên app
- ✅ Attendance history với Calendar view
- ✅ Real-time work hours display
- ✅ Manager: View all attendance, Edit attendance

---

### 🔵 Tuần 4 (Ngày 22-28): Leave Management

**Mục tiêu học tập**: Workflow management, Notifications, Enums

#### Backend - Kiến thức học

- ✅ Enum types trong JPA
- ✅ Workflow state management
- ✅ Email templates
- ✅ Async processing (@Async)
- ✅ Query methods với specifications

#### Backend - Code implementation

```
✅ LeaveRequest Entity (employee, leaveType, startDate, endDate, reason, status, approvedBy, approvedDate)
✅ LeaveType Enum (ANNUAL, SICK, UNPAID, MATERNITY, etc.)
✅ LeaveStatus Enum (PENDING, APPROVED, REJECTED)
✅ LeaveBalance Entity (employee, year, totalDays, usedDays, remainingDays)
✅ LeaveRequestService:
   - createLeaveRequest()
   - approve/reject()
   - calculateLeaveBalance()
   - checkOverlap()
✅ NotificationService (send email)
✅ LeaveRequestController
```

#### Mobile Tasks

- ✅ Create leave request form
- ✅ Leave history với status colors
- ✅ Manager: Approve/Reject interface
- ✅ Push notifications
- ✅ Leave balance widget

---

## THÁNG 2: ADVANCED FEATURES + DEMO PREPARATION

### 🔵 Tuần 5 (Ngày 29-35): Payroll System

**Mục tiêu làm**: Complex calculations, PDF generation, Integration

#### Backend - Kiến thức học

- ✅ PDF generation với iText/JasperReports
- ✅ Complex calculations trong Service
- ✅ Integration giữa modules
- ✅ @Transactional với multiple operations

#### Backend - Code implementation

```
✅ Salary Entity (employee, month, year, baseSalary, allowances, deductions, netSalary, status, paidDate)
✅ SalaryComponent Entity (type, amount, description)
✅ SalaryService:
   - calculateSalary(employeeId, month, year)
   - integrate với Attendance (work days)
   - integrate với LeaveRequest (unpaid leaves)
   - applyDeductions (late, absent)
   - applyBonuses (overtime)
✅ PdfService (generate salary slip PDF)
✅ SalaryController
```

#### Mobile Tasks

- ✅ Salary slip screen (beautiful design)
- ✅ Salary breakdown (base, allowances, deductions)
- ✅ Download PDF button
- ✅ Manager: Payroll management, Bulk salary generation

#### 🎯 Demo Checkpoint 5 (Ngày 35)

### 🔵 Tuần 6 (Ngày 36-42): Dashboard & Reports

**Mục tiêu làm**: Data aggregation, Analytics, Excel export

#### Backend - Kiến thức học

- ✅ Complex aggregation queries
- ✅ Native queries với @Query
- ✅ Excel generation với Apache POI
- ✅ DTO projections
- ✅ Caching strategies

#### Backend - Code implementation

```
✅ DashboardService:
   - getTotalEmployees()
   - getPendingLeaveRequests()
   - getMonthlyAttendanceRate()
   - getPayrollSummary()
   - getTopPerformers()
✅ ReportService:
   - generateAttendanceReport(month, year)
   - generateLeaveReport()
   - generatePayrollReport()
✅ ExcelExportService (Apache POI)
✅ ChartDataController (data for charts)
✅ ReportController (download Excel/PDF)
```

#### Mobile Tasks

- ✅ Dashboard screen với charts (fl_chart)
- ✅ KPIs cards (Total employees, Attendance rate, etc.)
- ✅ Interactive charts
- ✅ Export reports button

### 🔵 Tuần 7 (Ngày 43-49): Notifications & Polish

**Mục tiêu làm**: Real-time features, Push notifications, Code optimization

#### Backend - Code implementation

```
✅ Notification Entity (user, title, content, type, isRead, createdDate)
✅ NotificationService với Firebase Cloud Messaging
✅ NotificationController
✅ Optimize queries (indexing, N+1 problem)
✅ Add audit fields (createdBy, createdDate, modifiedBy, modifiedDate)
✅ API response standardization
✅ Global exception handler improvement
```

#### Mobile Tasks

- ✅ Notification center
- ✅ Push notification handling
- ✅ UI/UX polish
- ✅ Dark mode
- ✅ Loading states
- ✅ Error handling

---

### 🔵 Tuần 8-9 (Ngày 50-60): DEMO PREPARATION & FINAL POLISH

#### Week Focus: CHUẨN BỊ DEMO HOÀN CHỈNH

**Mấy ngày trước demo: Testing & Bug Fixes**

- Tạo slide thuyết trình
- Code presentation

## ✅ Final Checklist

### Code Quality

- [ ] Code clean & well-commented
- [ ] Consistent naming conventions
- [ ] No hardcoded values
- [ ] Proper error handling
- [ ] Security best practices

### Features

- [ ] Authentication (Login, Register, Forgot Password)
- [ ] User Management (CRUD)
- [ ] Attendance (Check-in/out, History)
- [ ] Leave Management (Request, Approve/Reject)
- [ ] Payroll (Calculate, View, PDF)
- [ ] Dashboard (Charts, Statistics)
- [ ] Notifications (Email, Push)
- [ ] Reports (Excel, PDF)

### Documentation

- [ ] README.md complete
- [ ] API documentation (Swagger)
- [ ] Architecture diagram
- [ ] Setup guide
- [ ] Demo script

### Demo

- [ ] Demo data seeded
- [ ] Demo accounts created
- [ ] All features tested
- [ ] Backup plan prepared
- [ ] Presentation slides ready

---
