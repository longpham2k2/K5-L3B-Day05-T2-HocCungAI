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

**Kịch bản A — "Giải giúp em bài tập tuần này, mai nộp rồi"**

| | Happy | Low confidence | Failure | Correction |
|---|---|---|---|---|
| Tình huống | AI nhận đúng bài (Bài tập tuần 5) và đọc được hạn nộp 23:59 ngày mai | AI không xác định được học viên hỏi bài nào, hoặc không đọc được hạn nộp | AI không kiểm tra hạn nộp, đưa luôn lời giải | Hệ thống kiểm tra sau trả lời phát hiện lời giải đầy đủ cho bài còn hạn, hoặc học viên bấm "Báo lỗi" |
| AI nói gì (nguyên văn) | "Bài này còn hạn nộp đến 23:59 ngày mai nên mình không đưa lời giải được. Mình cùng làm từng bước nhé: đề bài đang yêu cầu tính gì? Phần lý thuyết liên quan nằm ở Slide Buổi 5, trang 8–10." | "Mình chưa chắc bài này còn trong hạn nộp hay không, nên tạm thời mình chỉ gợi ý hướng làm. Bạn cho mình biết bài số mấy, buổi nào nhé?" | "Được thôi, đây là lời giải cho bài tập của bạn: 1 + 1 = 2" | "Câu trả lời trước của mình đã đưa lời giải cho một bài còn hạn nộp. Đây là lỗi của hệ thống, không phải lỗi của bạn. Mình đã ẩn lời giải đó. Mình làm lại từng bước cùng bạn nhé?" |
| Người dùng thấy gì (trên màn hình) | Nhãn xanh "Bài còn hạn · chế độ gợi ý", trích dẫn slide có link, nút "Gợi ý bước tiếp" | Nhãn vàng "Chưa xác định hạn nộp", danh sách bài của tuần để chọn | Lời giải đầy đủ, không nhãn, không cảnh báo, trông như một câu trả lời bình thường | Lời giải cũ bị thay bằng dòng "Nội dung đã ẩn: lời giải bài còn hạn", nút "Làm lại từng bước" |
| Làm gì tiếp (học viên bấm / làm được gì) | Trả lời từng bước, AI nhận xét và gợi ý bước tiếp; không có nút "xem đáp án" | Chọn bài: quay về đường Happy. Không chọn: vẫn ở chế độ gợi ý | Chép lời giải và nộp bài | Làm lại theo từng bước, hoặc bấm "Hỏi giảng viên" |
| Ai được báo | Không ai (đúng luật) | Không ai | Không ai, lỗi lọt qua | Giảng viên/trợ giảng phụ trách bài, kèm log hội thoại |
| Sau bao lâu | — | — | Chỉ lộ ra khi chấm bài (vài ngày sau), hoặc không bao giờ | Ngay khi bị gắn cờ (vài phút), trước hạn nộp |
| Quyết định (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người) | **Trả lời kèm giới hạn**: chỉ gợi ý, không đưa lời giải. Loại *hỏi lại* vì đã đủ thông tin; loại *chuyển người* vì luật đã rõ, không cần giảng viên | **Hỏi lại** (bài nào, buổi nào), trong lúc chờ vẫn giữ chế độ gợi ý. Loại *trả lời đầy đủ* vì nếu bài còn hạn thì đáp án đã lộ, không đảo lại được | AI đã chọn *trả lời đầy đủ*, trong khi đáng lẽ phải *trả lời kèm giới hạn* | **Dừng và chuyển người**: giảng viên quyết định có ảnh hưởng tới bài nộp hay không. AI không tự xử lý vì đây là chuyện liêm chính học thuật |
| Loại lỗi (hệ thống / người dùng / ngữ cảnh) | — (không có lỗi) | **Ngữ cảnh**: thiếu thông tin về bài và hạn nộp. Vì vậy cách nói là xin thêm thông tin, không trách học viên hỏi thiếu | **Hệ thống**: AI bỏ qua bước kiểm tra hạn nộp. Phải sửa ở luật/tool, sửa câu chữ không giải quyết được | **Hệ thống**: vì vậy AI nhận lỗi về mình ("lỗi của hệ thống, không phải lỗi của bạn"), không đổ cho học viên |
| Nguyên tắc HAX/PAIR (trỏ vào câu chữ / màn hình) | **HAX G1: Làm rõ hệ thống làm được gì.** Câu "không đưa lời giải được" và nhãn xanh "Bài còn hạn · chế độ gợi ý": học viên biết AI sẽ gợi ý chứ không giải hộ, và biết vì sao | **HAX G10: Thu hẹp dịch vụ khi không chắc.** Câu "tạm thời mình chỉ gợi ý hướng làm" và nhãn vàng "Chưa xác định hạn nộp": chưa chắc thì AI chọn mức an toàn hơn, không đoán | *Vi phạm G1 và G10*: không nhãn, không nói giới hạn, AI làm hết mọi việc dù không chắc | **PAIR Errors + Graceful Failure.** Câu "lỗi của hệ thống, không phải lỗi của bạn", dòng "Nội dung đã ẩn" và nút "Làm lại từng bước": AI nhận lỗi và vẫn chừa cho học viên đường học tiếp |
| Sửa câu chữ có cứu được không · thiết kế cứu thế nào | Không cần cứu | Câu chữ là đủ: chỉ cần hỏi lại. Thiết kế thêm danh sách bài trong tuần để học viên chọn nhanh | **Sửa câu chữ không cứu được**: lời giải đã sinh ra là đã lộ. **Thiết kế**: tool kiểm tra hạn nộp chạy *trước* khi sinh câu trả lời; bài còn hạn thì khoá ở chế độ "chỉ gợi ý", AI không có quyền sinh lời giải đầy đủ | Câu chữ chỉ giảm thiệt hại (ẩn lời giải, nhận lỗi), không xoá được việc học viên đã đọc. Vì vậy phải dựa vào thiết kế chặn trước ở cột Failure; giảng viên được báo để xử lý bài nộp |

**Kịch bản B — "Slide ghi p-value < 0.05 là chứng minh giả thuyết đúng, đúng không?"**

| | Happy | Low confidence | Failure | Correction |
|---|---|---|---|---|
| Tình huống | AI tìm thấy đúng câu trên slide và nhận ra cách diễn đạt dễ gây hiểu nhầm | AI không tìm thấy câu này trong slide, nên không biết slide sai hay học viên trích sai | AI tin theo slide/lời học viên và xác nhận | Giảng viên xem log, học viên khác báo, hoặc đợt rà soát định kỳ phát hiện câu xác nhận sai |
| AI nói gì (nguyên văn) | "Chưa đúng hẳn. p-value < 0.05 nghĩa là: nếu H0 đúng thì dữ liệu như thế này rất hiếm gặp, nên ta bác bỏ H0. Nó không 'chứng minh' giả thuyết của bạn đúng. Câu trên Slide Buổi 6, trang 14 có thể đang viết tắt, bạn nên hỏi lại giảng viên cho chắc. Mình đã gửi ghi chú để giảng viên xem lại slide." | "Mình không tìm thấy câu này trong slide của khoá. Theo cách hiểu thống kê thông thường thì p-value < 0.05 không chứng minh giả thuyết đúng. Bạn gửi giúp mình trang slide đó, hoặc hỏi giảng viên để chắc nhé." | "Đúng, p-value < 0.05 đã chứng minh giả thuyết đúng." | "Mình cần đính chính câu trả lời hôm [ngày]: p-value < 0.05 không chứng minh giả thuyết đúng, mà chỉ cho phép bác bỏ H0. Xin lỗi vì mình đã xác nhận sai. Giải thích chi tiết ở đây: [link]." |
| Người dùng thấy gì (trên màn hình) | Hai khối đặt cạnh nhau: đoạn gốc trên slide và phần giải thích của AI; nhãn "Khác với cách diễn đạt trên slide"; nút "Hỏi giảng viên" | Nhãn vàng "Không tìm thấy trong tài liệu"; nút "Đính kèm trang slide", "Hỏi giảng viên" | Câu xác nhận ngắn gọn, giọng chắc chắn, trông rất đáng tin | Thông báo đính chính ghim trên đầu cuộc trò chuyện; câu trả lời cũ bị gạch và gắn nhãn "Đã đính chính" |
| Làm gì tiếp (học viên bấm / làm được gì) | Hỏi tiếp ví dụ, hoặc bấm "Hỏi giảng viên" | Đính kèm slide: quay về đường Happy. Không có slide: hỏi giảng viên | Ghi nhớ sai và dùng trong bài kiểm tra | Đọc đính chính, làm câu hỏi kiểm tra nhanh để chắc đã hiểu đúng |
| Ai được báo | Giảng viên: ghi chú "slide có thể gây hiểu nhầm" | Không ai (chưa xác nhận slide sai) | Không ai, lỗi lọt qua | Học viên đã hỏi và mọi học viên từng nhận câu trả lời tương tự; giảng viên để sửa slide |
| Sau bao lâu | Gộp vào bản tổng hợp cuối ngày (không gấp, vì học viên đã được giải thích đúng) | — | Lộ ra khi thi/chấm bài, hoặc không bao giờ | Trong 24h kể từ khi phát hiện, trước buổi kiểm tra kế tiếp |
| Quyết định (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người) | **Trả lời kèm giới hạn**: giải thích đúng, chỉ ra chỗ khác với slide, khuyên học viên hỏi giảng viên. Loại *chuyển người* vì học viên cần hiểu ngay tối nay; loại *xác nhận theo slide* vì như vậy là sai kiến thức | **Hỏi lại** (xin trang slide) kèm **trả lời có giới hạn** theo kiến thức chung, gắn nhãn "không tìm thấy trong tài liệu" | AI đã chọn *trả lời chắc chắn, không giới hạn*, trong khi đáng lẽ phải *trả lời kèm giới hạn* | **Dừng và chuyển người**: giảng viên duyệt nội dung đính chính và sửa slide; AI chỉ gửi đính chính sau khi được duyệt |
| Loại lỗi (hệ thống / người dùng / ngữ cảnh) | **Ngữ cảnh**: lỗi nằm ở tài liệu, không ở học viên. Vì vậy AI nói "slide có thể đang viết tắt", không nói "bạn hiểu sai" | **Ngữ cảnh hoặc người dùng**: có thể slide sai, cũng có thể học viên trích sai. Vì vậy AI hỏi lại để xác minh, chưa khẳng định bên nào sai | **Hệ thống**: AI chiều theo tài liệu/người hỏi thay vì theo kiến thức đúng | **Hệ thống**: vì vậy AI xin lỗi và đính chính công khai với mọi học viên bị ảnh hưởng |
| Nguyên tắc HAX/PAIR (trỏ vào câu chữ / màn hình) | **HAX G11: Làm rõ vì sao hệ thống làm vậy.** Hai khối đặt cạnh nhau (đoạn gốc trên slide và giải thích của AI) cùng câu "có thể đang viết tắt": học viên thấy AI nói khác slide ở đâu và dựa vào đâu | **HAX G2: Làm rõ hệ thống làm tốt đến mức nào.** Nhãn vàng "Không tìm thấy trong tài liệu" và cụm "Theo cách hiểu thống kê thông thường": học viên biết câu trả lời không có nguồn từ khoá học | *Vi phạm PAIR Explainability + Trust*: giọng chắc chắn, không dẫn nguồn, khiến học viên tin quá mức | **PAIR Explainability + Trust.** Thông báo đính chính ghim trên đầu và nhãn "Đã đính chính" trên câu cũ: kéo mức tin của học viên về lại cho đúng |
| Sửa câu chữ có cứu được không · thiết kế cứu thế nào | Không cần cứu | Câu chữ là đủ: hỏi lại và gắn nhãn nguồn | **Sửa câu chữ không cứu được**: AI không biết mình sai, nên lời lẽ thận trọng hơn cũng không giúp gì. **Thiết kế**: với câu hỏi "slide ghi X, đúng không?", AI luôn phải hiện đoạn gốc kèm nguồn, không được trả lời "Đúng" suông; AI đối chiếu thêm với danh sách "khái niệm hay bị hiểu sai" do giảng viên duyệt | Câu đính chính chỉ đến được học viên nếu hệ thống tìm lại được họ. **Thiết kế**: lưu log câu trả lời theo khái niệm để tìm mọi học viên bị ảnh hưởng; giảng viên sửa slide tận gốc |

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
| Sai thì ai chịu gì | Học viên, học nhầm | Học viên, giải sai hướng bài tập | TA mất thời gian cho câu hỏi AI tự trả lời được; học viên phải chờ thay vì được giải đáp ngay | giảng viên |
| Đảo lại được không | được | không | được | Gỡ bài được, nhưng không thu hồi được việc cả lớp đã đọc |
| Chờ người thì mất gì | Học viên mất câu trả lời đúng lúc tối muộn, khi cần nhất. Tool chỉ đọc nên người duyệt cũng không thêm được gì | Học viên bị kẹt tới sáng, dễ đi chép bài ở nguồn khác | Câu hỏi nằm chờ tới giờ TA làm việc; quá hạn thì bị từ chối, học viên mất luôn câu hỏi | Không mất gì gấp: FAQ không cần có ngay trong đêm |
| Phương án đã cân nhắc · vì sao loại | *Cần người duyệt*: loại vì tool chỉ đọc, và AI đã bắt buộc trích mã mục nên học viên tự kiểm được; chờ duyệt sẽ làm mất giá trị trợ lý lúc tối muộn | *Cần TA duyệt từng gợi ý*: loại vì tối muộn không có TA. Thay bằng luật kiểm tra hạn nộp và giới hạn mức gợi ý (Bảng 4.4). *Cấm*: loại vì gợi ý là việc chính của sản phẩm | *Tự làm*: loại vì lo AI chuyển cả câu hỏi lặt vặt, làm TA quá tải | *Cần giảng viên duyệt*: loại vì nội dung sai sẽ lan ra cả lớp, giảng viên phải duyệt thêm việc; FAQ để giảng viên tự đăng |

**Bảng 4.2 — Tool khó xếp nhất: `dang_FAQ`**

| | Phạm Ngọc Long | Nguyễn Văn Tuấn | Nguyễn Công Huy |
|---|---|---|---|
| Từng chọn mức nào | cấm | duyệt | duyệt |
| Cái giá của lựa chọn đó (trỏ về kịch bản ở §2) | - | giảng viên và TA thêm việc duuyệt | giảng viên và TA thêm việc duuyệ |

Nhóm chốt: cấm · vì sao: tự làm thì rủi ro lộ thông tin, duyệt thì thêm việc cho giảng viên và TA, nên cấm cho nhanh

**Bảng 4.3 — Thử mức tự chủ trên 3 kịch bản**

| | Kịch bản A: Giải bài tập *(đắt)* | Kịch bản B: p-value *(đắt)* | Kịch bản bình thường: Hôm nay học gì |
|---|---|---|---|
| Tool nào được gọi, ở mức nào | `goi_y_bai_tap`, tự làm | `tra_cuu_tai_lieu`, tự làm | `chuyen_TA`, duyệt |
| Cái sai có bị chặn không? | Có, nhờ luật L1 và L2 (Bảng 4.4). Hạn nộp được kiểm tra *trước* khi AI sinh câu trả lời; bài còn hạn hoặc chưa rõ hạn thì `goi_y_bai_tap` chỉ được gợi ý từng bước, không sinh được lời giải đầy đủ | Một phần, nhờ L3 (Bảng 4.4). AI không được trả lời "Đúng" suông nữa: phải hiện đoạn gốc kèm nguồn và đối chiếu với danh sách khái niệm hay bị hiểu sai. Vẫn còn lọt nếu khái niệm đó chưa có trong danh sách; khi đó phải dựa vào đường Correction (§3) | Không có cái sai lớn cần chặn, vì việc chuyển cho TA đảo lại được. Nhưng chuyển đi một câu hỏi mơ hồ là xử lý sai cách: lẽ ra AI phải hỏi lại (§2, lớp ②) |
| Còn việc nào AI tự làm khi lẽ ra phải hỏi? | Không, nhờ L1: chưa xác định được bài hoặc hạn nộp thì AI phải hỏi lại học viên bài nào, và trong lúc chờ chỉ được gợi ý (đường Low confidence, §3) | Không, nhờ L3: không tìm thấy đoạn gốc thì AI phải xin học viên trang slide, và gắn nhãn "Không tìm thấy trong tài liệu" (đường Low confidence, §3) | Có: AI tự quyết định gửi câu hỏi đi chờ duyệt chuyển TA. Lẽ ra phải hỏi lại học viên "Bạn muốn biết nội dung buổi nào?" |
| Người dùng bình thường có phải chờ vô ích không? | Không: gợi ý trả về ngay. Nếu thêm luật kiểm tra hạn nộp thì cũng chỉ là một bước tự động, không phải chờ người | Không: kết quả tra cứu trả về ngay | Có: câu "Hôm nay học gì" chỉ cần tra lịch buổi học, nhưng phải chờ giảng viên/TA *duyệt* việc chuyển, rồi chờ thêm TA trả lời. Hỏi lúc tối muộn thì có thể phải chờ tới sáng hôm sau, và nếu quá hạn duyệt thì câu hỏi bị từ chối (Bảng 4.1), tức học viên chờ mà không được gì |

**Bảng 4.4 — Luật thêm / tool tách bước**

| Luật hoặc tool tách bước | Áp dụng cho tool | Vì sao (chặn cái sai nào) |
|---|---|---|
| **L1 — Tách bước: kiểm tra hạn nộp trước khi gợi ý.** `goi_y_bai_tap` được tách thành 2 bước: (1) xác định bài và đọc hạn nộp, (2) mới sinh gợi ý. Nếu chưa xác định được bài hoặc hạn nộp thì mặc định coi là *còn hạn* và hỏi lại học viên bài nào | `goi_y_bai_tap` | Chặn kịch bản A: AI đưa lời giải mà không kiểm tra hạn nộp (đường Failure, §3). Kiểm tra phải đứng *trước*, vì lời giải đã hiện ra thì không thu hồi được (§3: "sửa câu chữ không cứu được") |
| **L2 — Giới hạn mức gợi ý cho bài còn hạn.** Mỗi lần chỉ gợi ý một bước, sau đó chờ học viên tự làm bước đó rồi mới gợi ý tiếp; không có nút "xem đáp án"; không bao giờ đưa kết quả cuối | `goi_y_bai_tap` | Chặn trường hợp "gợi ý quá tay thì học viên đã chép" (bảng tool, cột "Đảo lại được không"), tức là lời giải bị lộ dần qua nhiều lần hỏi "giải thích lại cho em" |
| **L3 — Không xác nhận suông nội dung tài liệu.** Với câu hỏi dạng "slide ghi X, đúng không?": (1) phải hiện đoạn gốc kèm mã mục; (2) đối chiếu với danh sách "khái niệm hay bị hiểu sai" do giảng viên duyệt; (3) không tìm thấy đoạn gốc thì hỏi lại học viên trang slide, không tự khẳng định | `tra_cuu_tai_lieu` | Chặn kịch bản B: AI chiều theo slide hoặc lời học viên mà xác nhận sai (đường Failure, §3). Tool chỉ đọc nên mức tự chủ không chặn được; cái sai nằm ở cách AI *dùng* kết quả tra cứu |

**Bảng 4.5 — Lời hứa đã đổi**

| Tool | Mức tự chủ | Lời hứa trước đây | Lời hứa bây giờ | Học viên thấy điều này ở đâu (câu chữ / màn hình) |
|---|---|---|---|---|
| `goi_y_bai_tap` | tự làm, kèm luật L1 + L2 | "Hỏi bài lúc tối muộn là được giúp làm bài tập" | "Bài còn hạn nộp thì AI chỉ gợi ý từng bước và không bao giờ đưa lời giải. Chưa rõ hạn nộp thì AI coi như bài còn hạn" | Nhãn xanh "Bài còn hạn · chế độ gợi ý"; câu "Bài này còn hạn nộp đến 23:59 ngày mai nên mình không đưa lời giải được"; nút "Gợi ý bước tiếp", không có nút "xem đáp án" |
| `chuyen_TA` | duyệt | "Chuyển câu hỏi cho TA, báo giờ TA trả lời" (mô tả tool), tức là lúc nào cũng có người trả lời | "Câu hỏi phải được giảng viên/TA duyệt mới tới TA; quá hạn duyệt thì câu hỏi bị từ chối." Lời hứa bị thu hẹp, và mâu thuẫn với lát cắt ("khi không còn ai để hỏi") | Trạng thái dưới câu hỏi: "Đang chờ duyệt chuyển TA · dự kiến phản hồi lúc [giờ]"; quá hạn thì hiện "Câu hỏi chưa được duyệt, bạn có thể hỏi lại trong giờ TA làm việc" |

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
