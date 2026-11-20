# 🧮 Sổ Tay Công Thức & Giải Chi Tiết Bài Tập Định Lượng (L5, L6, L7)

> Tổng hợp toàn bộ công thức tính toán xuất hiện trong bài giảng, bài giải trên bảng ([`Giabaitap tren slide Lecture6and7.jpg`](./ref/Quiz%20v%C3%A0%20%C4%91%C3%A1p%20%C3%A1n/Giabaitap%20tren%20slide%20Lecture6and7.jpg)) và Quiz 6.  
> [⬅️ Quay lại Trang chủ Ôn thi](./README.md)

---

## 1. Bảng Công Thức Tổng Hợp

### 1.1. Thời gian & Hiệu suất Chu kỳ (Time & CTE — Lecture 6)

$$\text{Cycle Time (CT)} = \text{Processing Time (PT)} + \text{Waiting Time (WT)}$$

$$\text{Cycle Time Efficiency (CTE)} = \frac{\text{Theoretical Cycle Time (Processing Time)}}{\text{Actual Cycle Time (bao gồm Waiting Time)}} \times 100\%$$

> [!TIP]
> **Chú ý đổi đơn vị khi tính CTE!**  
> Trong nhiều bài tập (VD: Lecture 6 slide 24), `Processing Time` tính theo **giờ** còn `Cycle Time` tính theo **ngày làm việc**. Quy ước chuẩn trong giáo trình: **1 ngày làm việc = 8 giờ** (kiểm tra kỹ đề bài nếu đề ghi khác).

---

### 1.2. Flow Analysis — 4 Cấu Trúc Chuẩn (Lecture 6)

| Cấu trúc BPMN | Công thức tính Cycle Time ($CT$) | Ghi chú |
| :--- | :--- | :--- |
| **Tuần tự (Sequence)** | $$CT = T_1 + T_2 + \dots + T_n$$ | Cộng tổng các bước |
| **Rẽ nhánh loại trừ (XOR)** | $$CT = p_1 T_1 + p_2 T_2 + \dots + p_n T_n$$ | Với $\sum p_i = 1$ (trung bình có trọng số) |
| **Song song (AND)** | $$CT = \max(T_1, T_2, \dots, T_n)$$ | Lấy nhánh **chậm nhất** (khi tính **Cost** thì cộng tổng, không lấy max!) |
| **Vòng lặp làm lại (Rework Loop)** | $$CT = \frac{T}{1 - r}$$ | $r$: xác suất lặp lại (rework); $(1 - r)$: xác suất thoát vòng lặp |

> [!IMPORTANT]
> **Mẹo nhớ công thức Rework Loop:**  
> Nếu xác suất làm lại là $r = 20\%$ (tức thoát ra là $80\% = 0.8$), số lần thực hiện trung bình là $\frac{1}{1 - 0.2} = \frac{1}{0.8} = 1.25$ lần → $CT = T / 0.8 = 1.25 T$.  
> **Flow Analysis KHÔNG cần dùng Arrival Rate ($\lambda$)!**

---

### 1.3. Mức độ Sử dụng Tài nguyên & Định luật Little (Lecture 6)

$$\text{Resource Utilization } (\rho) = \frac{\text{Thời gian thực làm trên quy trình}}{\text{Tổng thời gian sẵn có của tài nguyên}}$$

$$\text{Little's Law:} \quad WIP = \lambda \cdot CT \quad \Longleftrightarrow \quad L = \lambda \cdot W$$

Trong đó:
- $WIP$ (hay $L$): Số lượng hồ sơ/khách hàng trung bình đang nằm trong hệ thống (*Work-in-Process*).
- $\lambda$: Tốc độ đến trung bình (*Arrival rate*, đơn vị: khách/giờ hoặc đơn/ngày).
- $CT$ (hay $W$): Thời gian trung bình 1 khách/đơn ở trong hệ thống (*Cycle time*).

---

### 1.4. Lý thuyết Hàng đợi: $M/M/1$ và $M/M/c$ (Lecture 7)

Ký hiệu chung:
- $\lambda$: tốc độ đến trung bình (arrivals / time unit).
- $\mu$: tốc độ phục vụ trung bình của **1 server** (jobs / time unit) $\Rightarrow$ Thời gian phục vụ trung bình $E[S] = \frac{1}{\mu}$.
- $c$: số lượng server chạy song song.

#### Trường hợp 1 server: **$M/M/1$** ($c = 1$, điều kiện ổn định $\rho < 1$)
| Đại lượng | Ý nghĩa | Công thức |
| :---: | :--- | :--- |
| $\rho$ | Hiệu suất sử dụng server (Utilization) | $$\rho = \frac{\lambda}{\mu}$$ |
| $L$ | Số khách trung bình trong **hệ thống** (WIP) | $$L = \frac{\rho}{1 - \rho}$$ |
| $L_q$ | Số khách trung bình trong **hàng đợi** | $$L_q = \frac{\rho^2}{1 - \rho} = L - \rho$$ |
| $W$ | Thời gian trung bình trong **hệ thống** (CT) | $$W = \frac{L}{\lambda} = \frac{1}{\mu - \lambda}$$ |
| $W_q$ | Thời gian trung bình chờ trong **hàng đợi** | $$W_q = \frac{L_q}{\lambda} = \frac{\lambda}{\mu(\mu - \lambda)} = W - \frac{1}{\mu}$$ |

#### Trường hợp nhiều server: **$M/M/c$** ($c \ge 2$, điều kiện ổn định $\rho < 1$)
- Hiệu suất sử dụng: $$\rho = \frac{\lambda}{c \cdot \mu}$$
- Mối liên hệ Little's Law luôn đúng:
  $$W_q = \frac{L_q}{\lambda}, \qquad W = W_q + \frac{1}{\mu}, \qquad L = \lambda \cdot W$$
- *(Trong thực tế/thi, $L_q$ của $M/M/c$ được tra bảng hoặc dùng Queue Theory Calculator).*

---

### 1.5. Tác động Định lượng trong Issue Register (Lecture 5)

$$\text{Quantitative Impact (năm)} = \text{Tổng số ca/năm} \times \text{Tỷ lệ xảy ra lỗi} \times \text{Chi phí thiệt hại mỗi ca lỗi}$$

---

## 2. Giải Chi Tiết Các Bài Tập Trong Slide, Ảnh Bảng & Quiz

### Bài Tập 1: Flow Analysis & Cycle Time Efficiency (Lecture 6 — Slide 23 & 24)

**Đề bài:** Cho một quy trình gồm 4 khối nối tiếp nhau:
1. **Khối 1 (Rework Loop):** Xác suất lặp lại $r = 20\%$ (thoát ra $80\%$). Thời gian chu kỳ $T = 1\text{ ngày}$, thời gian xử lý $PT = 2\text{ giờ}$.
2. **Khối 2 (Parallel — AND):** 2 nhánh song song có $CT = (1\text{ ngày}, 3\text{ ngày})$ và $PT = (0.5\text{ giờ}, 3\text{ giờ})$.
3. **Khối 3 (Sequence):** 1 tác vụ có $CT = 3\text{ ngày}$, $PT = 2\text{ giờ}$.
4. **Khối 4 (Exclusive — XOR):** Nhánh 1 ($60\%$) có $CT = 1\text{ ngày}, PT = 2\text{ giờ}$; Nhánh 2 ($40\%$) có $CT = 2\text{ ngày}, PT = 0.5\text{ giờ}$.

**Lời giải chi tiết:**
- **Bước 1 — Tính Cycle Time ($CT$):**
  $$CT = \frac{1}{1 - 0.2} + \max(1, 3) + 3 + (0.6 \times 1 + 0.4 \times 2)$$
  $$CT = 1.25 + 3 + 3 + 1.4 = \mathbf{8.65\text{ ngày}}$$
- **Bước 2 — Tính Processing Time ($PT$):**
  $$PT = \frac{2}{0.8} + \max(0.5, 3) + 2 + (0.6 \times 2 + 0.4 \times 0.5)$$
  $$PT = 2.5 + 3 + 2 + 1.4 = \mathbf{8.9\text{ giờ}}$$
- **Bước 3 — Tính Cycle Time Efficiency ($CTE$):**  
  Quy đổi $1\text{ ngày làm việc} = 8\text{ giờ} \Rightarrow CT = 8.65 \times 8 = 69.2\text{ giờ}$.
  $$CTE = \frac{8.9}{69.2} \approx \mathbf{12.86\% \approx 12.9\%}$$

---

### Bài Tập 2: Little's Law — Nhà Hàng Fast-Food (Lecture 6 Slide 30–31 & Ảnh Giải Bảng)

> Đối chiếu trực tiếp với ảnh bảng [`Giabaitap tren slide Lecture6and7.jpg`](./ref/Quiz%20v%C3%A0%20%C4%91%C3%A1p%20%C3%A1n/Giabaitap%20tren%20slide%20Lecture6and7.jpg).

**Đề bài:**  
Một nhà hàng fast-food mở cửa từ **10:00 đến 22:00** (12 giờ/ngày), đón trung bình **1200 khách/ngày**:
- **Giờ cao điểm (Peak times):** `12:00–15:00` (3 giờ) và `18:00–21:00` (3 giờ) → tổng **6 giờ**. Tổng lượng khách: **900 khách**, số khách trung bình có mặt trong quán tại một thời điểm: **90 khách**.
- **Giờ thấp điểm (Non-peak times):** 6 giờ còn lại (`10:00–12:00`, `15:00–18:00`, `21:00–22:00`). Tổng lượng khách: **300 khách**, số khách trung bình có mặt trong quán: **30 khách**.

**Câu 1: Thời gian trung bình 1 khách ở trong nhà hàng vào giờ cao điểm?**
- Tổng thời gian cao điểm: $3 + 3 = 6\text{ giờ}$.
- Tốc độ khách đến: $\lambda_1 = \frac{900}{6} = 150\text{ khách/giờ}$.
- Số khách trung bình trong quán: $L_1 = 90\text{ khách}$.
- Áp dụng Little's Law ($L = \lambda \cdot W$):
  $$W_1 = \frac{L_1}{\lambda_1} = \frac{90}{150} = \mathbf{0.6\text{ giờ} = 36\text{ phút}}$$

**Câu 2: Thời gian trung bình 1 khách ở trong nhà hàng vào giờ thấp điểm?**
- Tổng thời gian thấp điểm: $12 - 6 = 6\text{ giờ}$.
- Tốc độ khách đến: $\lambda_2 = \frac{300}{6} = 50\text{ khách/giờ}$.
- Số khách trung bình trong quán: $L_2 = 30\text{ khách}$.
- Áp dụng Little's Law:
  $$W_2 = \frac{L_2}{\lambda_2} = \frac{30}{50} = \mathbf{0.6\text{ giờ} = 36\text{ phút}}$$

**Câu 3 (Mở rộng tư duy thi tự luận): Quán muốn chạy marketing hút thêm khách nhưng giờ cao điểm đã chật kín chỗ ($L$ không tăng thêm được). Làm sao giải quyết mà KHÔNG cần mở rộng mặt bằng?**
Từ công thức $L = \lambda \cdot W$, nếu sức chứa $L$ cố định, muốn tăng $\lambda$ (đón nhiều khách hơn) thì có 2 hướng:
1. **Giảm thời gian ở lại ($W$) vào giờ cao điểm:** Tăng tốc phục vụ (kiosk tự đặt hàng, thanh toán trước, mở thêm quầy/nhân viên giờ cao điểm), đẩy mạnh **take-away / delivery** để khách không chiếm chỗ ngồi.
2. **Dịch chuyển nhu cầu sang giờ thấp điểm:** Khuyến mãi/giảm giá giờ thấp điểm (*happy hour*) để tăng $\lambda_2$ khi quán đang trống chỗ.

---

### Bài Tập 3: Hàng Đợi $M/M/1$ vs $M/M/2$ — Phòng Cấp Cứu ER (Lecture 7 — Slide 17–18)

**Đề bài:**  
Bệnh nhân đến phòng cấp cứu theo quá trình Poisson với $\lambda = 2\text{ bệnh nhân/giờ}$. Thời gian khám của 1 bác sĩ theo phân phối mũ với tốc độ phục vụ $\mu = 3\text{ bệnh nhân/giờ}$ (tức trung bình $1/\mu = 20\text{ phút/bệnh nhân}$). So sánh phương án **1 bác sĩ ($c=1$)** và **2 bác sĩ ($c=2$)**.

**Lời giải ($c = 1$, dùng công thức $M/M/1$):**
- $\rho = \frac{\lambda}{\mu} = \frac{2}{3} \approx 66.7\%$
- $L = \frac{\rho}{1 - \rho} = \frac{2/3}{1/3} = \mathbf{2\text{ bệnh nhân}}$
- $L_q = \frac{\rho^2}{1 - \rho} = \frac{4/9}{1/3} = \mathbf{\frac{4}{3} \approx 1.33\text{ bệnh nhân}}$
- $W = \frac{1}{\mu - \lambda} = \frac{1}{3 - 2} = \mathbf{1\text{ giờ} = 60\text{ phút}}$
- $W_q = \frac{L_q}{\lambda} = \frac{4/3}{2} = \mathbf{\frac{2}{3}\text{ giờ} = 40\text{ phút}}$

**Bảng so sánh $c = 1$ vs $c = 2$ (theo Slide 18):**
| Chỉ số | 1 Bác sĩ ($c = 1$) | 2 Bác sĩ ($c = 2$) | Nhận xét |
| :--- | :---: | :---: | :--- |
| Utilization ($\rho$) | $2/3 \approx 66.7\%$ | $1/3 \approx 33.3\%$ | Tải mỗi bác sĩ giảm một nửa |
| Số người chờ ($L_q$) | $4/3 \approx 1.33$ người | $1/12 \approx 0.08$ người | Gần như không phải xếp hàng |
| Tổng số người trong ER ($L$) | $2$ người | $3/4 = 0.75$ người | Giảm mạnh WIP |
| Thời gian chờ ($W_q$) | **$40$ phút** | **$2.5$ phút** | **Giảm 16 lần!** (rất đáng thuê thêm bác sĩ với phòng cấp cứu) |
| Tổng thời gian ở ER ($W$) | $60$ phút | $22.5$ phút | ($W = 2.5 + 20 = 22.5$ phút) |

---

### Bài Tập 4: Case Bảo Hiểm InsureIT (Quiz 6 — Câu 2, 3, 4)

**Tóm tắt dữ kiện:**
- Tổng lượng yêu cầu bồi thường: $2000\text{ claims/năm}$ ($\rightarrow$ **không dùng** khi tính CT & CTE bằng Flow Analysis!).
- Nhánh phân loại: **$20\%$ ngắn hạn** (short-term) và **$80\%$ dài hạn** (long-term).
- **Bước 1 (Chung):** Nhập liệu & kiểm tra cơ bản = **$10\text{ phút}$**.
- **Nhánh ngắn hạn ($20\%$):** Đánh giá & thông báo = **$20\text{ phút}$**. Tổng thời gian chu kỳ thực tế = **$3\text{ ngày làm việc}$**.
- **Nhánh dài hạn ($80\%$):**
  - Liên hệ khách xin giấy ủy quyền = **$10\text{ phút}$**.
  - Gửi yêu cầu báo cáo y tế cho bệnh viện = **$10\text{ phút}$**.
  - Chờ bệnh viện trả lời = trung bình $15\text{ ngày}$ (*đây là Waiting time, KHÔNG tính vào Theoretical CT!*).
  - Đánh giá quyền lợi = **$60\text{ phút}$** (1 giờ).
  - Tổng thời gian chu kỳ thực tế = **$20\text{ ngày làm việc}$**.
- **Bước cuối (Thanh toán):** $80\%$ tổng số yêu cầu được duyệt hưởng quyền lợi → Nhân viên tài chính xử lý mất **$20\text{ phút}$**.

**Lời giải:**
1. **Average Cycle Time (bao gồm thời gian chờ):**
   $$CT = 0.2 \times 3 + 0.8 \times 20 = 0.6 + 16 = \mathbf{16.6\text{ ngày làm việc}}$$
2. **Theoretical Cycle Time (Tổng thời gian xử lý — loại bỏ thời gian chờ):**
   $$TCT = 10 + 0.2 \times 20 + 0.8 \times (10 + 10 + 60) + 0.8 \times 20$$
   $$TCT = 10 + 4 + 64 + 16 = \mathbf{94\text{ phút}}$$
3. **Cycle Time Efficiency (tham khảo thêm):**  
   Với $1\text{ ngày} = 8\text{ giờ} = 480\text{ phút} \Rightarrow CT = 16.6 \times 480 = 7968\text{ phút}$:
   $$CTE = \frac{94}{7968} \approx \mathbf{1.18\%}$$ *(cực thấp vì chờ báo cáo y tế quá lâu!)*.

---

### Bài Tập 5: Tính Quantitative Impact trong Issue Register (Lecture 5 — Slide 29)

**Case BuildIT (Thuê thiết bị xây dựng):** $3000$ lượt thuê/năm, giá thuê $100\text{ EUR/ngày}$, thời gian thuê trung bình $4\text{ ngày}$.
1. **Giữ thiết bị lâu hơn cần thiết:** $10\%$ ca giữ thừa $2\text{ ngày}$:
   $$\text{Impact} = 0.1 \times 3000 \times 2 \times 100 = \mathbf{60,000\text{ EUR/năm}}$$
2. **Giao sai thiết bị do lỗi nội bộ:** $5\%$ ca bị trả lại, mỗi ca bị tính phí $100\text{ EUR}$:
   $$\text{Impact} = 0.05 \times 3000 \times 100 = \mathbf{15,000\text{ EUR/năm}}$$
3. **Phí phạt thanh toán hóa đơn trễ:** $10\%$ hóa đơn trả trễ, phí phạt $2\%$ giá trị hóa đơn ($4\text{ ngày} \times 100\text{ EUR}$):
   $$\text{Impact} = 0.1 \times 3000 \times 4 \times 100 \times 0.02 = \mathbf{2,400\text{ EUR/năm}}$$
→ **Ưu tiên xử lý vấn đề #1 trước** (chiếm gần $78\%$ tổng thiệt hại tài chính — đúng nguyên lý Pareto!).
