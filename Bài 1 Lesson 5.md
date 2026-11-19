# **Lập kế hoạch tài chính cá nhân bằng Chain-of-Thought**

## **1. Mục tiêu**

Luyện tập tư duy suy luận logic phức tạp của AI bằng kỹ thuật Chain-of-Thought (CoT).

Biết cách kiểm soát các bước lập luận trung gian để hạn chế sai sót tính toán số học của LLM.

Cấu trúc kết quả đầu ra trực quan gồm cả phần phân tích logic và bảng tổng hợp số liệu.

## **2. Bối cảnh bài toán**

Một cá nhân có thu nhập biến động mỗi tháng và đang có một số khoản nợ cần thanh toán. Họ cần một trợ lý AI thông minh lập kế hoạch tài chính chi tiết, tối ưu hóa dòng tiền và đưa ra đề xuất phân bổ ngân sách chi tiêu hợp lý.

Do bài toán liên quan đến nhiều phép tính số học và ràng buộc tài chính (tiết kiệm tối thiểu 20%, trả nợ đúng hạn, quỹ dự phòng), nếu để AI trả lời ngay đáp án sẽ rất dễ bị sai lệch số liệu.

## **3. Yêu cầu**

Thiết kế prompt yêu cầu AI lập kế hoạch tài chính hàng tháng từ dữ liệu đầu vào gồm: Thu nhập, Chi phí cố định, Các khoản nợ, Mục tiêu tiết kiệm.

Yêu cầu AI thực hiện suy luận từng bước (Chain-of-Thought) để tính toán ngân sách trước khi xuất kết quả cuối cùng.

## **4. Quy tắc xử lý**

Kích hoạt Chain-of-Thought bằng chỉ thị tường minh: 'Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định'.

Vạch ra quy trình lập luận gồm các bước:

- Bước 1: Tính toán tổng thu nhập khả dụng sau khi trừ thuế và chi phí cố định bắt buộc.

- Bước 2: Phân bổ khoản tiền trả nợ tối thiểu.

- Bước 3: Trích lập quỹ tiết kiệm theo tỷ lệ cam kết.

- Bước 4: Chia phần còn lại cho chi tiêu linh hoạt theo quy tắc 50/30/20 cải tiến.

## **5. Yêu cầu xử lý dữ liệu**

Trình bày kết quả lập luận thành hai phần rõ rệt:

- Phần 1: Nhật ký suy luận logic (Reasoning Steps) chỉ ra công thức tính toán và số liệu trung gian.

- Phần 2: Bảng phân bổ ngân sách cuối cùng bằng Markdown Table với các cột: Hạng mục, Số tiền, Tỷ lệ %, Ghi chú.

## **6. Ràng buộc kỹ thuật**

Bắt buộc hiển thị đầy đủ phép tính cộng trừ nhân chia trung gian, không nhảy cóc ra kết quả.

Đảm bảo tổng tỷ lệ phần trăm phân bổ ngân sách phải bằng chính xác 100%.

Không dùng Pydantic hay code Python, thực hiện hoàn toàn bằng kỹ năng Prompting logic.
