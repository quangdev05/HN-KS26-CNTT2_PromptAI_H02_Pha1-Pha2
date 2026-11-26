# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:** Phạm Duy Quang
- **Lớp:** HN-KS26-CNTT2
- **Link repository Pha2:** https://github.com/quangdev05/HN-KS26-CNTT2_PromptAI_H02_Pha1-Pha2
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Claude

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xem phim ra JSON

**KET QUA AI**

```text
[{"loai_ve": "P2D", "ngay_chieu": "2026-12-24", "ve_nguoi_lon": 2, "ve_tre_em": 1, "loai_ghe": "thuong", "ghi_chu": null}, {"loai_ve": "P3D", "ngay_chieu": "2027-01-01", "ve_nguoi_lon": 3, "ve_tre_em": 0, "loai_ghe": null, "ghi_chu": "1 người hay chóng mặt, cần ngồi gần lối ra"}, {"loai_ve": "GOLD", "ngay_chieu": null, "ve_nguoi_lon": 4, "ve_tre_em": 0, "loai_ghe": "doi", "ghi_chu": "1 bạn đi xe lăn"}]
```

**Link trò chuyện:** https://claude.ai/share/107a08ee-c8be-4036-a8be-17c3ca97765a

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
**Bảng giá áp dụng:** vé P3D = 130.000 đồng/người lớn.

**Bước 1: Tiền vé người lớn**
5 người × 130.000 = **650.000 đồng**

**Bước 2: Tiền vé trẻ em theo từng chiều cao**
- Bé cao 1,1 m (từ 1 m đến 1,3 m): 70% × 130.000 = 91.000 đồng
- Bé cao 1,25 m (từ 1 m đến 1,3 m): 70% × 130.000 = 91.000 đồng
- Bé cao 0,9 m (dưới 1 m, ngồi cùng người lớn): 0 đồng (miễn phí)

Tổng tiền vé trẻ em = 91.000 + 91.000 + 0 = **182.000 đồng**

**Bước 3: Tổng tiền vé trước giảm giá**
650.000 + 182.000 = **832.000 đồng**

**Bước 4: Kiểm tra điều kiện giảm giá**
- Nhóm có 5 người lớn, đạt điều kiện "từ 5 người lớn trở lên" nên được giảm 10% trên tiền vé.
- Số tiền giảm: 10% × 832.000 = **83.200 đồng**
- Tiền vé sau giảm: 832.000 − 83.200 = **748.800 đồng**

**Bước 5: Tiền combo bắp nước**
3 combo × 75.000 = **225.000 đồng** (combo không được giảm giá)

**Bước 6: Tổng tiền cuối cùng**
Tiền vé sau giảm + tiền combo = 748.800 + 225.000 = **973.800 đồng**

[RESULT: 973.800 đồng]
```

**Link trò chuyện:** https://claude.ai/share/6d8f803f-ceda-40aa-add7-0b59aa1e8087

### b) Kiểm tra kết quả AI

AI trả lời đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "loi_ky_thuat", "so_khach": 4, "so_suat_bi_loi": 2, "tom_tat": "Cả hai suất phim liên tiếp tại phòng 3 bị mất tiếng giữa phim hơn 15 phút; khách yêu cầu giải quyết."}
```

**Link trò chuyện:** https://claude.ai/share/4b43e8ed-2b22-4c6b-9bd7-9b3662b03cb8

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
|---|---|---|---|
| **1. Độ chính xác thông tin (5đ)** | **1/5** | **Sai chính sách huỷ vé:** bài viết nói "huỷ trước 2 tiếng vẫn được hoàn 50%". Theo chuẩn, huỷ dưới 3 giờ thì **không hoàn tiền**. Hoàn 50% chỉ áp dụng khi huỷ trước giờ chiếu từ 3 giờ đến dưới 24 giờ. Sai này có thể khiến khách hiểu nhầm và gây khiếu nại. **Giá 80k:** rubric không cung cấp bảng giá chuẩn nên không thể xác nhận. Con số này cần đối chiếu với bảng giá chính thức. Bài cũng không nêu rõ giá áp dụng cho suất nào, ngày thường hay cuối tuần. | Nêu đủ ba mốc: từ 24 giờ trở lên hoàn 100%, từ 3 giờ đến dưới 24 giờ hoàn 50%, dưới 3 giờ không hoàn tiền. Đối chiếu giá 80k với bảng giá chuẩn và ghi rõ điều kiện áp dụng. |
| **2. Độ đầy đủ (3đ)** | **1/3** | Có đề cập giá vé 2D và chính sách huỷ, nhưng chính sách huỷ chỉ nêu một mốc (và là mốc sai), thiếu hai mốc còn lại. **Không mời khách cung cấp ngày chiếu, suất chiếu, số lượng vé** để đặt chỗ. Câu "Cần gì nhắn em nha!" chung chung, không dẫn dắt khách đặt vé. | Thêm câu mời đặt chỗ, ví dụ: "Anh vui lòng cho em biết ngày chiếu, suất chiếu và số lượng vé để em hỗ trợ đặt chỗ ạ." |
| **3. Văn phong (2đ)** | **0.5/2** | Dùng nhiều từ suồng sã, không phù hợp tư vấn chuyên nghiệp: "rẻ xỉu", "thôi nè", "nha anh", "Hi anh!". Xưng hô thân mật quá mức, thiếu từ kính ngữ như "dạ", "ạ". Điểm cộng nhỏ: thái độ thân thiện, có xưng hô rõ ràng. | Bỏ "rẻ xỉu", "nè", "nha". Mở đầu bằng "Dạ, Rạp Ánh Dương xin chào anh ạ" và kết bằng "Rất mong được phục vụ anh ạ". |

**Tổng điểm: 2.5/10** (1 + 1 + 0.5)

**Lỗi nghiêm trọng nhất:** thông tin sai về hoàn tiền khi huỷ dưới 3 giờ. Đây là lỗi nội dung, không chỉ lỗi trình bày.

**Bản sửa đề xuất:**
> Dạ, Rạp Ánh Dương xin chào anh ạ. Vé 2D hiện có giá 80.000đ [bổ sung điều kiện áp dụng nếu có]. Về chính sách huỷ vé: huỷ trước giờ chiếu từ 24 giờ trở lên được hoàn 100%; huỷ từ 3 giờ đến dưới 24 giờ được hoàn 50%; huỷ dưới 3 giờ không được hoàn tiền ạ. Anh vui lòng cho em biết ngày chiếu, suất chiếu và số lượng vé để em hỗ trợ đặt chỗ nhé. Em cảm ơn anh ạ.

Lưu ý: đề không cho biết câu hỏi gốc của khách và bảng giá chuẩn, nên tôi chấm độ đầy đủ dựa trên rubric và để giá ở trạng thái chưa xác nhận được.
```

**Link trò chuyện:** https://claude.ai/share/1fe09235-8107-466f-9e4b-fb2076951e77
