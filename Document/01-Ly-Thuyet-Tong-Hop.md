# 📖 Tổng Hợp Lý Thuyết BPM (Lecture 1 → Lecture 12)

> Giáo trình gốc: *Fundamentals of Business Process Management (2nd ed.)* — Dumas, La Rosa, Mendling & Reijers (Marlon Dumas, University of Tartu).  
> [⬅️ Quay lại Trang chủ Ôn thi](./README.md)

---

## Mục lục
1. [Lecture 1: Giới thiệu BPM (Introduction)](#lecture-1-giới-thiệu-bpm-introduction)
2. [Lecture 2: Xác định Quy trình (Process Identification)](#lecture-2-xác-định-quy-trình-process-identification)
3. [Lecture 3: Mô hình hóa BPMN Cơ bản (Process Modeling 1)](#lecture-3-mô-hình-hóa-bpmn-cơ-bản-process-modeling-1)
4. [Lecture 4: Mô hình hóa BPMN Nâng cao (Process Modeling 2)](#lecture-4-mô-hình-hóa-bpmn-nâng-cao-process-modeling-2)
5. [Lecture 5: Phân tích Quy trình Định tính (Qualitative Analysis)](#lecture-5-phân-tích-quy-trình-định-tính-qualitative-analysis)
6. [Lecture 6: Phân tích Quy trình Định lượng 1 — Flow Analysis](#lecture-6-phân-tích-quy-trình-định-lượng-1--flow-analysis)
7. [Lecture 7: Phân tích Quy trình Định lượng 2 — Queuing & Simulation](#lecture-7-phân-tích-quy-trình-định-lượng-2--queuing--simulation)
8. [Lecture 8: Tái thiết kế Quy trình 1 — BPR](#lecture-8-tái-thiết-kế-quy-trình-1--bpr)
9. [Lecture 9: Tái thiết kế Quy trình 2 — Heuristic Redesign](#lecture-9-tái-thiết-kế-quy-trình-2--heuristic-redesign)
10. [Lecture 10: Tự động hóa Quy trình (Process Automation)](#lecture-10-tự-động-hóa-quy-trình-process-automation)
11. [Lecture 12: Giám sát & Khai phá Quy trình (Monitoring & Process Mining)](#lecture-12-giám-sát--khai-phá-quy-trình-monitoring--process-mining)

---

## Lecture 1: Giới thiệu BPM (Introduction)

### 1.1. Quy trình nghiệp vụ (Business Process) là gì?
- Là một **chuỗi các sự kiện (events), hoạt động (activities) và quyết định (decisions)** liên quan đến nhiều tác nhân (actors) và đối tượng (objects), được kích hoạt bởi một nhu cầu và dẫn đến một **kết quả mang lại giá trị cho khách hàng** (positive outcome / value-adding; hoặc negative outcome nếu thất bại).
- **4 quy trình kinh điển:**
  - `Order-to-Cash` (Đặt hàng → Thu tiền)
  - `Procure-to-Pay` / `Purchase-to-Pay` (Mua sắm → Thanh toán)
  - `Application-to-Approval` (Nộp đơn → Phê duyệt)
  - `Issue-to-Resolution` (Sự cố/Khiếu nại → Giải quyết)

> [!WARNING]
> **Phân biệt Quy trình (Process) vs Chức năng (Function):**  
> *Human Resource Management*, *CRM*, *Accounts Payable* là **Chức năng/Phòng ban** (Function), KHÔNG phải quy trình cốt lõi. *Order-to-Cash*, *Bill-to-Cash* mới là **Quy trình** (vắt ngang nhiều phòng ban).

### 1.2. Quản lý Quy trình Nghiệp vụ (BPM) & 3 Chiều Hiệu suất
- **BPM:** Tập hợp các nguyên lý, phương pháp và công cụ để thiết kế, phân tích, thực thi và giám sát quy trình nhằm **cải thiện hiệu suất**.
- **3 chiều hiệu suất (Faster – Cheaper – Better):**
  1. **Time (Thời gian):** Cycle time, Waiting time...
  2. **Cost (Chi phí):** Chi phí xử lý, chi phí sai lỗi (lỗi tính thiếu & lỗi tính thừa hóa đơn đều gây chi phí vì phát sinh khiếu nại), chi phí lãi vay do thu tiền chậm (Cycle time dài).
  3. **Quality (Chất lượng):** Tỷ lệ lỗi (defect rate), tỷ lệ giao đúng hạn, mức độ hài lòng khách hàng.
- **Quy tắc Bill Gates:** Tự động hóa một quy trình hiệu quả sẽ khuếch đại hiệu quả; tự động hóa một quy trình kém hiệu quả sẽ **khuếch đại sự kém hiệu quả** (IT + Process Change → Business Value).

### 1.3. Các vai trò trong tổ chức định hướng quy trình
| Vai trò | Trách nhiệm chính | Chịu trách nhiệm trực tiếp khi quy trình kém? |
| :--- | :--- | :---: |
| **Process Owner** (Chủ sở hữu quy trình) | Chịu trách nhiệm vận hành và cải tiến toàn bộ một quy trình cụ thể | **CÓ (Trực tiếp chịu trách nhiệm giải trình)** |
| **Process Participants** | Nhân viên trực tiếp thực hiện các tác vụ trong quy trình | Không (chỉ chia sẻ trách nhiệm) |
| **Executive Management** | Giám sát tổng thể toàn doanh nghiệp | Không (ủy quyền cho Process Owner) |
| **Process Analyst / BPM Group** | Hỗ trợ phân tích, mô hình hóa, tư vấn cải tiến | Không (chỉ đóng vai trò hỗ trợ) |

---

## Lecture 2: Xác định Quy trình (Process Identification)

Gồm **2 bước chính** (Davenport, 1993):
1. **Designation (Chỉ định / Liệt kê & Phân phạm vi)** → Đầu ra: **Process Architecture** (Kiến trúc quy trình).
2. **Prioritization (Ưu tiên / Chọn quy trình)** → Đầu ra: **Prioritized Process Portfolio**.

### 2.1. Phân loại 3 nhóm quy trình (Michael Porter, 1985)
| Loại quy trình | Định nghĩa | Ví dụ |
| :--- | :--- | :--- |
| **Core Processes** (Cốt lõi) | Tạo ra giá trị **trực tiếp cho khách hàng bên ngoài** | Sales (`Order-to-Cash`), Direct procurement, Distribution, Service, `Bill-to-cash` & `Infrastructure inspection` (công ty cấp nước), Giảng dạy (đại học) |
| **Support Processes** (Hỗ trợ) | Cung cấp **nguồn lực** cho các quy trình khác vận hành | HR, IT, Finance/Accounting, Indirect procurement (mua văn phòng phẩm/MRO) |
| **Management Processes** (Quản trị) | Đưa ra **định hướng, quy tắc, chính sách, kiểm soát** | Strategic management, Risk management, Suppliers management, Curriculum management |

### 2.2. Scoping & Value Chain (Chuỗi giá trị)
- **3 chiều quan hệ:**
  - **Specialization (Chuyên biệt hóa):** Tổng quát – Chuyên biệt (VD: Stocked vs MTO vs ETO).
  - **Horizontal (Ngang):** Thượng nguồn – Hạ nguồn trong **Value Chain** (thường 3–7 quy trình; tư duy: *Imagine it → Build it → Sell it*).
  - **Vertical (Dọc):** Phân cấp từ cao xuống thấp:
    - **Level 1:** Process Landscape / Value Chains.
    - **Level 2:** Main / Root Processes (VD: Lead-to-quote, Order-to-cash).
    - **Level 3+:** Sub-processes → Atomic Tasks (vẽ bằng BPMN).
- **4 quy tắc xác định ranh giới ngang (Horizontal boundaries):** Thay đổi về (1) Đối tượng kinh doanh chính, (2) Mức độ chi tiết (granularity), (3) Tần suất/thời gian, (4) Kết quả/mục tiêu trung gian.
- **Reference Models (Mô hình tham chiếu):** ITIL, SCOR, **APQC PCF** (4 cấp: *Category → Process Group → Process → Activity*), COBIT, VRM, eTOM.

### 2.3. Tiêu chí Ưu tiên quy trình (Hammer & Champy, 1993)
1. **Importance (Tầm quan trọng):** Tác động lớn nhất đến mục tiêu chiến lược.
2. **Health / Dysfunction (Sức khỏe / Mức độ trục trặc):** Quy trình nào đang gặp vấn đề nặng nhất.
3. **Feasibility (Tính khả thi):** Mức độ dễ thành công khi cải tiến (văn hóa, chính trị, nguồn lực).  
→ Biểu diễn bằng **Process Portfolio Matrix** hoặc **PICK Chart** (Ưu tiên hành động ngắn hạn: Importance cao + Health kém + Feasibility cao).

---

## Lecture 3: Mô hình hóa BPMN Cơ bản (Process Modeling 1)

### 3.1. 4 Phần tử lõi & Quy ước đặt tên
1. **Activity (Task):** Hình chữ nhật bo góc — Đặt tên: **Động từ + Danh từ** (*Check stock availability, Emit invoice*). Tránh động từ chung chung như *Handle, Record*.
2. **Event:** Hình tròn (Start: viền mảnh, End: viền đậm) — Đặt tên: **Danh từ + Phân từ quá khứ** (*Purchase order received, Order fulfilled*).
3. **Gateway:** Hình thoi — Điều phối luồng token. Nhánh đi ra từ **XOR-split** phải ghi **điều kiện** (*Items in stock / Items not in stock*).
4. **Sequence Flow:** Mũi tên liền nét biểu thị thứ tự thực thi.

### 3.2. Token Game & 3 loại Gateway cơ bản
| Gateway | Ký hiệu | Split (Tách luồng) | Join (Gộp luồng) |
| :--- | :---: | :--- | :--- |
| **XOR (Exclusive)** | `X` | Chọn **đúng 1** nhánh dựa trên điều kiện | Đẩy tiếp **mỗi token** nhận được từ **bất kỳ** nhánh vào nào ("dumb" gateway) |
| **AND (Parallel)** | `+` | Kích hoạt **tất cả** các nhánh song song | Chờ **tất cả** các nhánh vào đều có token rồi mới đi tiếp (đồng bộ) |
| **OR (Inclusive)** | `O` | Chọn **1 hoặc nhiều** nhánh ($n$ trong $m$) tùy điều kiện | Chờ tất cả các nhánh vào **đang hoạt động (active)** hoàn tất |

> [!CAUTION]
> **Implicit vs Explicit Gateways (Cực hay ra thi!):**
> - 1 Task có **≥ 2 cung đi ra** ⟺ tương đương **AND-split**.
> - 1 Task có **≥ 2 cung đi vào** ⟺ tương đương **XOR-join**.
> - **Rework Loop (Vòng lặp làm lại):** Điểm vào vòng lặp là **XOR-join**, điểm ra vòng lặp là **XOR-split**.
> - **Lỗi kinh điển (Deadlock / Lack of Synchronization):**
>   - Tách bằng `XOR-split` mà gộp bằng `AND-join` → **Deadlock** (kẹt vĩnh viễn vì không bao giờ đủ token ở mọi nhánh).
>   - Tách bằng `AND-split` mà gộp bằng `XOR-join` → **Lack of synchronization** (tạo ra nhiều token chạy trùng lặp các bước phía sau).
>   - Nhánh song song có xen vòng lặp quay lại 1 nhánh → Cổng gộp cuối phải là **OR-join** (không dùng AND-join).

### 3.3. Pools, Lanes, Message Flow & Artifacts
- **Pool:** Đại diện cho một **thực thể/tổ chức độc lập** (*Customer, Company, Subcontractor*).
  - *White-box pool:* Hiển thị chi tiết quy trình bên trong.
  - *Black-box pool:* Chỉ vẽ khung tên bên ngoài (ẩn chi tiết).
- **Lane:** Phân chia bên trong 1 Pool thành **phòng ban, vai trò, hệ thống** (*Sales, Finance, ERP*).
- **3 quy tắc cú pháp bắt buộc:**
  1. **Sequence Flow** KHÔNG ĐƯỢC vượt qua ranh giới Pool (nhưng được vượt qua Lane).
  2. **Message Flow** (mũi tên nét đứt, đầu tròn rỗng) CHỈ nối giữa **2 Pool khác nhau** (có thể nối tới biên Pool hoặc tới Task/Event bên trong Pool).
  3. **Message Flow** KHÔNG ĐƯỢC nối 2 phần tử trong **cùng một Pool**.
- **Data Object vs Data Store:**
  - **Data Object:** Tài liệu/dữ liệu được tạo ra hoặc dùng trong 1 instance (*Shopping cart, Invoice, Purchase order [approved]*).
  - **Data Store:** Kho lưu trữ **bền vững** tồn tại lâu hơn vòng đời 1 instance (*CRM system, Product catalog, Orders DB*).
- **Text Annotation:** Ghi chú giải thích, không ảnh hưởng luồng token.

---

## Lecture 4: Mô hình hóa BPMN Nâng cao (Process Modeling 2)

### 4.1. Sub-processes (Quy trình con)
**3 lý do sử dụng Sub-process:**
1. **Giảm độ phức tạp:** Khi mô hình quá lớn khó hiểu/bảo trì (Multi-level modeling: Level 1 Value Chain → Level 2+ mở rộng chi tiết).
2. **Tránh dư thừa (Redundancy):** Tái sử dụng các đoạn quy trình chung giữa nhiều mô hình khác nhau.
3. **Khoanh vùng phạm vi:** Để áp dụng **lặp lại (Repetition)** hoặc **ngắt ngoại lệ (Interruption)** cho cả một nhóm hoạt động.
*(Lưu ý: Sub-process KHÔNG giảm số cung cắt nhau và KHÔNG giảm số End Events).*

### 4.2. Lặp lại (Repetition Markers)
- **Activity Loop Marker** (mũi tên xoay tròn `↺`): Lặp tuần tự (structured cycle) cho đến khi thỏa *completion condition*.
- **Parallel Multi-Instance Marker** (`|||`): Thực hiện song song nhiều bản sao cho từng phần tử trong tập dữ liệu (VD: gửi yêu cầu báo giá đến 5 nhà cung cấp cùng lúc).

### 4.3. Events (Sự kiện) & Event-Based Gateway
| Loại sự kiện | Start | Intermediate Catching | Intermediate Throwing | End |
| :--- | :---: | :---: | :---: | :---: |
| **Untyped (None)** | Khởi tạo không rõ nguyên nhân | — | — | Kết thúc bình thường |
| **Message (Phong bì)** | Nhận tin nhắn → tạo instance | Chờ nhận tin nhắn | Gửi tin nhắn giữa quy trình | Gửi tin nhắn & kết thúc |
| **Timer (Đồng hồ)** | Chạy theo lịch (VD: 6pm thứ 6) | Chờ đến mốc giờ / độ trễ (delay) | — | — |
| **Error (Tia sét)** | — | **Bắt lỗi (chỉ gắn trên biên / Boundary)** | — | Ném lỗi nội bộ (cùng tên với Catch) |
| **Signal (Tam giác)** | Nhận tín hiệu broadcast | Bắt tín hiệu (có thể gắn Boundary) | Phát tín hiệu | Phát tín hiệu & kết thúc |
| **Terminate (Chấm đen đậm)** | — | — | — | **Hủy toàn bộ quy trình**, xóa sạch mọi token còn lại |

- **Data-based XOR-split vs Event-based Gateway:**
  - `XOR-split`: Quyết định **ngay lập tức** dựa trên dữ liệu sẵn có.
  - `Event-based Gateway`: Trì hoãn quyết định, chờ **"cuộc đua" giữa các sự kiện** (sự kiện nào đến trước thì đi nhánh đó).
  - **Quy tắc:** Ngay sau Event-based Gateway CHỈ được là **Intermediate Catching Event** (Message, Timer, Signal...) hoặc **Receive Task** (KHÔNG được là Start Event hay Send Task).

### 4.4. Xử lý Ngoại lệ (Boundary Events)
- **Boundary Event** luôn là **Intermediate Catching Event** gắn lên viền của Task hoặc Sub-process (KHÔNG bao giờ dùng End Event):
  - **External exception:** Boundary **Message** event (VD: khách hàng gửi yêu cầu hủy/đổi PO).
  - **Internal exception:** Boundary **Error** event — bắt lỗi từ End Error Event **cùng tên** ném ra từ *bên trong* Sub-process đó.
  - **Timeout:** Boundary **Timer** event (VD: quá 48h không xong thì ngắt).
  - **Signal:** Có thể kích hoạt ngắt từ trong quy trình nhưng **bên ngoài** Sub-process đó.
- **Interrupting (Viền nét liền):** Ngắt ngay lập tức hoạt động đang chạy, chuyển sang luồng xử lý ngoại lệ.
- **Non-Interrupting (Viền nét đứt):** Không ngắt luồng chính, tạo thêm luồng song song để xử lý phụ (VD: khách đổi địa chỉ giao hàng).

### 4.5. Choreography (Vũ đạo tương tác)
- Một **Choreography Activity** biểu diễn sự tương tác (trao đổi thông điệp) giữa **2 bên** (có thể 1 chiều hoặc 2 chiều; *Sub-choreography* có thể gồm > 2 bên).
- KHÔNG biểu diễn một đơn vị công việc nội bộ (unit of work).
- **Quy tắc nối tiếp:** Hoạt động B chỉ có thể đứng ngay sau hoạt động A nếu **bên khởi xướng (initiator) của B có tham gia vào A**.

---

## Lecture 5: Phân tích Quy trình Định tính (Qualitative Analysis)

### 5.1. Value-Added Analysis (Phân tích Giá trị Gia tăng)
Tách quy trình thành từng bước nhỏ (trước – trong – sau task) và phân loại:
| Phân loại | Tiêu chí nhận diện | Hành động | Ví dụ |
| :--- | :--- | :---: | :--- |
| **VA (Value-Adding)** | Tạo giá trị trực tiếp cho **khách hàng**; khách sẵn sàng trả tiền | **Maximize** | Giao hàng, xác nhận ngày giao, điều tra & giải quyết khiếu nại, thông báo kết quả cho khách |
| **BVA (Business Value-Adding)** | Cần cho **doanh nghiệp** (thu tiền, giảm rủi ro, tuân thủ luật, kiểm soát nội bộ) | **Minimize** | Kiểm tra tồn kho, đối chiếu thanh toán, nhắc nợ, phê duyệt quản lý, nhập hồ sơ vào hệ thống, yêu cầu báo cáo y tế |
| **NVA (Non-Value-Adding)** | Khách không muốn trả tiền: **chuyển giao (handovers), chờ đợi (waiting), làm lại (rework)** | **Remove** | Chuyển hồ sơ giữa các phòng ban, chờ báo cáo y tế, xử lý hàng trả lại do lỗi nội bộ |

### 5.2. Waste Analysis — 7 Nguồn Lãng Phí (Toyota / Taiichi Ohno)
Nhớ theo **3 nhóm (Move – Hold – Over-do)**:
1. **Move (Di chuyển):**
   - **Transportation:** Gửi/nhận tài liệu, vật tư giữa các bước (kể cả gửi email/chuyển tiếp điện tử).
   - **Motion:** Nhân sự di chuyển vật lý trong nội bộ (VD: đi xin chữ ký các phòng).
2. **Hold (Lưu giữ / Tồn đọng):**
   - **Inventory:** Tồn kho nguyên vật liệu hoặc **Work-in-Process (WIP)** (VD: 3000 hồ sơ đang xử lý cùng lúc).
   - **Waiting:** Chờ tài liệu, chờ người duyệt, hoặc tài nguyên nhàn rỗi chờ việc.
3. **Over-do (Làm thừa / Làm lỗi):**
   - **Defects:** Sai lỗi cần sửa lại / vòng lặp làm lại (rework loops).
   - **Over-processing:** Làm các bước thừa so với kết quả cuối (VD: kiểm tra xác thực rất tốn công cho 100% hồ sơ dù hội đồng loại tới 80%).
   - **Over-production:** Thực hiện cả các quy trình không tạo ra giá trị cuối cùng (VD: làm 50% báo giá nhưng không ra đơn hàng; thuê thiết bị về nhưng không dùng).

### 5.3. Issue Register, Pareto Chart & PICK Chart
- **Issue Register:** Bảng ghi nhận có hệ thống các vấn đề gồm: *ID, Tên ngắn, Mô tả, Giả định/Dữ liệu, Tác động Định tính & Định lượng (Quantitative Impact), Hành động cải tiến*.
- **Kỹ thuật sắp xếp thứ tự ưu tiên (Prioritizing issues):** **Pareto Chart** (quy tắc 80/20) và **Issue Register** (kết hợp **PICK Chart**: Possible, Implement, Challenge, Kill).

### 5.4. Root-Cause Analysis (Phân tích Nguyên nhân Gốc rễ)
- **Why-Why Diagram (5 Whys):** Hỏi "Tại sao?" lặp lại (~5 tầng) để lần ra nguyên nhân sâu xa.
- **Cause-Effect / Fishbone Diagram (Biểu đồ Xương cá — 6Ms):**
  1. **Machine:** Công nghệ, phần mềm, UI kém, thiếu tích hợp hệ thống.
  2. **Method:** Cách thiết kế quy trình, phân công không rõ, thiếu quy chuẩn/giao tiếp.
  3. **Material:** Dữ liệu/nguyên liệu đầu vào thiếu, sai, lỗi thời.
  4. **Man:** Con người (thiếu đào tạo, thiếu động lực, quá tải).
  5. **Measurement:** Ước lượng sai, tính toán nhầm.
  6. **Milieu:** Môi trường bên ngoài (đối tác phản hồi chậm, đột biến lượng việc).

---

## Lecture 6: Phân tích Quy trình Định lượng 1 — Flow Analysis

*(Xem toàn bộ công thức toán học và bài giải chi tiết tại [02-Cong-Thuc-Va-Bai-Tap-Dinh-Luong.md](./02-Cong-Thuc-Va-Bai-Tap-Dinh-Luong.md))*

- **Đo lường Thời gian:** $\text{Cycle Time (CT)} = \text{Processing Time (PT)} + \text{Waiting Time (WT)}$; $\text{CTE} = \frac{\text{PT}}{\text{CT}}$.
- **Đo lường Chi phí:** Per-Instance Cost = Processing Cost + Cost of Waste (gồm Material Cost + Resource Cost).
- **Resource Utilization ($\rho$):** Tỷ lệ thời gian làm việc trên tổng thời gian sẵn có. Khi $\rho > 90\%$, **Waiting Time tăng vọt theo hàm mũ**.
- **Đo lường Chất lượng:** Product quality (Defect rate), Delivery quality (On-time rate, SLA violation rate, CT variance), Customer satisfaction.
  - *Lưu ý:* Số lượng đơn/khiếu nại đầu vào (VD: số khiếu nại hàng tháng) **KHÔNG phải chỉ số hiệu suất**, chỉ là chỉ số đầu vào!
- **Flow Analysis:** Tính CT/PT/Cost cho toàn quy trình từ thông số từng bước qua 4 cấu trúc: **Sequence**, **XOR**, **AND**, **Rework Loop**.
- **2 Hạn chế của Flow Analysis:**
  1. Chỉ áp dụng chuẩn cho mô hình có cấu trúc (block-structured).
  2. **Bỏ qua Arrival Rate ($\lambda$) và tranh chấp tài nguyên (Resource contention)** — không tính được thời gian chờ do xếp hàng.
- **Little's Law:** $WIP = \lambda \cdot CT$ (liên kết lượng việc đang tồn đọng, tốc độ đến và thời gian chu kỳ).

---

## Lecture 7: Phân tích Quy trình Định lượng 2 — Queuing & Simulation

### 7.1. Lý thuyết Hàng đợi (Queuing Analysis)
- Nguyên nhân sinh ra hàng đợi: **Biến thiên (variability)** về khoảng cách thời gian đến (burstiness) và/hoặc thời gian xử lý (job size variation), trầm trọng hơn khi $\rho \to 100\%$.
- **Quá trình Poisson:** Thời gian giữa 2 lần đến tuân theo phân phối **mũ âm (Negative Exponential)** với tính chất **không nhớ (memoryless)**: $P(X > 40 \mid X \ge 30) = P(X > 10)$.
- **Mô hình $M/M/1$ và $M/M/c$:**
  - $\lambda$: tốc độ đến trung bình; $\mu$: tốc độ phục vụ của 1 server; $c$: số server; $\rho = \frac{\lambda}{c\mu}$.
  - Tính được $L_q, L, W_q, W$ (chi tiết công thức ở file 02).

### 7.2. Mô phỏng Quy trình (Business Process Simulation)
- **5 thành phần của một Simulation Scenario:**
  1. Thời gian xử lý từng hoạt động (Fixed / Normal / Exponential).
  2. Xác suất rẽ nhánh có điều kiện (Branching probabilities).
  3. Tốc độ đến ($\lambda$), phân phối inter-arrival time & lịch đến (Arrival calendar).
  4. Resource pools (Tên, kích thước, chi phí/giờ, lịch làm việc).
  5. Gán tác vụ cho Resource pools.
- **Chọn phân phối xác suất:**
  - **Fixed:** Ít biến động (VD: tác vụ phần mềm).
  - **Normal:** Lặp lại ổn định (cần *mean* & *std dev*).
  - **Exponential:** Tác vụ phức tạp, có **đuôi dài (long tail)** — thường nhanh nhưng thỉnh thoảng mất rất lâu (chỉ cần *mean*).
- **3 Cạm bẫy của Simulation (Pitfalls):**
  1. **Stochasticity (Tính ngẫu nhiên):** Mỗi lần chạy ra kết quả khác nhau → *Giải pháp:* Chạy đủ dài, chạy nhiều lần (multiple runs), tính trung bình & khoảng tin cậy (confidence intervals).
  2. **Data quality (Chất lượng dữ liệu):** "Garbage in, garbage out" → *Giải pháp:* Dùng dữ liệu thực tế thay vì đoán mò, đối chiếu kết quả mô phỏng As-Is với thực tế.
  3. **Simplifying assumptions (Giả định đơn giản hóa):** Giả định quy trình luôn tuân thủ 100%, không làm đa nhiệm (no multitasking), không gom lô (no batching), không mệt mỏi/gián đoạn.

---

## Lecture 8: Tái thiết kế Quy trình 1 — BPR

### 8.1. Hai hướng tiếp cận Tái thiết kế
| Tiêu chí | Transformational Redesign (BPR) | Transactional Redesign (Heuristic) |
| :--- | :--- | :--- |
| **Bản chất** | Đặt lại toàn bộ giả định nền tảng của quy trình | Giữ nguyên cấu trúc chính, cải tiến từng bước (incremental) |
| **Mục tiêu** | Đổi mới đột phá (Breakthrough innovation) | Xử lý từng vấn đề cụ thể, cân bằng đánh đổi |
| **Đại diện** | **Business Process Reengineering (BPR)** | **Heuristic Redesign (Lecture 9)** |

### 8.2. Case Study kinh điển: Ford vs Mazda (Hammer, 1990)
- **As-Is (Ford):** Bộ phận Accounts Payable có **> 500 nhân viên** đối chiếu thủ công 3 chứng từ (PO – Phiếu nhận hàng – Hóa đơn). Tự động hóa kiểu cũ chỉ cải thiện 20%.
- **Mazda:** Chỉ có **~15 nhân viên** (gấp 6–7 lần hiệu quả hơn sau khi quy đổi quy mô).
- **To-Be (Evaluated Receipts Settlement — ERS):** Dùng CSDL chung; khi hàng đến kho, nhân viên kho quét xác nhận khớp PO → **tự động kích hoạt thanh toán, bỏ luôn bước kiểm tra hóa đơn**!
- **Kết quả:** Giảm **75% nhân sự**, giảm sai sót và chậm thanh toán.
- **Khẩu hiệu nổi tiếng:** *"Don't Automate, Obliterate!"* (Đừng tự động hóa cái không cần làm — hãy xóa bỏ nó trước!).

### 8.3. 5 Nguyên tắc cốt lõi của BPR
1. **Capture information once and at the source:** Nhập dữ liệu 1 lần tại nguồn (dùng CSDL chung / Self-service, không gửi lòng vòng).
2. **Subsume information-processing work into the real work:** Gộp việc xử lý thông tin vào chính công việc tạo ra thông tin đó (VD: ERS tại kho hàng).
3. **Have those who use the output drive the process:** Để người hưởng kết quả tự dẫn dắt quy trình (VD: Vendor-managed inventory, Scan-based trading).
4. **Put the decision point where the work is performed & build control into the process:** Trao quyền cho nhân viên tuyến đầu tự quyết định, thay kiểm duyệt rườm rà bằng kiểm soát thống kê (statistical controls).
5. **Treat geographically dispersed resources as though they were centralized:** Gom nhóm tài nguyên phân tán thành pool tập trung → giảm thời gian chờ dù utilization cao.

---

## Lecture 9: Tái thiết kế Quy trình 2 — Heuristic Redesign

### 9.1. Devil's Quadrangle (Tứ giác Ác quỷ)
Mọi cải tiến quy trình đều là sự **đánh đổi (trade-off)** giữa 4 chiều:
- **Time** (Thời gian) — **Cost** (Chi phí) — **Quality** (Chất lượng) — **Flexibility** (Tính linh hoạt: khả năng ứng phó biến động tải, nhu cầu, nguồn lực ở cấp Resource / Process / Management).
- *Thường cải thiện 1 chiều sẽ làm suy giảm 1 chiều khác!*

### 9.2. 9 Nhóm Heuristic Tái thiết kế (Tóm tắt nhanh)
*(Xem bảng chi tiết có tác động T/C/Q/F tại [redesign-heuristics.csv](./redesign-heuristics.csv))*

- **Cấp Task (Task-level):**
  - **H1. Task elimination:** Bỏ bước NVA, giảm kiểm duyệt tay bằng statistical control / miễn duyệt đơn nhỏ `(T+, C+/-, Q-)`.
  - **H2. Task composition / decomposition:** Gộp task để giảm handover/context switch `(T+, C+/-, F+)` HOẶC tách task cho chuyên viên chuyên biệt `(T-, C+, F-)`.
  - **H3. Triage:** Chuyên biệt hóa 1 task thành nhiều nhánh theo loại `(T+, C+/-, F-)` HOẶC tổng quát hóa nhiều task thành 1 `(T-, C+/-, F+)`.
- **Cấp Luồng (Flow-level):**
  - **H4. Re-sequencing:** Đưa kiểm tra loại sớm (**knock-out checks**) lên đầu; đẩy bước tốn kém xuống sau `(T+, C+)`.
  - **H5. Parallelism enhancement:** Chạy song song các tác vụ độc lập để giảm Cycle Time `(T+, C-)`.
- **Cấp Quy trình (Process-level):**
  - **H6. Process specialization & standardization:** Tách quy trình theo mùa/phân khúc `(F-)` HOẶC gộp chuẩn hóa chung `(C+, F+)`.
  - **H7. Resource optimization:** Gom pool tập trung, giao việc đúng sở trường, ưu tiên giao chuyên viên trước để giữ tính linh hoạt, giảm setup bằng **chaining** (tuần tự) hoặc **batching** (gom lô) `(T+, C+, F+/-)`.
  - **H8. Communication optimization:** Tối ưu số lần, loại hình (đồng bộ cho lỗi nhỏ / bất đồng bộ cho thông báo & lỗi lớn) và thời điểm tương tác (**Front-loaded / Complete-Kit Concept** — không bắt đầu việc khi chưa đủ hồ sơ) `(T+, Q+, C+/-, F-)`.
  - **H9. Automation:** Chia sẻ dữ liệu, self-service, RFID/GPS, BRMS/DMN, RPA, BPMS `(T+, C+/-, Q+/-, F-)`.

---

## Lecture 10: Tự động hóa Quy trình (Process Automation)

### 10.1. Conceptual Model vs Executable Model
- **Conceptual "To-Be" Model:** Do chuyên gia nghiệp vụ vẽ, dễ hiểu, phục vụ giao tiếp, có thể còn mơ hồ.
- **Executable Model:** Do chuyên gia IT xây dựng cho **BPMS**, máy đọc được, **không được mơ hồ**, đầy đủ chi tiết kỹ thuật.

### 10.2. 5 Bước chuyển từ Conceptual sang Executable Model
1. **Identify automation boundaries:** Phân loại từng tác vụ: **Automated** (Service/Script/Rule), **User task** (người dùng tương tác qua BPMS), **Manual task** (ngoài hệ thống).
2. **Review manual tasks:** *"If it can't be seen by the BPMS, it doesn't exist"* → Tìm cách hỗ trợ qua IT (biến thành User/Automated task) hoặc bỏ ra khỏi phạm vi tự động hóa.
3. **Complete the process model:**
   - *Exceptions are the rule:* Xử lý đủ timeout, không phản hồi, sai định dạng, lỗi tác vụ.
   - *No data = no decisions, no handovers:* Khai báo đủ đối tượng dữ liệu và phân tích **CRUD** (Create, Read, Update, Delete) cho từng task/decision.
4. **Adjust task granularity:** Gộp các task liên tiếp do **cùng 1 người** làm; tách task nếu cần **nhiều người khác nhau**.
5. **Specify execution properties:** Biến quy trình (process variables), mapping dữ liệu, API/Service endpoints, biểu thức rẽ nhánh, luật gán người thực hiện, giao diện Form.

### 10.3. Kiến trúc một BPMS (VD: Camunda, Bonita, Flowable, Bizagi, Pega)
- **Process Modeling Tool** & **Repository**
- **Execution Engine:** Khởi tạo case, điều phối work items, ghi log thực thi.
- **Worklist Handler:** "Hộp thư đến" (inbox) hiển thị và cho nhân viên nhận việc.
- **Administration & Monitoring Tools:** Quản trị phân quyền, theo dõi trạng thái case.
- **External Services / APIs:** Kết nối DB, CRM, BRMS, Email...

---

## Lecture 12: Giám sát & Khai phá Quy trình (Monitoring & Process Mining)

### 12.1. Process Performance Dashboards
| Loại Dashboard | Đối tượng | Dữ liệu | Mục tiêu chính |
| :--- | :--- | :---: | :--- |
| **Operational** | Nhân viên vận hành, quản lý trực tiếp | **Runtime** (thời gian thực) | Phát hiện & xử lý ngay (WIP, ca quá hạn/rủi ro, tải tài nguyên) |
| **Tactical** | Process Owner, Quản lý quy trình | **Historical** (lịch sử) | Phân tích tìm nút thắt cổ chai (Cycle time, Error rate, Utilization) |
| **Strategic** | Ban lãnh đạo (Executives) | **Historical** | Liên kết hiệu suất quy trình với mục tiêu chiến lược (Balanced Scorecard) |

- **4 loại Widget:**
  1. **1D:** 1 chỉ số đơn lẻ (KPI card).
  2. **2D:** Biểu đồ 2 trục — **Longitudinal** (x = thời gian), **Cross-sectional** (x = thuộc tính: nhân viên/quốc gia), **Histogram** (x = chỉ số, y = tần suất).
  3. **3D:** 3 biến — **Heat map** (màu/đậm nhạt), **Bubble chart** (kích thước), **Scatter plot**.
  4. **N-D:** Bảng dữ liệu (Tables).

### 12.2. Process Mining — 4 Năng lực cốt lõi
Đầu vào tối thiểu của **Event Log** gồm 3 cột bắt buộc: **`Case ID` (CID) + `Activity/Task` + `Timestamp`** (có thể thêm Resource, Cost...).

1. **Automated Process Discovery (Khám phá quy trình tự động):**
   - **Process Map / Directly-Follows Graph (DFG):** Nút = hoạt động (kèm tần suất), cung $A \to B$ = $B$ theo ngay sau $A$ trong ít nhất 1 trace. Có thể trừu tượng hóa (abstraction sliders) theo tần suất hoặc thời gian.
   - **Hạn chế của DFG:** **Over-generalize** (cho phép các đường đi vô lý không có trong log) và **không phân biệt rõ XOR, AND (song song), Loop**.
   - **Giải pháp:** Khám phá mô hình **BPMN** (VD: thuật toán **Split Miner** trong Apromore).
     - `[abc, abd]` → **XOR** (chọn c hoặc d).
     - `[abcd, acbd]` → **AND** (b và c song song).
     - `[abcd, abcbcd]` → **Loop** (lặp b–c).
2. **Conformance Checking (Kiểm tra tuân thủ):**
   - **Model-based:** So sánh Event Log với mô hình chuẩn để tìm *Unfitting behavior* (lệch chuẩn, bỏ bước) và *Additional behavior* (mô hình thừa đường đi).
   - **Rule-based:** Kiểm tra luật tuân thủ (VD: bước bắt buộc, tối đa 1 lần, **four-eyes principle** — 2 bước A và B không được làm bởi cùng 1 người).
3. **Performance Mining:** Tô màu hiệu suất lên Process Map (hiển thị thời gian thực thi từng nút & thời gian chờ trên từng cung → lộ rõ **Bottleneck node** nơi mọi cung đi vào đều chậm), Dashboards, Log Animation.
4. **Variant Analysis (Phân tích biến thể):** Cắt (slice) log thành nhiều tập con theo sản phẩm/khách hàng/nhanh vs chậm, rồi so sánh song song (process map, multi-log dashboard, animation) để tìm nguyên nhân khác biệt hiệu suất.

### 12.3. Log Filtering (Lọc Event Log)
- **Case-Level Filter:** Giữ lại hoặc xóa **toàn bộ case** (Attribute, Timeframe, Performance/Duration, Path, Repetition).
- **Event-Level Filter:** Chỉ giữ hoặc xóa **từng sự kiện riêng lẻ** bên trong case (Attribute, Timeframe, Between filter).
