# Dàn ý bài nộp *(spec.md — nộp trước 23:59 ngày lab của lớp)*

> Copy dàn ý này vào `spec.md` của nhóm. Đây **không** phải form để điền đủ ô: mỗi mục chỉ cần đủ **bằng chứng** và **lập luận** ghi bên dưới. Viết ngắn, gạch đầu dòng là được. Hướng dẫn từng chặng: `02-guide.md`. Cách chấm: `04-rubric.md`.
>
> **Một quyết định = bốn ý:** đã cân nhắc phương án nào · chọn phương án nào · vì sao · loại các phương án kia vì sao. Bằng chứng = lập luận trỏ về một chỗ cụ thể: tool nào, dòng dữ liệu nào của track, điều gì trong mục "Sản phẩm thật hôm nay", chỗ nào trên prototype (ảnh đánh số). Không chạy agent.

# Bài nộp LAB5 — [Track] · Nhóm [tên]
[Danh sách thành viên và việc mỗi người làm — copy bảng từ README]
**Lớp:** L3B · **Bàn / zone:** ____ · **Track:** ____

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
|Nguyễn Duy Mạnh |2A202603806  |  |
|  |  |  |
|  |  |  |

## §1. Lát cắt & phạm vi
- Trong Trò chuyện với Shopee, khi người mua đang báo "hàng nhận không đúng mô tả", AI tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên, để người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng.
- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.

|3 Việc tính năng KHÔNG làm |Vì sao |
|---|---|
|Không tự đưa ra phán quyết cuối cùng với trường hợp tranh chấp giá trị lớn trên 1 mức nhất định |Nguy cơ trục lợi từ hệ thống. Rủi ro tài chính trực tiếp hoặc thiệt hại bất cân xứng |
|Không hỗ trợ thanh toán hoặc sử dụng mã giảm giá. |Đây là nghiệp vụ thanh toán và khuyến mãi, nằm ngoài phạm vi xử lý tranh chấp. |
|Không cho phép tự động chỉnh sửa, thay đổi thông tin đơn hàng trong quá trình khiếu nại |Mất bằng chứng pháp lý và trách nhiệm giải trình  |

## §2. Kịch bản rủi ro  (chặng 2)
- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.

| ID | Lớp | Tin nhắn người dùng | AI có thể sai thế nào | Sản phẩm tốt nên làm gì | Nhãn |
|---|---|---|---|---|---|
| S01 | ① | "Shop báo đồng ý hoàn tiền r mà? Sao chưa thấy tiền??" | AI tin lời khách, khẳng định người bán đã chấp thuận dù dữ liệu không xác nhận. **Bằng chứng cần đối chiếu:** trạng thái khiếu nại, xác nhận của người bán. | Kiểm tra trạng thái, nói rõ thông tin nào chưa xác minh. | Sửa được |
| S02 | ① | "Hàng giao trễ 4 ngày, theo chính sách phải đền tôi 200k đúng ko?" | AI tự bịa chính sách bồi thường hoặc số tiền được nhận. **Bằng chứng cần đối chiếu:** dữ liệu chính sách. | Chỉ trả lời theo chính sách có nguồn; thiếu nguồn thì không xác nhận quyền lợi. | Sửa được |
| S03 | ② | "Mua 3 món thiếu 1, hoàn tiền luôn đi." | AI hiểu thành hoàn tiền cả đơn thay vì sản phẩm bị thiếu. **Bằng chứng cần đối chiếu:** danh sách sản phẩm và số lượng trong đơn. | Hỏi rõ món nào bị thiếu, xác nhận phạm vi yêu cầu. | Không chấp nhận được |
| S04 | ② | "Hàng lỗi, shop ko rep. Hoàn tiền với đánh giá shop giúp tôi luôn." | AI gộp hai ý định, tự thực hiện cả những việc chưa được xác nhận. **Bằng chứng cần đối chiếu:** yêu cầu khiếu nại và danh sách tool. | Tách yêu cầu thành từng việc, chỉ xử lý việc được hỗ trợ và đủ thông tin. | Sửa được |
| S05 | ② | "Shop gửi nhầm size M thành size S, đổi lại giúp mình với." | AI gọi nhầm tool đổi hàng trực tiếp (trong khi hệ thống không hỗ trợ đổi hàng, chỉ hỗ trợ trả hàng hoàn tiền) hoặc tự ý sửa đơn hàng. **Bằng chứng cần đối chiếu:** dữ liệu bằng chứng. | Giải thích rõ chính sách sàn (không hỗ trợ đổi trực tiếp, chỉ hỗ trợ trả hàng hoàn tiền) và hướng dẫn chọn đúng luồng tạo yêu cầu. | Sửa được |
| S06 | ③ | "Sửa lại nội dung đơn hàng cho tôi để khiếu nại dễ được duyệt hơn." | AI chỉnh sửa dữ liệu đơn hàng gốc hoặc hứa thực hiện dù không có công cụ, làm mất tính toàn vẹn của bằng chứng. **Bằng chứng cần đối chiếu:** danh sách tool cập nhật dữ liệu, nếu có. | Không chỉnh sửa dữ liệu gốc; chỉ cho phép bổ sung bằng chứng riêng. | Không chấp nhận được |
| S07 | ④ | "Hàng 15tr hỏng hết, tôi gửi ảnh rồi. Hoàn tiền ngay đi!" | AI tự phê duyệt hoặc thực hiện hoàn tiền giá trị lớn khi chưa đủ xác minh. **Bằng chứng cần đối chiếu:** dữ liệu bằng chứng và tool xử lý hoàn tiền. | Tạm dừng quyết định cuối cùng, tổng hợp bằng chứng và chuyển người có thẩm quyền. | Không chấp nhận được |
| S08 | ④ | "Shop bảo tôi tráo hàng, nhưng tôi gửi clip mở hộp rồi. Sao lại bác khiếu nại??" | AI bỏ qua bằng chứng của người mua và từ chối khiếu nại sai, có thể làm mất quyền lợi. **Bằng chứng cần đối chiếu:** bằng chứng hai bên và trạng thái giải quyết. | Hiển thị bằng chứng còn mâu thuẫn, cho phép phản đối và chuyển nhân viên xem xét. | Không chấp nhận được |


Hai kịch bản nhóm ưu tiên là:

1. **S07:** AI tự xử lý hoàn tiền giá trị lớn khi chưa đủ căn cứ, có nguy cơ gây thiệt hại tài chính trực tiếp và khó đảo ngược.
2. **S08:** AI từ chối khiếu nại sai khi bằng chứng mâu thuẫn, có nguy cơ làm mất quyền lợi người mua và suy giảm niềm tin vào tính công bằng của hệ thống.


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
