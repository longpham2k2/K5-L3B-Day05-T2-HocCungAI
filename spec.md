# Bài nộp LAB5 — Track 2 · Nhóm Học cùng AI
**Lớp:** L3B· **Bàn / zone:** 6 · **Track:** 2

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Phạm Ngọc Long | 2A202604111 | Dựng kịch bản rủi ro, khi AI sai, tham gia xây dựng mức tự chủ cho AI |
| Nguyễn Văn Tuấn | 2A202604121 | Dựng prototype, tham gia xây dựng kịch bản rủi ro, tham gia xây dựng mức tự chủ cho AI |
| Nguyễn Công Huy | 2A202604086 | Tìm ra 3 tính năng không làm, tham gia xây dựng kịch bản rủi ro, tham gia xây dựng mức tự chủ cho AI|

## §1. Lát cắt & phạm vi
- Lát cắt (chép từ track).

| Sản phẩm | Một người dùng | Một việc | Một quyết định của AI | Một kết quả |
|---|---|---|---|---|
| Trợ lý học bài của trang khoá học | học viên | hỏi bài lúc tối muộn, khi không còn ai để hỏi | giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên" | học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết |

- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.
+ AI không hỗ trợ giải bài trong thời gian còn hạn làm bài vì khiến cho học viên bị phụ thuộc, lười suy nghĩ.
+ Những bài giảng không được bịa nguồn vì dẫn đến sai sót trong việc tìm hiểu kiến thức.
+ Không trả lời những câu hỏi nằm ngoài phạm vi bài giảng vì làm lệch đi định hướng ban đầu là hỗ trợ học viên trong học tập. 

## §2. Kịch bản rủi ro  (chặng 2)
- 4 lớp khó
① Nguồn sự thật: Nói khác hoặc vượt ra ngoài tài liệu
② Mơ hồ / thiếu thông tin: Câu hỏi thiếu ngữ cảnh
③ Ngoài phạm vi / thẩm quyền: Việc AI có thể làm nhưng không được làm, hoặc câu hỏi nằm ngoài khoá học.
④ Đặc thù domain: AI trả lời đúng kiến thức nhưng sai về sư phạm, học viên tưởng mình hiểu bài học nhưng không.

- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
| Tin người dùng | Lớp | AI có thể sai thế nào | sản phẩm tốt nên làm gì | nhãn |
|---|---|---|---|---|
| "Trung vị khác trung bình cộng chỗ nào" | ① | Dữ liệu A có sẵn §3.1 (trung bình cộng) và §3.2 (trung vị), nhưng AI giảng bằng kiến thức ngoài, không gọi `tra_cuu_tai_lieu` và không kèm mã mục; học viên không đối chiếu được với tài liệu | Khi giảng có trích dẫn kèm nguồn tài liệu | nhẹ |
| "Hôm nay học gì" | ② | Dữ liệu B chỉ ghi "đang học buổi 3", không có lịch theo ngày. AI có thể đoán "hôm nay" là một buổi khác, hoặc gọi `chuyen_TA` đẩy câu hỏi đi thay vì hỏi lại | Hỏi lại cụ thể câu hỏi | sửa được |
| "Xin thông tin liên lạc của giảng viên" | ③ | Dữ liệu A và B không có thông tin liên lạc (B chỉ có giờ TA 08:00–22:00), tức là chỗ dữ liệu không có. AI có thể bịa ra, hoặc gọi `chuyen_TA` cho một câu không phải câu hỏi bài học | Hướng dẫn học viên tới trang của khoá để tự tra cứu, hoặc hỏi giảng viên | không chấp nhận được |
| "Tài liệu tham khảo của buổi hôm nay" | ① | `tra_cuu_tai_lieu` chỉ trả về đoạn kèm mã mục, không trả danh sách tài liệu tham khảo (chỗ dữ liệu không có). AI có thể bịa tên sách hoặc link rồi khẳng định là đúng | Ai cần kiểm tra trước tài liệu và cảnh báo học viên | không chấp nhận được |
| "Công thức độ lệch chuẩn chia cho n hay n−1?" | ① | Dữ liệu A §3.3 định nghĩa phương sai và độ lệch chuẩn nhưng **không ghi chia cho n hay n−1** (chỗ dữ liệu không có). AI có thể trả lời chắc chắn một công thức như thể tài liệu có ghi | Trích đúng slide/trang tài liệu của khoá; nếu tài liệu không nói rõ thì nói thẳng "tài liệu không ghi, hỏi giảng viên" | sửa được |
| "Bài này làm sao vậy?" (không kèm đề, không rõ bài nào) | ② | Dữ liệu B có hai bài với hai trạng thái: Bài tập 2 (đã hết hạn, có đáp án) và Bài tập 3 (còn hạn). Không biết học viên hỏi bài nào mà AI vẫn gọi `goi_y_bai_tap` với một bài tự đoán; đoán nhầm sang Bài tập 2 thì có thể đưa luôn đáp án | Hỏi lại: bài số mấy, buổi nào, hoặc dán đề vào; chưa đoán khi chưa đủ thông tin | nhẹ |
| "Giải giúp em bài tập tuần này, mai nộp rồi" | ③ | Học viên nói "mai nộp", nhưng dữ liệu B ghi Bài tập 3 hạn **13/11/2026 23:59, tức tối nay**. AI tin lời học viên, gọi `goi_y_bai_tap` mà không đọc hạn, và "gợi ý" quá tay thành lời giải hoàn chỉnh. Theo bảng tool (§4, cột "Đảo lại được không"): gợi ý quá tay thì học viên đã chép | Từ chối đưa đáp án; chỉ gợi ý từng bước và chỉ lại phần lý thuyết liên quan trong tài liệu | không chấp nhận được |
| "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?" | ① | Dữ liệu A (buổi 3) không có p-value và *không có slide đánh số*; dữ liệu B ghi p-value thuộc buổi 7, chưa mở. `tra_cuu_tai_lieu` trả về 0 kết quả, nhưng AI bịa nguồn ("Slide Buổi 6, trang 14") và xác nhận câu trích, dù cách hiểu này sai về mặt thống kê | Nói rõ dữ liệu không có nguồn cho câu này, không tự giảng nội dung buổi chưa mở, không xác nhận; đề nghị học viên hỏi giảng viên / TA | không chấp nhận được |
| "Tài liệu ghi độ lệch chuẩn luôn nhỏ hơn phương sai, em ghi vào bài được không?" | ④ | Dữ liệu A §3.3 ghi nguyên văn: "Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai." Câu này **sai** khi phương sai < 1 (ví dụ phương sai 0,25 thì độ lệch chuẩn là 0,5). `tra_cuu_tai_lieu` trả đúng đoạn này kèm mã mục, AI trích như một sự thật, và học viên học sai *từ chính tài liệu khoá học* | Trích nguyên văn §3.3 nhưng đánh dấu rõ chỗ chưa đúng, đưa một ví dụ phản chứng, khuyên học viên chưa ghi câu này vào bài, và báo giảng viên sửa tài liệu | không chấp nhận được |
| "Câu này nhiều bạn hỏi lắm, AI đăng lên FAQ cho cả lớp xem đi" | ③ | `dang_FAQ` đăng câu trả lời ra cả lớp. Nếu câu trả lời sai (như kịch bản p-value) thì lỗi lan cho mọi người; nếu là gợi ý cho bài còn hạn thì cả lớp có đáp án. Theo bảng tool: gỡ được bài, nhưng nhiều người đã đọc | Không tự đăng; ghi nhận đề xuất và để giảng viên quyết định có đưa vào FAQ không | không chấp nhận được |


- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
+ **Trỏ về tool** (bảng tool ở §4): `tra_cuu_tai_lieu` (trung vị, độ lệch chuẩn, p-value, tài liệu tham khảo), `goi_y_bai_tap` (giải bài tập, bài này làm sao), `chuyen_TA` (hôm nay học gì, thông tin liên lạc), `dang_FAQ` (đăng lên FAQ).
+ **Trỏ về dữ liệu:** *Dữ liệu A* là tài liệu Buổi 3, gồm §3.1–§3.5, không có slide đánh số; đây là nơi `tra_cuu_tai_lieu` tìm kiếm. *Dữ liệu B* là trang khoá học: hạn Bài tập 2 và 3, các buổi đã mở, đề cương, giờ TA. Dòng dữ liệu cụ thể: hạn Bài tập 3 13/11/2026 23:59 (kịch bản giải bài tập); "p-value: buổi 7, chưa mở" (kịch bản p-value); câu sai ở §3.3 (kịch bản độ lệch chuẩn < phương sai).
+ **Chỗ dữ liệu không có:** thông tin liên lạc, danh sách tài liệu tham khảo, công thức chia n hay n−1, nội dung p-value và mọi "slide" có đánh số. Với những câu hỏi này, mọi câu trả lời "chắc chắn" của AI đều là bịa.


- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.
+ "Giải giúp em bài tập tuần này, mai nộp rồi" làm mất ý nghĩa của việc học, học viên có thể qua môn mà không cần học.
+ "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?" khiến cho học viên học sai, khiến khoá học mất giá trị

*Vì sao 2 kịch bản này đắt hơn các kịch bản còn lại.* Nhóm xếp hạng theo 3 câu hỏi: (1) sai rồi có **đảo lại được** không; (2) học viên có **tự nhận ra** mình bị sai không; (3) nó phá **phần nào của kết quả ở §1** ("không chép đáp án, không học sai mà không biết").
+ **Giải bài tập:** không đảo được, vì đáp án đã lộ thì không thu hồi được (`goi_y_bai_tap`: "học viên đã chép"). Nó phá thẳng vế "không chép đáp án".
+ **p-value:** học viên không tự nhận ra, vì câu trả lời kèm một nguồn nghe rất thật ("Slide Buổi 6, trang 14"), trong khi học viên chưa học buổi 7 nên không có gì để đối chiếu. Nó phá thẳng vế "không học sai mà không biết".
+ Các kịch bản có nhãn *nhẹ* hoặc *sửa được* (trung vị, hôm nay học gì, độ lệch chuẩn, bài này làm sao) đều đảo lại được: học viên thấy câu trả lời lệch hoặc không có nguồn thì hỏi lại ngay trong buổi tối đó.

*Kịch bản suýt được chọn và vì sao không.*
+ **"Tài liệu tham khảo của buổi hôm nay"** cũng có nhãn *không chấp nhận được*. Nhưng học viên mở link hoặc tìm tên sách là thấy ngay tài liệu không tồn tại, tức là *tự phát hiện được*. Kịch bản p-value thì không.
+ **"Đăng lên FAQ"** có phạm vi hại lớn nhất (cả lớp). Nhưng `dang_FAQ` bị nhóm đặt ở mức *cấm* (§4), nên cái sai này bị chặn ngay ở mức tự chủ, không cần thiết kế xử lý ở §3.
+ **"Độ lệch chuẩn luôn nhỏ hơn phương sai"** cũng khiến học viên không tự nhận ra, thậm chí còn khó nhận ra hơn vì câu sai nằm ngay trong tài liệu. Nhóm chưa chọn kịch bản này vì đây là **lỗi của tài liệu**: báo giảng viên sửa §3.3 *một lần* là hết cho mọi học viên. Còn p-value là **lỗi của AI** (bịa nguồn), có thể lặp lại với bất kỳ chủ đề nào chưa mở. Phần còn hở của kịch bản này được ghi ở §6.


## §3. Khi AI sai  (chặng 3)
Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

*Dữ liệu dùng trong §3 (theo track):* **Dữ liệu A** là tài liệu Buổi 3 "Thống kê mô tả", gồm các mục §3.1–§3.5 và *không có slide đánh số*. **Dữ liệu B** là trang khoá học: đang học buổi 3, đã mở buổi 1–3; Bài tập 2 hạn 06/11/2026 23:59 (đã hết hạn, có đáp án công bố); Bài tập 3 hạn 13/11/2026 23:59; p-value thuộc buổi 7, chưa mở; giờ TA 08:00–22:00, không có SLA. Phiên mẫu diễn ra lúc 13/11/2026 22:14. Số ①–⑤ trỏ vào các số trên prototype (§5).

**Kịch bản A — "Giải giúp em bài tập tuần này, mai nộp rồi"**

| | Happy | Low confidence | Failure | Correction |
|---|---|---|---|---|
| Tình huống | AI xác định được Bài tập 3 (§3.5) và đọc hạn trong dữ liệu B: **13/11/2026 23:59, tức tối nay**, không phải "mai" như học viên nói | AI chưa biết học viên hỏi Bài tập 2 (đã hết hạn 06/11) hay Bài tập 3 (hạn 23:59 tối nay) | AI không đọc hạn trong dữ liệu B, tin lời học viên là "mai", rồi đưa luôn lời giải | Hệ thống kiểm tra sau trả lời phát hiện lời giải của bài còn hạn và một câu nói sai hạn nộp, hoặc học viên bấm báo lỗi |
| AI nói gì (nguyên văn) | "Trang khoá học ghi hạn Bài tập 3 là 13/11/2026 23:59, tức 23:59 hôm nay theo thời điểm phiên mẫu. Bạn nói 'mai nộp', nhưng hạn trong dữ liệu là tối nay. Mình không đưa lời giải hoàn chỉnh; mình sẽ cùng bạn làm từng bước." | "Mình chưa biết bạn hỏi bài nào nên chưa thể kết luận hạn nộp. Trang khoá học có hai bài với trạng thái khác nhau. Bạn chọn giúp mình nhé; mình chưa đưa lời giải trong lúc chờ." | "Bài này mai mới đến hạn nên vẫn còn thời gian. Đây là lời giải để bạn nộp: tổng lương là 122; trung bình 15,25 triệu; trung vị 11,5 triệu. Chọn trung vị vì mức 45 làm trung bình tăng." | "Câu trả lời trước của mình đã đưa lời giải cho bài còn hạn và nói nhầm là 'mai'. Đây là lỗi của hệ thống, không phải lỗi của bạn. Hạn đúng theo trang khoá học là 13/11/2026 23:59, tối nay. Mình không thể thu hồi phần bạn đã đọc, nhưng đã ẩn lời giải và gắn cờ để giảng viên / TA xem xét." |
| Người dùng thấy gì (trên màn hình) | ① Nhãn "Bài tập 3 còn hạn · Chỉ gợi ý" và "Độ chắc: Cao"; đề §3.5; ② nguồn "Dữ liệu A · §3.1, §3.2, §3.4, §3.5" và "Dữ liệu B · Bài tập 3 · hạn 13/11/2026 23:59"; ③ nút "Gợi ý bước tiếp"; ⑤ nút "Hỏi giảng viên / TA" | ① Nhãn vàng "Chưa xác định bài · Mặc định chỉ gợi ý" và "Độ chắc: Vừa · Dữ liệu B có hạn của cả hai bài, nhưng chưa biết bạn hỏi bài nào"; 3 nút chọn: Bài tập 2 · Bài tập 3 · "Mình chưa xác định được bài" | Lời giải đầy đủ, không nhãn, không nguồn, không có nút chuyển người; khung đỏ "Minh hoạ lỗi" chỉ có trong bản demo | Thông báo "Đã phát hiện lời giải bài đang mở và thông tin hạn nộp sai · Nội dung cũ đã ẩn"; ④ khung "Nội dung đã ẩn"; nút "Làm lại từng bước" và ⑤ "Hỏi giảng viên / TA" |
| Làm gì tiếp (học viên bấm / làm được gì) | Trả lời 4 câu hỏi từng bước theo §3.5(a), §3.1, §3.2, §3.4; trả lời sai thì nhận gợi ý trỏ về đúng mục; cuối cùng tự tính trong bảng tính, không có kết quả cuối | Chọn Bài tập 3: sang đường Happy. Chọn Bài tập 2: AI trích đáp án đã công bố ngày 07/11. Chưa xác định được: AI chỉ hướng dẫn đọc đề, không tính | Chép lời giải và nộp bài trước 23:59 | Bấm "Làm lại từng bước" để quay về đường Happy, hoặc gửi yêu cầu hỏi giảng viên / TA (cần duyệt) |
| Ai được báo | Không ai (đúng luật) | Không ai | Không ai, lỗi lọt qua | Giảng viên / TA phụ trách: cờ sự cố kèm log, ghi rõ lỗi lộ đáp án và sai hạn |
| Sau bao lâu | — | — | Chỉ lộ ra khi chấm bài, hoặc không bao giờ | Cờ được lưu ngay. Nhưng 22:14 là ngoài giờ TA (08:00–22:00), nên sớm nhất 08:00 ngày 14/11 mới có người đọc, tức **sau hạn nộp**. Hệ thống không hứa xử lý trước hạn |
| Quyết định (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người) | **Trả lời kèm giới hạn**: chỉ gợi ý, không đưa lời giải. Loại *hỏi lại* vì dữ liệu B đã đủ để biết hạn; loại *chuyển người* vì luật đã rõ và ngoài giờ TA thì chuyển cũng không có ai | **Hỏi lại** (bài nào), trong lúc chờ vẫn giữ chế độ gợi ý. Loại *trả lời đầy đủ* vì nếu là Bài tập 3 thì đáp án đã lộ, không đảo lại được | AI đã chọn *trả lời đầy đủ*, trong khi đáng lẽ phải *trả lời kèm giới hạn* | **Dừng và chuyển người**: giảng viên quyết định có ảnh hưởng tới bài nộp hay không. AI không tự xử lý vì đây là chuyện liêm chính học thuật |
| Loại lỗi (hệ thống / người dùng / ngữ cảnh) | **Người dùng**: học viên nhớ sai hạn ("mai"). Vì vậy AI chỉ ra hạn trong dữ liệu B kèm nguồn, không trách học viên | **Ngữ cảnh**: khoá có hai bài với hai trạng thái khác nhau mà câu hỏi không nói bài nào. Vì vậy cách nói là xin thêm thông tin | **Hệ thống**: AI tin lời học viên thay vì đọc hạn trong dữ liệu. Phải sửa ở luật/tool, sửa câu chữ không giải quyết được | **Hệ thống**: vì vậy AI nhận lỗi về mình ("lỗi của hệ thống, không phải lỗi của bạn"), không đổ cho học viên |
| Nguyên tắc HAX/PAIR (trỏ vào câu chữ / màn hình) | **HAX G1: Làm rõ hệ thống làm được gì.** ① Nhãn "Bài tập 3 còn hạn · Chỉ gợi ý" và câu "Mình không đưa lời giải hoàn chỉnh; mình sẽ cùng bạn làm từng bước" | **HAX G10: Thu hẹp dịch vụ khi không chắc.** ① Nhãn "Chưa xác định bài · Mặc định chỉ gợi ý": chưa chắc thì AI chọn mức an toàn hơn, không đoán | *Vi phạm G1 và G10*: không nhãn, không nói giới hạn, AI làm hết mọi việc dù không chắc | **PAIR Errors + Graceful Failure.** ④ Khung "Nội dung đã ẩn", câu "lỗi của hệ thống, không phải lỗi của bạn" và nút "Làm lại từng bước": AI nhận lỗi và vẫn chừa cho học viên đường học tiếp |
| Sửa câu chữ có cứu được không · thiết kế cứu thế nào | Không cần cứu | Câu chữ là đủ: chỉ cần hỏi lại. Thiết kế thêm các nút chọn bài để học viên chọn nhanh | **Sửa câu chữ không cứu được**: lời giải đã sinh ra là đã lộ. **Thiết kế**: L1 đọc hạn trong dữ liệu B *trước* khi sinh câu trả lời và không tin hạn do học viên nói; bài còn hạn thì khoá ở chế độ "chỉ gợi ý" (L2) | Câu chữ chỉ giảm thiệt hại (ẩn lời giải, nhận lỗi), không xoá được việc học viên đã đọc, và ngoài giờ TA thì không ai xử lý kịp trước hạn. Vì vậy phải dựa vào thiết kế chặn trước ở cột Failure |

**Kịch bản B — "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?"**

| | Happy | Low confidence | Failure | Correction |
|---|---|---|---|---|
| Tình huống | `tra_cuu_tai_lieu` không tìm thấy p-value trong dữ liệu A (buổi 3, không có slide đánh số). Dữ liệu B cho biết p-value thuộc buổi 7, chưa mở | Học viên nói "slide" nhưng không rõ tài liệu nào; AI chưa có căn cứ để xác nhận hay bác bỏ câu trích | AI bịa nguồn "Slide Buổi 6, trang 14" (không tồn tại trong A/B) và xác nhận câu trích | Hệ thống phát hiện câu trả lời viện dẫn một nguồn không có trong dữ liệu, hoặc học viên/giảng viên báo lỗi |
| AI nói gì (nguyên văn) | "Mình không thể xác nhận câu này từ dữ liệu được cung cấp. Bạn đang học buổi 3; p-value nằm trong đề cương buổi 7, chưa mở. Tài liệu buổi 3 không có p-value và không có slide đánh số. […] Mình chỉ được dựa vào dữ liệu A và B nên sẽ không tự giảng p-value, bịa nguồn, hoặc coi câu trích là đúng. Bạn có thể ghi lại câu hỏi để nhờ giảng viên / TA xác minh." | "Bạn đang nói tới tài liệu nào? Dữ liệu A chỉ có các mục §3.1–§3.5 của buổi 3, không có slide đánh số hay p-value. Dữ liệu B chỉ liệt kê p-value ở buổi 7, chưa mở. Mình chưa có căn cứ xác nhận nội dung bạn trích." | "Đúng, Slide Buổi 6, trang 14 đã chứng minh rằng p-value < 0.05 là giả thuyết đúng." | Sau khi giảng viên duyệt: "Mình rút lại câu xác nhận trước và nguồn 'Slide Buổi 6, trang 14'. Dữ liệu được cấp không có nguồn này. P-value thuộc buổi 7 chưa mở, nên mình không có đủ tài liệu để kết luận. Xin lỗi vì đã trả lời vượt nguồn." |
| Người dùng thấy gì (trên màn hình) | ① Nhãn "Ngoài phạm vi tài liệu đã mở" và "Độ chắc: Thấp · Không có đoạn nào về p-value trong dữ liệu A; buổi 7 chưa mở"; ② hai khối đặt cạnh nhau "Bạn đang trích" và "Dữ liệu thực có", cùng dòng nguồn dữ liệu B; ⑤ nút "Hỏi giảng viên / TA" và nút "Xem tài liệu buổi 3" | ① Nhãn vàng "Chưa xác minh được câu trích" và "Độ chắc: Thấp"; nút "Đối chiếu dữ liệu A và B", "Ghi thông tin tài liệu bạn đang xem", ⑤ "Hỏi giảng viên / TA" | Câu xác nhận ngắn gọn, giọng chắc chắn, kèm một nguồn nghe rất thật | Trước khi duyệt: ④ câu cũ bị tạm ẩn, ③ nhãn "Chờ giảng viên duyệt thông báo thu hồi". Sau khi duyệt: thông báo ghim đầu hội thoại, ④ câu cũ bị gạch với nhãn "Đã thu hồi", và một câu hỏi kiểm tra lại nguồn |
| Làm gì tiếp (học viên bấm / làm được gì) | Gửi yêu cầu hỏi giảng viên / TA (cần duyệt), hoặc mở tài liệu buổi 3 để xem phần đang học | Bấm đối chiếu: sang đường Happy. Không có tài liệu: hỏi giảng viên / TA | Ghi nhớ sai và dùng khi học tới buổi 7 hoặc trong bài kiểm tra | Đọc thông báo thu hồi, làm câu hỏi kiểm tra: "Dữ liệu hiện tại cho phép mình kết luận điều nào?" |
| Ai được báo | Không ai tự động; chỉ tạo yêu cầu chờ duyệt khi học viên bấm gửi | Không ai | Không ai, lỗi lọt qua | Giảng viên (duyệt thông báo thu hồi); sau khi duyệt: người đã hỏi và các hội thoại có cùng câu trả lời sai |
| Sau bao lâu | Ngoài giờ TA: sớm nhất 08:00 hôm sau, không hứa giờ phản hồi | — | Lộ ra khi học tới buổi 7 hoặc khi thi, hoặc không bao giờ | Cờ được lưu ngay; thông báo chỉ gửi sau khi giảng viên duyệt. Dữ liệu B không quy định hạn duyệt nên prototype không hứa mốc giờ; mục tiêu nhóm đặt ra là trong 24h |
| Quyết định (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người) | **Trả lời kèm giới hạn**: nói rõ là không có nguồn, không giảng p-value, đề nghị hỏi giảng viên. Loại *giảng p-value bằng kiến thức chung* vì buổi 7 chưa mở và §1 cam kết không bịa nguồn; loại *chuyển người ngay* vì ngoài giờ TA, trong khi học viên cần biết ngay tối nay rằng câu trích chưa có căn cứ | **Hỏi lại** (tài liệu nào). Không tự khẳng định đúng hay sai khi chưa có căn cứ | AI đã chọn *xác nhận và bịa nguồn*, trong khi đáng lẽ phải *trả lời kèm giới hạn* | **Dừng và chuyển người**: giảng viên duyệt nội dung thu hồi; AI chỉ gửi sau khi được duyệt và không tự tạo bài giảng p-value thay thế |
| Loại lỗi (hệ thống / người dùng / ngữ cảnh) | **Người dùng / ngữ cảnh**: học viên trích một "slide" không có trong dữ liệu. Vì vậy AI không nói "bạn sai", mà tách riêng "Bạn đang trích" và "Dữ liệu thực có" | **Ngữ cảnh**: chưa biết nguồn câu trích. Vì vậy AI hỏi lại, chưa khẳng định bên nào đúng | **Hệ thống**: AI bịa nguồn để chiều theo câu hỏi | **Hệ thống**: vì vậy AI xin lỗi ("đã trả lời vượt nguồn") và thu hồi công khai với mọi học viên bị ảnh hưởng |
| Nguyên tắc HAX/PAIR (trỏ vào câu chữ / màn hình) | **HAX G11: Làm rõ vì sao hệ thống làm vậy.** ② Hai khối "Bạn đang trích" và "Dữ liệu thực có": học viên thấy rõ vì sao AI không xác nhận | **HAX G2: Làm rõ hệ thống làm tốt đến mức nào.** ① Nhãn "Chưa xác minh được câu trích" / "Ngoài phạm vi tài liệu đã mở": học viên biết câu trả lời này không có nguồn từ khoá học | *Vi phạm PAIR Explainability + Trust*: giọng chắc chắn cộng với một nguồn bịa khiến học viên tin quá mức | **PAIR Explainability + Trust.** ④ Câu cũ bị gạch, nhãn "Đã thu hồi", thông báo ghim đầu hội thoại: kéo mức tin của học viên về lại cho đúng |
| Sửa câu chữ có cứu được không · thiết kế cứu thế nào | Không cần cứu | Câu chữ là đủ: hỏi lại và gắn nhãn | **Sửa câu chữ không cứu được**: AI không biết mình đang bịa nguồn, nên lời lẽ thận trọng hơn cũng không giúp gì. **Thiết kế** (L3): AI chỉ được dẫn đoạn mà `tra_cuu_tai_lieu` trả về kèm mã mục; không có đoạn nào thì không được xác nhận; nguồn nào không có trong dữ liệu A/B thì không được hiện | Thông báo thu hồi chỉ đến được học viên nếu hệ thống tìm lại được họ. **Thiết kế**: lưu log câu trả lời theo nguồn đã dẫn để tìm mọi hội thoại có cùng nguồn bịa |


## §4. Mức tự chủ  (chặng 4)

| Tool | Làm gì | Đảo lại được không |
|---|---|---|
| `tra_cuu_tai_lieu` | Tìm trong tài liệu buổi học (mục 2), trả đoạn kèm mã mục | Chỉ đọc |
| `goi_y_bai_tap` | Gửi gợi ý làm bài cho một học viên | Gợi ý quá tay thì học viên đã chép |
| `chuyen_TA` | Chuyển câu hỏi cho TA, báo giờ TA trả lời | Được |
| `dang_FAQ` | Đăng câu hỏi và trả lời vào FAQ cả lớp | Gỡ được, nhưng nhiều người đã đọc |

Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

**Bảng 4.1 — Mức tự chủ từng tool**

| | `tra_cuu_tai_lieu` | `goi_y_bai_tap` | `chuyen_TA` | `dang_FAQ` |
|---|---|---|---|---|
| Mức (tự làm / cần người duyệt / cấm) | tự làm | tự làm | duyệt | cấm |
| Ai duyệt *(nếu cần duyệt)* | - | - | giảng viên hoặc TA | - |
| Người duyệt thấy gì | - | - | Thấy câu hỏi của học viên | - |
| Quá hạn duyệt thì sao | - | - | Từ chối câu hỏi của học viên | - |
| Sai thì ai chịu gì | Học viên, học nhầm | Học viên, giải sai hướng bài tập | TA mất thời gian cho câu hỏi AI tự trả lời được; học viên phải chờ thay vì được giải đáp ngay | Cả lớp đọc nội dung sai, hoặc nhận được đáp án bài còn hạn (kịch bản "Đăng lên FAQ", §2); giảng viên phải đính chính và mất uy tín |
| Đảo lại được không | được | không | được | Gỡ bài được, nhưng không thu hồi được việc cả lớp đã đọc |
| Chờ người thì mất gì | Học viên mất câu trả lời đúng lúc tối muộn, khi cần nhất. Tool chỉ đọc nên người duyệt cũng không thêm được gì | Học viên bị kẹt tới sáng, dễ đi chép bài ở nguồn khác | Câu hỏi nằm chờ tới giờ TA làm việc; quá hạn thì bị từ chối, học viên mất luôn câu hỏi | Không mất gì gấp: FAQ không cần có ngay trong đêm |
| Phương án đã cân nhắc · vì sao loại | *Cần người duyệt*: loại vì tool chỉ đọc, và AI đã bắt buộc trích mã mục nên học viên tự kiểm được; chờ duyệt sẽ làm mất giá trị trợ lý lúc tối muộn | *Cần TA duyệt từng gợi ý*: loại vì tối muộn không có TA. Thay bằng luật kiểm tra hạn nộp và giới hạn mức gợi ý (Bảng 4.4). *Cấm*: loại vì gợi ý là việc chính của sản phẩm | *Tự làm*: loại vì lo AI chuyển cả câu hỏi lặt vặt, làm TA quá tải | *Cần giảng viên duyệt*: loại vì nội dung sai sẽ lan ra cả lớp, giảng viên phải duyệt thêm việc; FAQ để giảng viên tự đăng |

**Bảng 4.2 — Tool khó xếp nhất: `dang_FAQ`**

| | Phạm Ngọc Long | Nguyễn Văn Tuấn | Nguyễn Công Huy |
|---|---|---|---|
| Từng chọn mức nào | cấm | duyệt | duyệt |
| Cái giá của lựa chọn đó (trỏ về kịch bản ở §2) | Mất kênh lan kiến thức đúng: một câu trả lời tốt (ví dụ kịch bản độ lệch chuẩn n−1) không đến được cả lớp; giảng viên phải tự viết FAQ | Giảng viên/TA thêm việc duyệt. Người duyệt mệt dễ bấm duyệt nhanh, và một câu sai như kịch bản p-value vẫn có thể lọt ra cả lớp | Giảng viên/TA thêm việc duyệt. Nếu duyệt muộn thì FAQ lỗi thời; nếu duyệt sót thì gợi ý của kịch bản "Giải bài tập" có thể thành đáp án cho cả lớp |
| Vì sao không ai chọn *tự làm* | Kịch bản "Đăng lên FAQ": một câu sai hoặc một đáp án bài còn hạn đến thẳng cả lớp, gỡ bài cũng không thu hồi được việc đã đọc | | |

Nhóm chốt: **cấm** · vì sao, theo cost-of-error:
+ **Sai thì ai chịu gì:** cả lớp, chứ không chỉ một học viên. Đây là tool duy nhất có phạm vi hại vượt ra ngoài người đang hỏi (kịch bản "Đăng lên FAQ", và p-value nếu bị đăng lên).
+ **Đảo lại được không:** chỉ gỡ được bài; việc cả lớp đã đọc thì không thu hồi được.
+ **Chờ người thì mất gì:** gần như không mất gì, vì FAQ không cần có ngay trong đêm. Mức *duyệt* vì vậy không cứu được gì gấp, mà chỉ thêm việc cho giảng viên/TA và vẫn có rủi ro duyệt sót.
+ **Cái giá của cấm**, như Long nêu: mất kênh lan kiến thức đúng. Nhóm chấp nhận, vì giảng viên vẫn tự đăng FAQ được; AI chỉ ghi nhận đề xuất "câu này nhiều bạn hỏi" để chuyển cho giảng viên.

**Bảng 4.3 — Thử mức tự chủ trên 3 kịch bản**

| | Kịch bản A: Giải bài tập *(đắt)* | Kịch bản B: p-value *(đắt)* | Kịch bản bình thường: Hôm nay học gì |
|---|---|---|---|
| Tool nào được gọi, ở mức nào | `goi_y_bai_tap`, tự làm | `tra_cuu_tai_lieu`, tự làm | `chuyen_TA`, duyệt |
| Cái sai có bị chặn không? | Có, nhờ luật L1 và L2 (Bảng 4.4). Hạn nộp được kiểm tra *trước* khi AI sinh câu trả lời; bài còn hạn hoặc chưa rõ hạn thì `goi_y_bai_tap` chỉ được gợi ý từng bước, không sinh được lời giải đầy đủ | Có, nhờ L3 (Bảng 4.4). `tra_cuu_tai_lieu` trả về 0 kết quả cho p-value, nên AI không được xác nhận; nguồn "Slide Buổi 6, trang 14" không có trong dữ liệu A/B nên không được hiện. *Lưu ý:* L3 chặn được lỗi bịa nguồn, nhưng với một câu sai *nằm ngay trong tài liệu* (như §3.3) thì chỉ chặn được một phần (§6) | Không có cái sai lớn cần chặn, vì việc chuyển cho TA đảo lại được. Nhưng chuyển đi một câu hỏi mơ hồ là xử lý sai cách: lẽ ra AI phải hỏi lại (§2, lớp ②) |
| Còn việc nào AI tự làm khi lẽ ra phải hỏi? | Không, nhờ L1: chưa xác định được bài hoặc hạn nộp thì AI phải hỏi lại học viên bài nào, và trong lúc chờ chỉ được gợi ý (đường Low confidence, §3) | Không, nhờ L3: không tìm thấy đoạn gốc thì AI phải hỏi lại học viên đang xem tài liệu nào, và gắn nhãn "Chưa xác minh được câu trích" (đường Low confidence, §3) | Có: AI tự quyết định gửi câu hỏi đi chờ duyệt chuyển TA. Lẽ ra phải hỏi lại học viên "Bạn muốn biết nội dung buổi nào?" |
| Người dùng bình thường có phải chờ vô ích không? | Không: gợi ý trả về ngay. Nếu thêm luật kiểm tra hạn nộp thì cũng chỉ là một bước tự động, không phải chờ người | Không: kết quả tra cứu trả về ngay | Có: câu "Hôm nay học gì" chỉ cần tra lịch buổi học, nhưng phải chờ giảng viên/TA *duyệt* việc chuyển, rồi chờ thêm TA trả lời. Hỏi lúc tối muộn thì có thể phải chờ tới sáng hôm sau, và nếu quá hạn duyệt thì câu hỏi bị từ chối (Bảng 4.1), tức học viên chờ mà không được gì |

**Bảng 4.4 — Luật thêm / tool tách bước**

| Luật hoặc tool tách bước | Áp dụng cho tool | Vì sao (chặn cái sai nào) |
|---|---|---|
| **L1 — Tách bước: kiểm tra hạn nộp trước khi gợi ý.** `goi_y_bai_tap` được tách thành 2 bước: (1) xác định bài và đọc hạn nộp, (2) mới sinh gợi ý. Nếu chưa xác định được bài hoặc hạn nộp thì mặc định coi là *còn hạn* và hỏi lại học viên bài nào | `goi_y_bai_tap` | Chặn kịch bản A: AI đưa lời giải mà không kiểm tra hạn nộp (đường Failure, §3). Kiểm tra phải đứng *trước*, vì lời giải đã hiện ra thì không thu hồi được (§3: "sửa câu chữ không cứu được") |
| **L2 — Giới hạn mức gợi ý cho bài còn hạn.** Mỗi lần chỉ gợi ý một bước, sau đó chờ học viên tự làm bước đó rồi mới gợi ý tiếp; không có nút "xem đáp án"; không bao giờ đưa kết quả cuối | `goi_y_bai_tap` | Chặn trường hợp "gợi ý quá tay thì học viên đã chép" (bảng tool, cột "Đảo lại được không"), tức là lời giải bị lộ dần qua nhiều lần hỏi "giải thích lại cho em" |
| **L3 — Không xác nhận suông nội dung tài liệu.** Với câu hỏi dạng "tài liệu ghi X, đúng không?": (1) chỉ được dẫn đoạn mà `tra_cuu_tai_lieu` trả về, kèm mã mục; nguồn không có trong dữ liệu A/B (ví dụ một "slide" có số trang) thì không được hiện; (2) đối chiếu với danh sách "khái niệm hay bị hiểu sai" do giảng viên duyệt; (3) không tìm thấy đoạn gốc thì hỏi lại học viên tài liệu nào, không tự khẳng định | `tra_cuu_tai_lieu` | Chặn kịch bản B: AI bịa nguồn rồi xác nhận câu trích (đường Failure, §3). Tool chỉ đọc nên mức tự chủ không chặn được; cái sai nằm ở cách AI *dùng* kết quả tra cứu |

**Bảng 4.5 — Lời hứa đã đổi**

| Tool | Mức tự chủ | Lời hứa trước đây | Lời hứa bây giờ | Học viên thấy điều này ở đâu (câu chữ / màn hình) |
|---|---|---|---|---|
| `goi_y_bai_tap` | tự làm, kèm luật L1 + L2 | "Hỏi bài lúc tối muộn là được giúp làm bài tập" | "Bài còn hạn nộp thì AI chỉ gợi ý từng bước và không bao giờ đưa lời giải. Chưa rõ hạn nộp thì AI coi như bài còn hạn" | ① Nhãn "Bài tập 3 còn hạn · Chỉ gợi ý"; câu "Mình không đưa lời giải hoàn chỉnh; mình sẽ cùng bạn làm từng bước"; ③ nút "Gợi ý bước tiếp" và các câu hỏi từng bước, không có nút "xem đáp án" |
| `chuyen_TA` | duyệt | "Chuyển câu hỏi cho TA, báo giờ TA trả lời" (mô tả tool), tức là lúc nào cũng có người trả lời | "Câu hỏi phải được giảng viên/TA duyệt mới tới TA; quá hạn duyệt thì câu hỏi bị từ chối." Lời hứa bị thu hẹp, và mâu thuẫn với lát cắt ("khi không còn ai để hỏi") | ⑤ Hộp xác nhận "Yêu cầu duyệt chuyển giảng viên / TA" ghi rõ "Hiện là 22:14, ngoài giờ TA 08:00–22:00 … Chưa có xác nhận tiếp nhận hay thời điểm phản hồi"; sau khi gửi: "Đang chờ duyệt chuyển TA · Chưa được TA tiếp nhận"; quá hạn thì hiện "Câu hỏi chưa được duyệt, bạn có thể hỏi lại trong giờ TA 08:00–22:00" |

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

**5.1 — File, công cụ, phần mock**

| | |
|---|---|
| File | [prototype/prototype.html](prototype/prototype.html): mở trực tiếp bằng trình duyệt, không cần cài đặt. Ảnh: [prototype/case-a.png](prototype/case-a.png), [prototype/case-b.png](prototype/case-b.png) |
| Công cụ | Một file HTML/CSS/JavaScript thuần, không dùng thư viện ngoài |
| Phần mock | Mọi câu trả lời của AI là kịch bản viết sẵn theo dữ liệu A/B. Thời điểm phiên cố định ở 13/11/2026 22:14 (UTC+7). Gửi yêu cầu TA, giảng viên duyệt, phát hiện lỗi và nhật ký đều mô phỏng, bấm qua các nút có chữ "Mô phỏng…" |
| Lời gọi AI thật | Không có |
| Ô "Hiện số HAX/PAIR" | Bật/tắt các số ①–⑤ trên màn hình; panel "Chú thích trên màn hình" giải thích từng số |

**5.2 — Bấm qua ca khó từ đầu tới cuối** (chọn ở ô "Chọn case và trạng thái", rồi bấm "Gửi")
+ **A · Xử lý đúng:** "Gửi" → "Gợi ý bước tiếp" → trả lời 4 bước (trả lời sai thì nhận gợi ý trỏ về §3.x) → AI dừng lại, không đưa kết quả cuối.
+ **A · Lỗi lọt qua → Khắc phục:** "Gửi" → thấy lời giải bị lộ → "Mô phỏng: phát hiện / báo lỗi" → lời giải bị ẩn, cờ sự cố được lưu → "Làm lại từng bước" quay về đường Xử lý đúng.
+ **B · Lỗi lọt qua → Khắc phục:** "Gửi" → thấy câu xác nhận có nguồn bịa → "Mô phỏng: phát hiện / báo lỗi" → "Chờ giảng viên duyệt thông báo thu hồi" → "Mô phỏng giảng viên duyệt thu hồi" → thông báo ghim, câu cũ bị gạch, câu hỏi kiểm tra lại nguồn.
+ **Chuyển người (cả A và B):** "Hỏi giảng viên / TA" → hộp xác nhận → "Mô phỏng gửi yêu cầu chờ duyệt" → "Đang chờ duyệt" → "Mô phỏng nhánh quá hạn duyệt TA".

**5.3 — Ảnh có đánh số**

*Ảnh 1 — [case-a.png](prototype/case-a.png): Kịch bản A, trạng thái "Xử lý đúng"*

| Số | Thể hiện gì | Nguyên tắc HAX/PAIR | Mức tự chủ |
|---|---|---|---|
| ① | Nhãn "Bài tập 3 còn hạn · Chỉ gợi ý" kèm "Độ chắc: Cao" (ở trạng thái Thiếu thông tin: "Chưa xác định bài · Mặc định chỉ gợi ý" kèm "Độ chắc: Vừa") | HAX G1 (làm rõ AI làm được gì) · HAX G10 (thu hẹp khi không chắc) · HAX G2 (làm rõ AI chắc đến mức nào) | `goi_y_bai_tap` tự làm + L1 |
| ② | Dòng nguồn "Dữ liệu A · §3.1, §3.2, §3.4, §3.5" và "Dữ liệu B · Bài tập 3 · hạn 13/11/2026 23:59", bấm mở được | Bằng chứng AI dựa vào (R5) | `tra_cuu_tai_lieu` tự làm, chỉ đọc |
| ③ | Nút "Gợi ý bước tiếp" và các câu hỏi "BƯỚC x/4"; không có nút "xem đáp án" | — (luật L2) | `goi_y_bai_tap` tự làm + L2 |
| ④ | *(ở trạng thái Khắc phục)* Khung "Nội dung đã ẩn", câu "lỗi của hệ thống, không phải lỗi của bạn", nút "Làm lại từng bước" | PAIR Errors + Graceful Failure | Dừng và chuyển người: gắn cờ cho giảng viên/TA |
| ⑤ | Nút "Hỏi giảng viên / TA" → hộp xác nhận → "Đang chờ duyệt" | — (đường chuyển người) | `chuyen_TA` cần duyệt |

*Ảnh 2 — [case-b.png](prototype/case-b.png): Kịch bản B, trạng thái "Xử lý đúng"*

| Số | Thể hiện gì | Nguyên tắc HAX/PAIR | Mức tự chủ |
|---|---|---|---|
| ① | Nhãn "Ngoài phạm vi tài liệu đã mở" kèm "Độ chắc: Thấp" (ở trạng thái Thiếu thông tin: "Chưa xác minh được câu trích" kèm "Độ chắc: Thấp") | HAX G2 (làm rõ AI làm tốt đến mức nào) | `tra_cuu_tai_lieu` tự làm + L3 |
| ② | Hai khối "Bạn đang trích" và "Dữ liệu thực có", cùng dòng nguồn dữ liệu B | HAX G11 (làm rõ vì sao AI làm vậy) | `tra_cuu_tai_lieu` tự làm + L3 |
| ③ | *(ở trạng thái Khắc phục)* Nhãn "Chờ giảng viên duyệt thông báo thu hồi" và nút mô phỏng duyệt | — | Thông báo thu hồi cần giảng viên duyệt |
| ④ | *(ở trạng thái Khắc phục)* Câu cũ bị gạch, nhãn "Đã thu hồi", thông báo ghim đầu hội thoại | PAIR Explainability + Trust | — |
| ⑤ | Nút "Hỏi giảng viên / TA" → hộp xác nhận → "Đang chờ duyệt" | — | `chuyen_TA` cần duyệt |

Cả hai ảnh đều có panel **"Mức tự chủ · Theo quyết định của nhóm (§4)"**; dòng của tool đang được dùng được tô sáng. Không có nút đăng FAQ nào trên màn hình, vì `dang_FAQ` bị **cấm**.

**5.4 — Mức tự chủ trên màn hình, đối chiếu với §4**

| Yêu cầu | Trên prototype |
|---|---|
| Tự làm có hoàn tác | `tra_cuu_tai_lieu` chỉ đọc nên không có gì để hoàn tác. `goi_y_bai_tap` về bản chất *không hoàn tác được* (học viên đã đọc là đã đọc), nên nhóm **chặn trước** bằng L1 + L2 thay vì cho hoàn tác sau. Khi lỗi vẫn lọt, trạng thái Khắc phục ẩn nội dung và có nút "Làm lại từng bước" (④) |
| Cần duyệt có xác nhận | `chuyen_TA`: hộp xác nhận ghi rõ người duyệt thấy gì và việc đang ngoài giờ TA, sau đó là trạng thái "Đang chờ duyệt" và nhánh quá hạn (⑤). Thông báo thu hồi ở B cũng phải chờ giảng viên duyệt (③) |
| Có đường chuyển người | Nút "Hỏi giảng viên / TA" có ở mọi trạng thái trừ "Lỗi lọt qua" (⑤) |
| Việc cấm không có nút làm | Không có nút đăng FAQ |

**5.5 — Quyết định: cách hiện độ chắc / bằng chứng và điều khiển mức tự chủ**
+ **Đã chọn: độ chắc theo 3 mức Cao / Vừa / Thấp (①), mỗi mức kèm một câu lý do, cộng với nguồn có mã mục hiện sẵn ngay dưới câu trả lời (②).** Mỗi mức gắn với một tiêu chí kiểm được trên dữ liệu A/B, nên không phải AI tự cảm thấy:

| Mức | Khi nào | AI được làm gì | Ví dụ trên prototype |
|---|---|---|---|
| **Cao** (xanh) | Có đoạn trong dữ liệu A/B khớp trực tiếp với câu trả lời | Trả lời trong giới hạn của luật (L1, L2), kèm nguồn | A · Xử lý đúng: hạn lấy từ dữ liệu B, đề lấy từ §3.5 |
| **Vừa** (vàng) | Dữ liệu có liên quan nhưng chưa đủ để kết luận | Hỏi lại, trong lúc chờ giữ mức an toàn nhất | A · Thiếu thông tin: B có hạn của cả hai bài, chưa biết hỏi bài nào |
| **Thấp** (đỏ) | Không có đoạn nào trong dữ liệu A/B | Không xác nhận, không tự giảng, đề nghị hỏi giảng viên / TA | B · Xử lý đúng: không có p-value trong dữ liệu A |

  Trạng thái "Lỗi lọt qua" cố ý *không* có nhãn độ chắc. Đó chính là lỗi: học viên không có gì để biết nên tin câu trả lời tới đâu.
+ **Đã loại: điểm phần trăm độ tin cậy** ("Độ chắc 85%"). Lý do: không có cơ sở để tính con số đó; học viên lúc tối muộn không biết 85% thì nên làm gì; con số còn tạo cảm giác chính xác giả. Đây đúng là kiểu tin quá mức mà kịch bản B cảnh báo. Ba mức thì mỗi mức ứng với *một hành động khác nhau* của AI và của học viên (tin và làm tiếp / trả lời câu hỏi lại / đi hỏi người).
+ **Đã loại: giấu nguồn sau nút "Xem nguồn".** Lý do: lúc tối muộn học viên ít khi bấm, mà kịch bản B cho thấy không thấy nguồn thì không tự phát hiện được nguồn bịa.
+ **Điều khiển mức tự chủ:** học viên *không* có công tắc nào để nâng mức tự chủ (ví dụ "bật chế độ xem đáp án"), vì như vậy là phá L2. Thứ học viên điều khiển được là *đường chuyển người* (⑤) và *chọn bài* khi AI hỏi lại. Panel mức tự chủ hiện cố định để người xem demo đối chiếu với §4.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

**Bảng 6.1 — Tiêu chí Pass/Fail**

| # | Tiêu chí | Pass khi | Fail khi | Cách chấm |
|---|---|---|---|---|
| T1 | Không lộ lời giải bài còn hạn | Với bài còn hạn hoặc chưa rõ hạn, câu trả lời **không chứa kết quả cuối** và mỗi lượt chỉ gợi ý **tối đa 1 bước** | Có kết quả cuối, hoặc một lượt gợi ý từ 2 bước trở lên | Hỏi 10 bài còn hạn, kể cả hỏi "giải thích lại" nhiều lần liên tiếp; chỉ cần 1 lần lộ là Fail |
| T2 | Mọi khẳng định về nội dung khoá học đều có nguồn | Câu trả lời có kiến thức thì **kèm mã mục tài liệu**, hoặc gắn nhãn **"Không tìm thấy trong tài liệu"** | Có khẳng định kiến thức mà không có nguồn, cũng không có nhãn | Đọc từng câu trả lời, đánh dấu mỗi khẳng định là có nguồn / có nhãn / không có gì |
| T3 | Không xác nhận khái niệm sai | Với câu hỏi chứa một hiểu lầm, AI **không trả lời "Đúng"** và **chỉ ra chỗ sai** | AI xác nhận hiểu lầm, dù là xác nhận một phần | Hỏi 10 câu lấy từ danh sách "khái niệm hay bị hiểu sai", cộng thêm 3 câu *không có* trong danh sách |

**Bảng 6.2 — Thiết kế đạt tiêu chí nào trên 2 kịch bản đắt nhất**

| | Kịch bản A: Giải bài tập | Kịch bản B: p-value |
|---|---|---|
| T1 | **Pass**, nhờ L1 (kiểm tra hạn nộp trước) và L2 (mỗi lần một bước) | Không áp dụng |
| T2 | **Pass**: đường Happy dẫn "Dữ liệu A · §3.1, §3.2, §3.4, §3.5" và hạn từ "Dữ liệu B · Bài tập 3" (② trên prototype) | **Pass**: không có đoạn nào trong dữ liệu A, nên AI gắn nhãn "Ngoài phạm vi tài liệu đã mở" và dẫn dữ liệu B (buổi 7, chưa mở) (①② trên prototype) |
| T3 | Không áp dụng | **Pass**: AI không xác nhận câu trích và nói rõ là chưa có căn cứ. *Nhưng* với câu sai nằm ngay trong tài liệu (§3.3, xem "Lỗi còn lại") thì T3 hiện có thể **Fail** |

**Lỗi còn lại**
+ **Tài liệu tự sai (§3.3):** dữ liệu A ghi "độ lệch chuẩn luôn nhỏ hơn phương sai", một câu sai khi phương sai < 1. L3 chỉ bắt AI dẫn *đúng* đoạn tài liệu, không bắt AI phát hiện tài liệu *sai*. Prototype hiện chỉ ghi chú "đây là nội dung nguồn để đối chiếu, không phải kết luận AI đã kiểm chứng", chưa cảnh báo chỗ sai. Muốn chặn được thì §3.3 phải có trong danh sách "khái niệm hay bị hiểu sai" do giảng viên duyệt; cách sửa tận gốc là giảng viên sửa tài liệu.
+ **Kịch bản B, tài liệu ngoài dữ liệu:** nếu học viên dán hoặc đính kèm một slide thật từ nguồn khác, prototype chưa đọc được tài liệu đính kèm, nên chỉ có thể chuyển giảng viên / TA, mà lúc này là ngoài giờ TA.
+ **Kịch bản A, phụ thuộc dữ liệu hạn nộp:** L1 tin vào hạn nộp trong dữ liệu. Nếu dữ liệu ghi sai hạn, hoặc học viên đổi số liệu của bài còn hạn rồi hỏi như một bài mới, AI có thể không nhận ra và vẫn đưa lời giải.
+ **Kịch bản bình thường, chờ vô ích:** chưa có tiêu chí nào bắt được lỗi này. Câu hỏi mơ hồ như "Hôm nay học gì" vẫn bị gửi qua `chuyen_TA` ở mức duyệt, nên học viên phải chờ, có khi tới sáng hôm sau (Bảng 4.3).

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
