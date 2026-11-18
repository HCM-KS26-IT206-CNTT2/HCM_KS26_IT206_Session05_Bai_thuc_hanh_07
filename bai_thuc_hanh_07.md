**Prompt 1:**
```
# Context:
Bạn là chuyên gia tổ chức sự kiện sinh viên. BƯỚC 1/5 của chuỗi lập kế hoạch.
{{khoi_thong_tin_co_dinh}}

# Request:
Thực hiện lần lượt: (Việc 1) Phân tích tính khả thi. (Việc 2) Xây dựng lịch trình một ngày theo khung giờ, dựa đúng trên kết luận Việc 1.

# Explanation:
Kết quả là nền tảng cho ngân sách, phân công, truyền thông nên mọi con số phải có công thức.

# Action:
Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi kết luận:
Việc 1:
B1: Ngân sách mỗi người = 15.000.000 / 150.
B2: Tỷ lệ nhân sự = 150 / 10.
B3: Đối chiếu mục tiêu "hiểu và trải nghiệm AI" với quy mô, thời gian: cần hình thức nghe và thực hành.
B4: Liệt kê nguồn lực đề chưa cung cấp (địa điểm, Wi-Fi, diễn giả), gắn nhãn "giả định cần xác nhận".
B5: 5 đến 6 rủi ro (khả năng, ảnh hưởng, giảm thiểu).
B6: Kết luận: Khả thi / Khả thi có điều kiện / Không khả thi.
Việc 2:
B7: Sắp xếp hạng mục theo khung giờ, cộng kiểm tra tổng thời lượng.
B8: Chia nhóm hoạt động sao cho tổng đúng 150 sinh viên.
B9: Ghi rõ số diễn giả, số đợt giải lao, có hay không có bữa ăn (để tính tiền ở bước sau).
Xử lý lỗi: nếu kết luận "Không khả thi", dừng và nêu điều kiện cần sửa.

# Tone:
Khách quan, rõ ràng.

# Extras:
PHẦN 1 PHÂN TÍCH KHẢ THI: chỉ số (kèm công thức) | nguồn lực và giả định | bảng rủi ro | kết luận.
PHẦN 2 LỊCH TRÌNH: bảng Giờ | Thời lượng | Hạng mục | Nội dung | Ghi chú chi phí; cuối bảng ghi số diễn giả, số đợt giải lao, số nhóm.
```

**Prompt 2:**
```
# Context:
Bạn là trưởng ban tổ chức kiêm thủ quỹ. BƯỚC 2/5.
{{khoi_thong_tin_co_dinh}}
PHÂN TÍCH KHẢ THI + LỊCH TRÌNH: {{output_prompt_1}}

# Request:
Thực hiện lần lượt: (Việc 1) Lập dự toán ngân sách, không vượt 15.000.000đ. (Việc 2) Phân công đúng 10 nhân sự.

# Explanation:
Mỗi khoản chi truy về một hạng mục trong LỊCH TRÌNH; mỗi hạng mục chi phí phải có người phụ trách trong bảng phân công.

# Action:
Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi kết luận:
Việc 1:
B1: Liệt kê hạng mục phát sinh chi phí từ LỊCH TRÌNH.
B2: Số người hưởng dịch vụ = 150 + 10 + số diễn giả.
B3: Mỗi khoản = số lượng × đơn giá (đơn giá là giả định, ghi công thức).
B4: Cộng tổng, dự phòng khoảng 5%.
B5: Kiểm tra tổng ≤ 15.000.000đ; mọi hạng mục cần tiền trong lịch đều có khoản chi.
B6: Nếu vượt: cắt khoản ít phục vụ mục tiêu trải nghiệm AI, ghi rõ và tính lại.
Việc 2:
B7: Chia đúng 10 người (đếm lại tổng), mỗi người có nhiệm vụ trước và trong sự kiện.
B8: Mỗi hạng mục ngân sách có người phụ trách; không ai quá tải cùng khung giờ.
Xử lý lỗi: thiếu LỊCH TRÌNH thì ghi "DỪNG: thiếu dữ liệu".

# Tone:
Chính xác, minh bạch.

# Extras:
PHẦN 1: nhật ký tính toán, rồi bảng DỰ TOÁN (Hạng mục | Công thức | Thành tiền | % ngân sách | Ghi chú), dòng cuối Tổng chi và Còn lại.
PHẦN 2: bảng PHÂN CÔNG (STT | Vai trò | Nhiệm vụ trước | Nhiệm vụ trong sự kiện | Ngân sách phụ trách), cuối ghi "Tổng: 10 người".
```

**Prompt 3:**
```
# Context:
Bạn là chuyên viên truyền thông của câu lạc bộ. BƯỚC 3/5.
{{khoi_thong_tin_co_dinh}}
LỊCH TRÌNH: {{lich_trinh_tu_output_1}}
DỰ TOÁN + PHÂN CÔNG: {{output_prompt_2}}

# Request:
Xây dựng kế hoạch truyền thông trước sự kiện để lấp đủ 150 chỗ.

# Explanation:
Chi phí không vượt khoản truyền thông trong DỰ TOÁN, người thực hiện phải nằm trong PHÂN CÔNG, nội dung đúng chương trình trong LỊCH TRÌNH.

# Action:
Hãy suy nghĩ từng bước:
1. Thông điệp chính bám mục tiêu của sự kiện.
2. Chia mốc trước ngày sự kiện (T-n): gây chú ý, mở đăng ký, nhắc lịch, xác nhận.
3. Mỗi mốc: kênh, nội dung, người phụ trách, chi phí, chỉ số.
4. Giới hạn đăng ký 150 chỗ, có danh sách chờ, không mở rộng quy mô.
Không bịa ưu đãi hoặc chi phí ngoài DỰ TOÁN.

# Tone:
Trẻ trung, rõ ràng, phù hợp sinh viên.

# Extras:
Thông điệp chính + bảng: Mốc | Kênh | Nội dung | Người phụ trách | Chi phí | Chỉ số.
```

**Prompt 4:**
```
# Context:
Bạn là chuyên gia kiểm duyệt kế hoạch sự kiện. BƯỚC 4/5.
{{khoi_thong_tin_co_dinh}}
KHẢ THI + LỊCH TRÌNH: {{output_prompt_1}}
DỰ TOÁN + PHÂN CÔNG: {{output_prompt_2}}
TRUYỀN THÔNG: {{output_prompt_3}}

# Request:
Kiểm tra tính thống nhất, phát hiện vấn đề và hiệu chỉnh kế hoạch.

# Explanation:
Các hạng mục tạo ở nhiều bước nên dễ mâu thuẫn. Mọi sửa đổi không được đổi 150 SV, 10 nhân sự, 15.000.000đ.

# Action:
Hãy suy nghĩ từng bước, kiểm tra từng tiêu chí, ghi Đạt/Không đạt kèm dẫn chứng:
1. Thông tin cố định không bị đổi.
2. Tính lại tổng ngân sách bằng phép cộng, so với 15.000.000đ.
3. LỊCH TRÌNH và DỰ TOÁN khớp hai chiều.
4. PHÂN CÔNG đủ 10 người, mỗi hạng mục có người phụ trách.
5. TRUYỀN THÔNG: chi phí trong dự toán, người thực hiện có trong phân công, giới hạn 150 chỗ.
6. Rủi ro ở bước khả thi đều có biện pháp.
Với mỗi lỗi: nêu vị trí, cách sửa; xuất phần hiệu chỉnh và tính lại ngân sách.

# Tone:
Khách quan, cụ thể.

# Extras:
BÁO CÁO KIỂM TRA (Tiêu chí | Kết quả | Dẫn chứng); BẢNG LỖI VÀ HIỆU CHỈNH (Lỗi | Vị trí | Cách sửa | Trước | Sau); KẾT LUẬN "ĐẠT" hoặc "CẦN SỬA Ở BƯỚC _".
```

**Prompt 5:**
```
# Context: 
Bạn là trợ lý lập kế hoạch AI Innovation Day. Đây là hội thoại mới, chỉ dùng thông tin trong bản tóm tắt sau, không bịa thêm.
TÓM TẮT NGỮ CẢNH: {{ban_tom_tat}}
Việc cần làm tiếp: {{viec_can_lam}}
Hãy suy nghĩ từng bước, xác nhận lại ràng buộc cố định (150 SV, 10 nhân sự, 15.000.000đ), chỉ cập nhật phần bị ảnh hưởng, tính lại ngân sách ≤ 15.000.000đ. Nếu yêu cầu mâu thuẫn với ràng buộc cố định, nêu rõ và dừng.

# Request:
Tạo bản tóm tắt ngữ cảnh tối đa 300 từ, đủ để hội thoại mới tiếp tục ngay.

# Explanation:
Hội thoại mới không có lịch sử, nên phải giữ nguyên ràng buộc cứng, số liệu đã chốt và việc còn dang dở.

# Action: 
1. Giữ nguyên văn các ràng buộc cố định.
2. Tóm tắt từng phần bằng số liệu then chốt.
3. Ghi quyết định đã hiệu chỉnh, giả định chưa xác nhận, việc tiếp theo.
4. Không thêm thông tin mới.

# Tone:
Cô đọng, chính xác.

# Extras:
TÓM TẮT NGỮ CẢNH gồm: 1. Ràng buộc cố định | 2. Kết quả đã chốt | 3. Quyết định đã hiệu chỉnh | 4. Giả định chưa xác nhận | 5. Việc tiếp theo.
```

**Dữ liệu test:**
```
THÔNG TIN SỰ KIỆN (CỐ ĐỊNH, KHÔNG ĐƯỢC THAY ĐỔI):
- Tên sự kiện: AI Innovation Day, do câu lạc bộ công nghệ tổ chức cho sinh viên trong trường
- Quy mô: 150 sinh viên
- Thời gian: 1 ngày
- Ngân sách tối đa: 15.000.000 đồng
- Nhân sự tổ chức: 10 người
- Mục tiêu: Giúp sinh viên hiểu và trải nghiệm ứng dụng AI trong học tập và công việc
- Chưa có dữ liệu: {{dia_diem}}, {{ngay_to_chuc}}, {{ten_clb}}, {{link_dang_ky}}
```