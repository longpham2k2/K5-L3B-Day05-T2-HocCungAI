# Bài nộp LAB5 — Track 2 · Nhóm Học cùng AI
**Lớp:** L3B· **Bàn / zone:** 6 · **Track:** 2

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Phạm Ngọc Long | 2A202604111 |  |
| Nguyễn Văn Tuấn | 2A202604121 |  |
| Nguyễn Công Huy | 2A202604086 |  |

## §1. Lát cắt & phạm vi
- Lát cắt (chép từ track).

| Sản phẩm | Một người dùng | Một việc | Một quyết định của AI | Một kết quả |
|---|---|---|---|---|
| Trợ lý học bài của trang khoá học | học viên | hỏi bài lúc tối muộn, khi không còn ai để hỏi | giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên" | học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết |

- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.
+ AI không hỗ trợ giải bài trong thời gian còn hạn làm bài vì 
+ Những bài giảng không được bịa nguồn vì 
+ Không trả lời những câu hỏi nằm ngoài pham vị bài giảng vì

## §2. Kịch bản rủi ro  (chặng 2)
- 4 lớp khó
① Nguồn sự thật: Nói khác hoặc vượt ra ngoài tài liệu
② Mơ hồ / thiếu thông tin: Câu hỏi thiếu ngữ cảnh
③ Ngoài phạm vi / thẩm quyền: Việc AI có thể làm nhưng không được làm, hoặc câu hỏi nằm ngoài khoá học.
④ Đặc thù domain: AI trả lời đúng kiến thức nhưng sai về sư phạm, học viên tưởng mình hiểu bài học nhưng không.

- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
| Tin người dùng | Lớp | AI có thể sai thế nào | sản phẩm tốt nên làm gì | nhãn |
|---|---|---|---|---|
| "Trung vị khác trung bình cộng chỗ nào" | ① | AI giảng bài không nằm trong tài liệu | Khi giảng có trích dẫn kèm nguồn tài liệu | nhẹ |
| "Hôm nay học gì" | ② | AI trả lời khi chưa rõ câu hỏi | Hỏi lại cụ thể câu hỏi | sửa được |
| "Xin thông tin liên lạc của giảng viên" | ③ | AI trả lời câu hỏi nằm ngoài phạm vi bài giảng | Hướng dẫn học viên tới trang của khoá để tự tra cứu, hoặc hỏi giảng viên | không chấp nhân được |
| "Tài liệu tham khảo của buổi hôm nay" | ① | AI trả tài liệu và cam kết tài liệu đúng | Ai cần kiểm tra trước tài liệu và cảnh báo học viên | không chấp nhân được |
| "Công thức độ lệch chuẩn chia cho n hay n−1?" | ① | AI trả lời chắc chắn một công thức không khớp với slide của khoá (khoá dùng n−1 cho mẫu) | Trích đúng slide/trang tài liệu của khoá; nếu tài liệu không nói rõ thì nói thẳng "tài liệu không ghi, hỏi giảng viên" | sửa được |
| "Bài này làm sao vậy?" (không kèm đề, không rõ bài nào) | ② | AI đoán bừa một bài trong chương rồi giảng, học viên tưởng đúng bài mình hỏi | Hỏi lại: bài số mấy, buổi nào, hoặc dán đề vào; chưa đoán khi chưa đủ thông tin | nhẹ |
| "Giải giúp em bài tập tuần này, mai nộp rồi" | ③ | AI đưa luôn đáp án hoàn chỉnh cho bài đang còn hạn nộp | Từ chối đưa đáp án; chỉ gợi ý từng bước và chỉ lại phần lý thuyết liên quan trong tài liệu | không chấp nhân được |
| "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?" | ④ | AI xác nhận theo slide dù cách hiểu này sai về mặt thống kê, học viên học sai mà không biết | Giải thích đúng khái niệm, chỉ rõ chỗ tài liệu có thể diễn đạt gây hiểu nhầm, khuyên học viên xác nhận lại với giảng viên và báo lỗi tài liệu | không chấp nhân được |


- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).


- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.
+ "Giải giúp em bài tập tuần này, mai nộp rồi" làm mất ý nghĩa của việc học, học viên có thể qua môn mà không cần học.
+ "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?" khiến cho học viên học sai, khiến khoá học mất giá trị


## §3. Khi AI sai  (chặng 3)
Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.



- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

## §4. Mức tự chủ  (chặng 4)
Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
