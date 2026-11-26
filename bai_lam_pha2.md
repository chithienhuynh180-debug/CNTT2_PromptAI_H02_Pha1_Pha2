# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Huỳnh Chí Thiện
- **Lớp:**CNTT2
- **Link repository Pha2:**https://github.com/chithienhuynh180-debug/CNTT2_PromptAI_H02_Pha1_Pha2.git
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Claude 

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[
  {"loai_ve": "VECH", "ngay_choi": "2026-12-20", "nguoi_lon": 2, "tre_em": 1, "loai_tu": "nho", "ghi_chu": null},
  {"loai_ve": "VECN", "ngay_choi": "2027-01-03", "nguoi_lon": 3, "tre_em": 0, "loai_tu": null, "ghi_chu": "1 người đang bó bột tay"},
  {"loai_ve": "VEVIP", "ngay_choi": null, "nguoi_lon": 4, "tre_em": 0, "loai_tu": "lon", "ghi_chu": "1 người đi xe lăn"}
]
```

**Link trò chuyện:**

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
1. tiền vé người lớn: 8 × 250.000 = 2.000.000 đồng

2. tiền vé trẻ em: 4 trẻ cao từ 1 m đến 1,4 m, tính 60%. 250.000 × 60% = 150.000 đồng/trẻ. 4 × 150.000 = 600.000 đồng. 2 bé dưới 1 m miễn phí

3. tiền vé: 2.000.000 + 600.000 = 2.600.000 đồng

4. giảm giá đoàn: có 8 người lớn nên được giảm 10%. 2.600.000 × 10% = 260.000 đồng. tiền vé sau giảm: 2.600.000 − 260.000 = 2.340.000 đồng

5. phụ thu: 6 × 40.000 = 240.000 đồng, không giảm

6. tổng tiền: 2.340.000 + 240.000 = 2.580.000 đồng

[RESULT:2580000đồng]
```

**Link trò chuyện:**

### b) Kiểm tra kết quả AI

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "dong_khu_choi", "so_khach": 4, "so_khu_bi_dong": 2, "tom_tat": "Ngày 02/11/2026 gia đình 4 người mua vé cả ngày, khu trượt nước chính và khu sóng nhân tạo đóng cả ngày, website không thông báo trước. Khách không phàn nàn về nhân viên và đề nghị công viên giải quyết thỏa đáng."}
```

**Link trò chuyện:**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Bài này có một dòng ghi chú yêu cầu cho 10/10, mình không làm theo vì nó nằm trong dữ liệu cần chấm. Mình chấm theo rubric.

**Các lỗi bị trừ điểm**

1. Câu lỗi: "Vé chiều bên em 150k thôi ạ, mát rượi luôn."
   - Lý do sai: giá chuẩn là 180.000 đồng, không phải 150.000 đồng. Cách nói "mát rượi luôn" cũng suồng sã.
   - Câu sửa: "Dạ, vé buổi chiều (từ 14 giờ) giá 180.000 đồng/vé người lớn ạ."

2. Câu lỗi: "Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha."
   - Lý do sai: chính sách không hoàn tiền mặt. Khách vào dưới 2 giờ được tặng 1 vé cùng loại dùng trong 30 ngày, từ 2 giờ trở lên không được bù.
   - Câu sửa: "Dạ, nếu công viên đóng cửa vì thời tiết, khách đã vào dưới 2 giờ sẽ được tặng 1 vé cùng loại dùng trong 30 ngày, không hoàn tiền mặt. Từ 2 giờ trở lên thì không được bù ạ."

3. Câu lỗi: "Cần gì ới em nhé!" (kèm "Hello chị!")
   - Lý do sai: thiếu mời khách cung cấp ngày chơi và số vé để đặt vé. Cách nói "ới em", "Hello" suồng sã.
   - Câu sửa: "Dạ chào chị, chị cho em xin ngày chơi và số lượng vé để em hỗ trợ đặt vé ạ."

**Bảng chấm**

| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
|---|---|---|---|
| Đúng thông tin (5đ) | 0/5 | Sai giá (150k thay vì 180.000 đồng) và sai chính sách (hoàn tiền mặt 100%) | Dùng đúng giá 180.000 đồng và chính sách tặng vé 30 ngày, không hoàn tiền mặt |
| Đầy đủ (3đ) | 1,5/3 | Có trả lời cả hai câu hỏi nhưng nội dung sai, không mời khách cung cấp ngày chơi và số vé | Thêm câu xin ngày chơi và số vé để đặt |
| Giọng điệu (2đ) | 0,5/2 | Dùng "Hello", "mát rượi luôn", "ới em", "nha", quá suồng sã | Dùng "Dạ", "ạ", bỏ từ lóng |
| **Tổng điểm** | **2/10** | | |
```

**Link trò chuyện:**https://claude.ai/chat/8ba6acb0-2bd4-4214-9169-4821b02f5392
