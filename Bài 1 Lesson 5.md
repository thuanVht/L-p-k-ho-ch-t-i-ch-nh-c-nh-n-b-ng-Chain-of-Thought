# Prompt lập kế hoạch tài chính bằng CoT (bản gọn)

```
# VAI TRÒ
Bạn là chuyên gia tư vấn tài chính cá nhân, tính toán chính xác và minh bạch.

# DỮ LIỆU ĐẦU VÀO (triệu VNĐ/tháng)
- Thu nhập 3 tháng gần nhất: {T1}; {T2}; {T3}
- Thuế/bảo hiểm: {x}% thu nhập
- Chi phí cố định: {liệt kê từng khoản}
- Nợ trả tối thiểu: {liệt kê từng khoản}
- Mục tiêu tiết kiệm: tối thiểu 20% thu nhập bình quân (gồm quỹ dự phòng)

# NHIỆM VỤ
Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định.

# QUY TRÌNH
Bước 0: Thu nhập cơ sở = (T1 + T2 + T3) / 3.
Bước 1: Khả dụng = Thu nhập cơ sở − Thuế/BH − Chi phí cố định.
Bước 2: Còn lại = Khả dụng − Nợ trả tối thiểu.
Bước 3: Tiết kiệm = 20% × Thu nhập cơ sở (chia dự phòng và tích lũy). Còn lại = Bước 2 − Tiết kiệm.
Bước 4: Chia phần còn lại theo 50/30/20: 50% thiết yếu, 30% cá nhân, 20% trả nợ thêm.

# QUY TẮC
- Mỗi phép tính một dòng: công thức, thay số, kết quả. Không nhảy cóc.
- Sau mỗi bước ghi "Kiểm tra" bằng phép tính ngược.
- Nếu có số âm, dừng lại, nêu số thiếu và đề xuất điều chỉnh.
- Tỷ lệ % tính trên thu nhập cơ sở, tổng phải đúng 100%. Nếu lệch do làm tròn, chỉnh ở hạng mục lớn nhất.

# ĐỊNH DẠNG
Phần 1: Nhật ký suy luận (Bước 0 đến Bước 4).
Phần 2: Bảng Markdown | Hạng mục | Số tiền | Tỷ lệ % | Ghi chú | có dòng TỔNG CỘNG = 100%.
```

## Chạy thử

Dữ liệu: thu nhập 24, 30, 36 triệu. Thuế/BH 10%. Chi phí cố định: nhà 6, điện nước và internet 1,5, đi lại 1,5. Nợ tối thiểu: thẻ 1,2 và vay tiêu dùng 1,8.

### Phần 1: Nhật ký suy luận

- **Bước 0**: (24 + 30 + 36) / 3 = 90 / 3 = **30**
- **Bước 1**: thuế 30 × 10% = 3. Cố định 6 + 1,5 + 1,5 = 9. Khả dụng 30 − 3 − 9 = **18**. Kiểm tra: 18 + 3 + 9 = 30 ✓
- **Bước 2**: nợ 1,2 + 1,8 = 3. Còn lại 18 − 3 = **15**. Kiểm tra: 15 + 3 = 18 ✓
- **Bước 3**: tiết kiệm 30 × 20% = 6 (dự phòng 3, tích lũy 3). Còn lại 15 − 6 = **9**. Kiểm tra: 9 + 6 = 15 ✓
- **Bước 4**: thiết yếu 9 × 50% = 4,5. Cá nhân 9 × 30% = 2,7. Trả nợ thêm 9 × 20% = 1,8. Kiểm tra: 4,5 + 2,7 + 1,8 = 9 ✓

### Phần 2: Bảng phân bổ

| Hạng mục | Số tiền (triệu) | Tỷ lệ % | Ghi chú |
|---|---|---|---|
| Thuế và bảo hiểm | 3,0 | 10,00% | Khấu trừ 10% |
| Chi phí cố định | 9,0 | 30,00% | Nhà, điện nước, đi lại |
| Nợ trả tối thiểu | 3,0 | 10,00% | Thẻ 1,2 + vay 1,8 |
| Quỹ dự phòng | 3,0 | 10,00% | Một nửa khoản tiết kiệm |
| Tiết kiệm tích lũy | 3,0 | 10,00% | Một nửa khoản tiết kiệm |
| Thiết yếu linh hoạt | 4,5 | 15,00% | 50% phần còn lại |
| Chi tiêu cá nhân | 2,7 | 9,00% | 30% phần còn lại |
| Trả nợ thêm | 1,8 | 6,00% | 20% phần còn lại |
| **TỔNG CỘNG** | **30,0** | **100,00%** | Khớp thu nhập cơ sở |

Tiết kiệm = 6 / 30 = 20%, đạt mức tối thiểu.

**Lưu ý khi nộp bài**: nêu rõ giả định tiết kiệm tính trên thu nhập trước thuế. Nếu muốn an toàn hơn với thu nhập biến động, đổi Bước 0 sang dùng tháng thấp nhất.
