# BÀI LÀM PHA 1 

- **Họ tên:**
- **Lớp:**
- **Link repository Pha1:**

> Pha 1 (70 phút đầu, KHÔNG dùng AI). Viết xong, kéo thả file này vào repository Pha1 trước mốc giờ giám thị công bố.

## 4.1. Bảo vệ dữ liệu và chống ảo giác

### a) Ghi chú đã ẩn danh hoá

**GHI CHU DA AN DANH**

```text
Khán giả [TEN_KHACH], số điện thoại 0987 654 321, số [CCCD_MA_DINH_DANH] , email [TEN_gmail.com] , đặt 3 vé gói SVT trận bán kết Cúp Sao Vàng ngày 18/12/2026 cho 2 người lớn và 1 trẻ em 9 tuổi. Khán giả đã chuyển khoản đặt cọc 1.500.000 đồng. Khán giả yêu cầu 3 ghế ngồi cạnh nhau gần lối đi
```

### b) Hai câu lệnh chống ảo giác

**CAU LENH**

```text
-trả lời câu hỏi dựa trên file vừa gửi ,nếu file không có thông tin thì dựa trên câu hỏ và trả lời đúng trọng tâm tự tìm hiểu trên các trang chính chủ về vấn đề liên quan không bịa những cái không có thật
-ghi rõ câu trả lời đang nói đến mục nào trong file,giải thích rõ ràng vấn đề đang gặp phải 
```

## 4.2. Trích xuất tin nhắn đặt vé ra JSON

**PROMPT**

```text
1. C - Context bối cảnh
Bạn là AI chuyên xử lý tin nhắn đặt vé sự kiện thể thao. Nhiệm vụ của bạn là đọc nội dung khách hàng gửi, trích xuất thông tin và chuyển thành dữ liệu JSON theo đúng cấu trúc quy định.

Bảng mã gói:
SVT – Sân Vận Động: vé trận đấu
FZ – Fan Zone: khu cổ vũ
VIP – Khán đài VIP

2. R- Request yêu cầu
Xử lý 3 tin nhắn TN1, TN2, TN3 thành một mảng JSON gồm 3 đối tượng theo đúng thứ tự
Mỗi đối tượng phải có đủ 6 trường:
- ma_goi
- ngay_su_kien
- nguoi_lon
- tre_em
- loai_ve
- ghi_chu
3. E – Explanation giải thích
Áp dụng 5 quy tắc chuẩn hóa sau:
1.ma_goi lấy theo bảng mã gói.
2. ngay_su_kien dạng YYYY-MM-DD; tin nhắn không ghi năm thì lấy năm 2026; không có ngày cụ thể thì null.
3. Khách không nhắc trẻ em thì tre_em là 0 và mọi khách là người lớn.
4. loai_ve chỉ nhận "thuong", "vip" hoặc null.
5. ghi_chu chỉ ghi yêu cầu đặc biệt về chỗ ngồi, hỗ trợ di chuyển hoặc ăn uống; không có thì null.

Ví dụ Few-shot 

Input:
Đặt giúp mình 2 vé VIP trận chung kết ngày 15/11/2026, 2 người lớn và 1 bé. Cần chỗ ngồi cạnh lối đi
Output:
  Ví dụ Few-shot 
{"ma_goi": "VIP", "ngay_su_kien": "2026-11-15", "nguoi_lon": 2, "tre_em": 1, "loai_ve": "vip", "ghi_chu": "chỗ ngồi cạnh lối đi"}

Input:
Cho mình một vé Fan Zone, ngày nào cũng được, mình đi một mình
Output:
{"ma_goi": "FZ", "ngay_su_kien": null, "nguoi_lon": 1, "tre_em": 0, "loai_ve": "thuong", "ghi_chu": null}


4. A – Action hành động
Đọc và xử lý chính xác 3 tin nhắn dưới đây:

TN1: Mình muốn đặt gói Sân Vận Động trận tứ kết ngày 20/12 nha, 2 người lớn với 1 bé 8 tuổi, vé thường.

TN2: Cho 3 người đi Fan Zone trận ngày 05/01/2027 ạ. Một người cần hỗ trợ xe lăn.

TN3: Trận chung kết Cúp Sao Vàng tháng 12 còn vé không ạ? Nhà em 4 người lớn, có một người khiếm thị cần hỗ trợ tìm chỗ, lấy vé VIP.

Chuyển từng tin nhắn thành một mảng JSON, giữ đúng thứ tự TN1, TN2, TN3. Không tự ý thêm thông tin không có trong tin nhắn.
5. T – Tone going điệu
- chính xác, rõ ràng 
- không suy đoán thông tin khách hàng chưa cung cấp
- không tự ý them những thông tin không có
6. E – Extras 
- chỉ trả về một mảng JSON gồm đúng 3 đối tượng
- mỗi đối tượng phải có đúng 6 trường đã quy định
- số lượng người ghi bang số
- không chào hỏi, không giải thích, không thêm bất kỳ nội dung nào ngoài JSON

```

## 4.3. Báo giá vé bằng Chain-of-Thought

### a) Prompt

**PROMPT**

```text

```

## 4.4. Dây chuyền xử lý khiếu nại (Prompt Chaining)

### a) Prompt Trạm 1

**PROMPT**

```text
(Viết prompt vào đây – xoá dòng này)
```

### b) Hai điều cần kiểm tra ở JSON đầu ra của Trạm 1

1. (Viết câu trả lời vào đây – xoá dòng này)

2.

### c) Câu lệnh viết tiếp

**CAU LENH**

```text
(Viết câu lệnh vào đây – xoá dòng này)
```

## 4.5. Prompt chấm bài theo Rubric

**PROMPT**

```text
(Viết prompt vào đây – xoá dòng này)
```

## 4.6. Hoàn thiện System Prompt

> Phần Vai trò và Chuẩn đầu ra đã cho sẵn. Viết tiếp phần Quy tắc ràng buộc và Xử lý ngoại lệ.

```text
[Vai trò]
Bạn là "Trợ lý Cúp Sao Vàng", nhân viên tư vấn vé và dịch vụ trên website của giải bóng đá Cúp Sao Vàng, giúp khán giả chọn và đặt một trong 3 gói: SVT (Sân Vận Động – vé trận đấu), FZ (Fan Zone – khu cổ vũ), VIP (Khán đài VIP).

[Quy tắc ràng buộc]
1. (Viết quy tắc 1 – xoá dòng này)
2.
3.

[Chuẩn đầu ra]
Trả lời bằng tiếng Việt, lịch sự, tối đa 120 từ. Giá vé trình bày dạng gạch đầu dòng. Kết thúc bằng một câu hỏi về nhu cầu tiếp theo của khách.

[Xử lý ngoại lệ]
- Khách hỏi ngoài phạm vi: (Viết cách trả lời – xoá dòng này)
- Khách cung cấp thiếu thông tin:
```
