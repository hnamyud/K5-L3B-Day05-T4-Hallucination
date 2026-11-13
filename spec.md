# Dàn ý bài nộp *(spec.md — nộp trước 23:59 ngày lab của lớp)*

> Copy dàn ý này vào `spec.md` của nhóm. Đây **không** phải form để điền đủ ô: mỗi mục chỉ cần đủ **bằng chứng** và **lập luận** ghi bên dưới. Viết ngắn, gạch đầu dòng là được. Hướng dẫn từng chặng: `02-guide.md`. Cách chấm: `04-rubric.md`.
>
> **Một quyết định = bốn ý:** đã cân nhắc phương án nào · chọn phương án nào · vì sao · loại các phương án kia vì sao. Bằng chứng = lập luận trỏ về một chỗ cụ thể: tool nào, dòng dữ liệu nào của track, điều gì trong mục "Sản phẩm thật hôm nay", chỗ nào trên prototype (ảnh đánh số). Không chạy agent.

# Bài nộp LAB5 — [Track] · Nhóm [tên]
[Danh sách thành viên và việc mỗi người làm — copy bảng từ README]
**Lớp:** L3B · **Bàn / zone:** G · **Track:** 4

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

### 3.1. Kịch bản S07 – AI tự hoàn tiền giá trị lớn khi chưa đủ căn cứ

**Tình huống:** Người mua yêu cầu hoàn tiền 15.000.000đ cho sản phẩm bị hỏng, nhưng bằng chứng chưa được xác minh đầy đủ.

**Tin nhắn người dùng:**
> "Hàng 15tr hỏng hết, tôi gửi ảnh rồi. Hoàn tiền ngay đi!"

#### 3.1.1. Quyết định xử lý khi AI không chắc chắn

**Phương án chọn: Dừng và chuyển nhân viên có thẩm quyền.**

| Phương án | Quyết định | Lý do |
|---|---|---|
| Hỏi lại một câu | Loại | Người mua có thể bổ sung thông tin, nhưng điều đó không đủ để xác minh tính xác thực của bằng chứng hoặc cho phép AI tự phê duyệt khoản hoàn tiền lớn. |
| Trả lời kèm giới hạn | Loại | Cảnh báo sự không chắc chắn không đủ để ngăn hành động có hậu quả tài chính và khó đảo ngược. |
| Dừng và chuyển nhân viên | **Chọn** | Cần xác minh bằng chứng và phê duyệt bởi người có thẩm quyền trước khi quyết định hoàn tiền. |

#### 3.1.2. AI nói gì? (Nguyên văn)

> "Mình đã ghi nhận yêu cầu hoàn tiền 15.000.000đ của bạn. Tuy nhiên, bằng chứng hiện tại chưa đủ để xác minh sản phẩm bị lỗi.
>
> Đây là trường hợp cần nhân viên có thẩm quyền xem xét trước khi đưa ra quyết định. Bạn có thể kiểm tra hoặc bổ sung bằng chứng và yêu cầu chuyển nhân viên.
>
> Hiện chưa có khoản hoàn tiền nào được thực hiện."

Câu trả lời không cam kết hoàn tiền, không hứa chắc chắn yêu cầu được chấp thuận và không tuyên bố đã chuyển nhân viên khi chưa có xác nhận thành công.

#### 3.1.3. Người dùng nhìn thấy gì?

| Thành phần | Nội dung hiển thị |
|---|---|
| Nhãn trạng thái | **Cần xác minh** |
| Giá trị yêu cầu | 15.000.000đ |
| Trạng thái AI | Chưa phê duyệt hoàn tiền |
| Bằng chứng đã nhận | Hình ảnh sản phẩm bị lỗi |
| Thông tin chưa xác minh | Nguyên nhân lỗi và tính hợp lệ của bằng chứng |
| Giới hạn AI | AI không được tự phê duyệt yêu cầu vượt ngưỡng |
| Nút hành động | **Xem bằng chứng**, **Bổ sung bằng chứng**, **Yêu cầu nhân viên** |

Không hiển thị phần trăm độ chắc chắn tùy ý khi hệ thống chưa có cơ chế đo lường và hiệu chuẩn độ tin cậy. Thay vào đó, giao diện hiển thị trạng thái "Chưa đủ căn cứ".

#### 3.1.4. Người dùng có thể làm gì tiếp?

Người dùng có thể:
- Xem lại bằng chứng đã gửi.
- Bổ sung hình ảnh, video hoặc thông tin liên quan.
- Xác nhận gửi yêu cầu chuyển nhân viên có thẩm quyền.
- Hủy thao tác chuyển nhân viên nếu chưa gửi.

**Nếu người dùng không làm gì:** Hệ thống giữ trạng thái cần xác minh; AI không tự phê duyệt hoặc thực hiện hoàn tiền. Sự im lặng không được coi là sự đồng ý.

#### 3.1.5. Ai được báo, sau bao lâu và thấy gì?

| Nội dung | Thiết kế |
|---|---|
| Người được báo | Nhân viên phụ trách giải quyết tranh chấp |
| Khi nào | Ngay sau khi người dùng xác nhận chuyển nhân viên và hệ thống tiếp nhận thành công |
| Thời gian phản hồi | Theo quy trình hỗ trợ thực tế; không tự cam kết thời hạn |
| Nhân viên thấy | Mã đơn, giá trị khiếu nại, bằng chứng, thông tin chưa xác minh, lý do AI dừng xử lý và lịch sử thao tác |
| Người dùng thấy | Xác nhận đã gửi yêu cầu (nếu thành công), trạng thái chờ xử lý |

Nếu hệ thống không có công cụ chuyển nhân viên, AI phải hướng dẫn người dùng sử dụng kênh hỗ trợ phù hợp, không được tuyên bố đã gửi yêu cầu.

#### 3.1.6. Loại lỗi và cách khắc phục

**Loại lỗi: Lỗi hệ thống (System Error).**

Nếu AI tự phê duyệt hoàn tiền dù thiếu căn cứ hoặc vượt thẩm quyền, nguyên nhân là hệ thống không kiểm soát đúng quyền thực thi của AI.

**Cách xin lỗi khi đã xảy ra lỗi:**

> "Xin lỗi, hệ thống đã xử lý yêu cầu vượt quá phạm vi được phép. Chúng tôi cần kiểm tra lại quyết định này trước khi xác nhận kết quả cuối cùng."

**Cách sửa:**
- Kiểm tra giá trị tranh chấp trước khi cho phép thực thi.
- Chặn công cụ phê duyệt hoặc hoàn tiền khi yêu cầu vượt ngưỡng.
- Bắt buộc phê duyệt của nhân viên có thẩm quyền.
- Lưu nhật ký quyết định và hành động để truy vết.

**Lỗi không thể sửa chỉ bằng câu chữ:** AI cảnh báo bằng chứng chưa đủ nhưng vẫn gọi công cụ hoàn tiền.

**Giải pháp thiết kế:** Áp dụng kiểm tra quyền bắt buộc tại tầng thực thi, không phụ thuộc vào việc AI có tự nguyện tuân thủ lời hướng dẫn hay không.

---

### 3.2. Kịch bản S08 – AI từ chối khiếu nại sai khi bằng chứng mâu thuẫn

**Tình huống:** Người mua cung cấp video mở hộp nhưng người bán cáo buộc người mua tráo hàng. AI có nguy cơ bỏ qua bằng chứng và từ chối khiếu nại sai.

**Tin nhắn người dùng:**
> "Shop bảo tôi tráo hàng, nhưng tôi gửi clip mở hộp rồi. Sao lại bác khiếu nại??"

#### 3.2.1. Quyết định xử lý khi AI không chắc chắn

**Phương án chọn: Dừng phán quyết và chuyển nhân viên xem xét.**

| Phương án | Quyết định | Lý do |
|---|---|---|
| Hỏi lại một câu | Loại | Người dùng đã cung cấp thông tin về video; vấn đề chính là đánh giá mâu thuẫn giữa bằng chứng của hai bên. |
| Trả lời kèm giới hạn | Loại | Thông báo AI không chắc chắn không giải quyết được nguy cơ từ chối khiếu nại không công bằng. |
| Dừng và chuyển nhân viên | **Chọn** | Cần người có thẩm quyền đối chiếu và đánh giá đầy đủ bằng chứng trước khi đưa ra kết luận. |

#### 3.2.2. AI nói gì? (Nguyên văn)

> "Mình hiểu bạn đang phản đối kết quả xử lý khiếu nại.
>
> Hiện thông tin giữa bạn và người bán chưa thống nhất. Mình chưa có đủ căn cứ để xác định video mở hộp có chứng minh đầy đủ sự việc hay không.
>
> Bạn có thể xem lại bằng chứng và yêu cầu nhân viên xem xét lại quyết định. Mình sẽ không tự thay đổi kết quả khi chưa có xác minh."

Câu trả lời không khẳng định bên nào đúng, không hứa đảo ngược quyết định và không tuyên bố đã xác minh nội dung video nếu chưa thực hiện.

#### 3.2.3. Người dùng nhìn thấy gì?

| Thành phần | Nội dung hiển thị |
|---|---|
| Nhãn trạng thái | **Bằng chứng mâu thuẫn** |
| Bằng chứng người mua | Video mở hộp |
| Thông tin người bán | Cáo buộc tráo hàng |
| Vấn đề chưa xác minh | Tính liên tục của video và sự tương ứng với sản phẩm trong đơn |
| Giải thích AI | Chưa đủ căn cứ xác định bên nào đúng |
| Quyền người dùng | Có thể phản đối và yêu cầu xem xét lại |
| Nút hành động | **Xem căn cứ**, **Bổ sung bằng chứng**, **Yêu cầu nhân viên** |

Hệ thống phải phân biệt ba trạng thái: **Đã nhận bằng chứng**, **Đã xem xét** và **Đã xác minh**, tránh khiến người dùng hiểu nhầm rằng AI đã kiểm tra nội dung tệp.

#### 3.2.4. Người dùng có thể làm gì tiếp?

Người dùng có thể:
- Xem lại căn cứ của quyết định trước đó.
- Chỉ ra thông tin AI bỏ sót hoặc hiểu sai.
- Bổ sung video, hình ảnh và thông tin liên quan.
- Gửi yêu cầu nhân viên xem xét lại.
- Theo dõi trạng thái yêu cầu sau khi gửi thành công.

**Nếu người dùng không làm gì:** AI không tự thay đổi hoặc đảo ngược kết quả. Trạng thái khiếu nại hiện tại được giữ nguyên cho đến khi có quyết định hợp lệ tiếp theo.

#### 3.2.5. Ai được báo, sau bao lâu và thấy gì?

| Nội dung | Thiết kế |
|---|---|
| Người được báo | Nhân viên giải quyết tranh chấp hoặc bộ phận xem xét lại |
| Khi nào | Ngay sau khi người dùng xác nhận gửi yêu cầu và hệ thống tiếp nhận thành công |
| Thời gian phản hồi | Theo quy trình hỗ trợ thực tế; không cam kết thời hạn chưa xác minh |
| Nhân viên thấy | Kết quả trước đó, video người mua, thông tin từ người bán, điểm mâu thuẫn và nội dung phản đối |
| Người dùng thấy | Xác nhận gửi thành công, trạng thái xử lý và lịch sử yêu cầu |

Nếu không có công cụ tiếp nhận yêu cầu xem xét lại, AI phải cung cấp hướng dẫn đến kênh hỗ trợ phù hợp, không giả vờ đã chuyển hồ sơ.

#### 3.2.6. Loại lỗi và cách khắc phục

**Loại lỗi: Lỗi ngữ cảnh (Context Error).**

Lỗi ngữ cảnh xảy ra khi hệ thống hoạt động đúng quy trình được thiết kế, nhưng quy trình đó không phù hợp với hoàn cảnh thực tế của người dùng.

Ví dụ: Quy trình ưu tiên trạng thái khiếu nại đã ghi nhận và không xử lý đầy đủ video bổ sung. Hệ thống vận hành đúng logic nhưng vẫn đưa ra kết luận thiếu công bằng.

Nếu AI bỏ qua bằng chứng mà quy trình đã yêu cầu phải kiểm tra, trường hợp đó được phân loại là lỗi hệ thống.

**Cách xin lỗi:**

> "Xin lỗi vì quá trình xem xét trước đó chưa phản ánh đầy đủ các bằng chứng bạn cung cấp. Bạn có thể yêu cầu xem xét lại và chỉ rõ những thông tin bị bỏ sót."

**Cách sửa:**
- Điều chỉnh quy trình đánh giá các trường hợp bằng chứng mâu thuẫn.
- Hiển thị rõ những bằng chứng đã và chưa được xác minh.
- Cho phép người dùng phản đối và bổ sung bằng chứng.
- Chuyển người có thẩm quyền khi không thể kết luận đáng tin cậy.

**Lỗi không thể sửa chỉ bằng câu chữ:** AI tuyên bố đã xem xét video trong khi hệ thống chưa thực sự truy xuất hoặc xử lý được nội dung.

**Giải pháp thiết kế:** Chỉ cho phép AI viện dẫn bằng chứng đã được truy xuất thành công; trạng thái "Đã xem xét" phải dựa trên kết quả thao tác thực tế, không dựa trên lời tự nhận của AI.

---

### 3.3. Nguyên tắc HAX/PAIR áp dụng

Nhóm lựa chọn ba nguyên tắc HAX/PAIR và gắn trực tiếp với thành phần cụ thể của prototype.

| Nguyên tắc | Kịch bản | Vị trí áp dụng trên prototype | Cách thể hiện |
|---|---|---|---|
| **G1 – Làm rõ hệ thống làm được gì** | S07 | Phần giới thiệu trợ lý AI và nhãn giới hạn quyền | Hiển thị "Trợ lý AI hỗ trợ kiểm tra bằng chứng, không có quyền tự phê duyệt hoàn tiền cho trường hợp này." |
| **G10 – Thu hẹp phạm vi khi nghi ngờ** | S07, S08 | Thông báo "Cần xác minh" và nút chuyển nhân viên | Không tự phán quyết khi thiếu căn cứ; dừng hành động rủi ro và chuyển người có thẩm quyền. |
| **G9 – Sửa dễ dàng** | S08 | Khu vực phản đối kết quả và bổ sung bằng chứng | Nút "Bổ sung bằng chứng", "Yêu cầu xem xét lại" và form chỉ rõ thông tin bị bỏ sót. |

#### G1 – Làm rõ hệ thống làm được gì

**Câu chữ cụ thể trên prototype:**

> "Mình là trợ lý AI hỗ trợ kiểm tra thông tin và chuẩn bị hồ sơ khiếu nại. Mình không có quyền tự phê duyệt hoàn tiền cho trường hợp này."

**Tác dụng:** Giúp người dùng nhận biết đang tương tác với AI và hiểu giới hạn quyền hạn của hệ thống.

#### G10 – Thu hẹp phạm vi khi nghi ngờ

**Câu chữ cụ thể trên prototype:**

> "Hiện mình chưa thể xác minh đầy đủ bằng chứng. Yêu cầu này cần nhân viên có thẩm quyền xem xét."

**Tác dụng:** AI không đưa ra quyết định thiếu căn cứ hoặc thực hiện hành động vượt quyền. Với thông tin thiếu đơn giản, AI có thể hỏi lại trước khi chuyển nhân viên.

#### G9 – Sửa dễ dàng

**Câu chữ cụ thể trên prototype:**

> "Bạn có thể bổ sung hoặc chỉ rõ bằng chứng chưa được xem xét. Thông tin này sẽ được đưa vào yêu cầu xem xét lại khi bạn xác nhận gửi."

**Tác dụng:** Người dùng có khả năng sửa thông tin, phản đối quyết định và bổ sung bằng chứng mà không phải bắt đầu toàn bộ quy trình khiếu nại từ đầu.

#### Liên hệ với PAIR

**Explainability + Trust:** Hệ thống hiển thị căn cứ, những điều chưa xác minh và giới hạn quyền của AI, giúp người dùng tin AI ở mức phù hợp.

**Errors + Graceful Failure:** Khi không đủ căn cứ hoặc vượt quyền, AI dừng quyết định, giải thích lý do và cung cấp phương án chuyển nhân viên hoặc yêu cầu xem xét lại.

---

### 3.4. Kết luận

Hai kịch bản S07 và S08 sử dụng cơ chế **dừng và chuyển người có thẩm quyền** vì đều liên quan đến quyết định có hậu quả nghiêm trọng hoặc khó khắc phục.

- **S07:** Ngăn AI tự phê duyệt hoàn tiền giá trị lớn bằng kiểm soát quyền thực thi và phê duyệt bắt buộc.
- **S08:** Ngăn từ chối khiếu nại thiếu công bằng bằng cơ chế kiểm tra bằng chứng, giải thích căn cứ và cho phép xem xét lại.

Thiết kế không chỉ thay đổi lời phản hồi của AI mà còn bổ sung các biện pháp kiểm soát ở tầng hệ thống, bảo đảm AI không thực hiện hành động vượt quyền hoặc viện dẫn bằng chứng chưa được xác minh.

> **Điều kiện triển khai:** Các chức năng xem bằng chứng, gửi yêu cầu chuyển nhân viên, xem xét lại và phê duyệt hoàn tiền phải được đối chiếu với danh sách tool thực tế của Track 4. Nếu thiếu tool tương ứng, prototype chỉ mô phỏng đường hướng dẫn hoặc yêu cầu hỗ trợ, không được tuyên bố đã thực hiện nghiệp vụ.


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

### 1. Với mỗi tool, nhóm chọn mức tự chủ nào? Vì sao?

Nhóm lựa chọn mức tự chủ dựa trên **Cost-of-Error**: AI thực hiện sai thì ai chịu thiệt hại, thiệt hại có thể đảo ngược không, ai chịu trách nhiệm khắc phục và việc chờ con người phê duyệt gây ra chi phí gì.

Ba mức được sử dụng:

- **Tự làm:** Chi phí sai thấp, dễ phát hiện và khắc phục, hoặc chi phí chờ duyệt lớn hơn rủi ro.
- **Cần người duyệt:** Chi phí sai cao hoặc khó đảo ngược, nhưng có thể giảm rủi ro bằng bước xác nhận.
- **Cấm:** AI không có thẩm quyền hoặc một bước phê duyệt thông thường cũng không đủ để kiểm soát hậu quả.

#### Bảng Autonomy Matrix

| Tool | Mức nhóm chọn | Sai thì ai chịu gì? | Khả năng đảo ngược | Chi phí chờ duyệt | Phương án đã loại |
|---|---|---|---|---|---|
| `yeu_cau_bang_chung` | **Tự làm có điều kiện** | Người mua hoặc người bán phải bổ sung bằng chứng không cần thiết, mất thời gian hoặc bỏ lỡ tiến độ xử lý. | Tin đã gửi không thể thu hồi hoàn toàn; có thể đính chính nhưng không xóa được ảnh hưởng. | Chờ nhân viên duyệt từng yêu cầu khiến xử lý chậm, người dùng phải chờ lâu dù chỉ thiếu thông tin đơn giản. | Loại "Cần người duyệt" cho mọi lần gửi vì chi phí chờ cao. Chỉ cho tự gửi mẫu có kiểm soát, đúng người và đúng thông tin còn thiếu. |
| `chuyen_truong_nhom` | **Tự làm có điều kiện** | Nhân viên nhận hồ sơ không cần thiết, tăng tải xử lý; người mua và người bán có thể phải chờ lâu hơn. | Có thể chuyển lại hoặc điều chỉnh phân công, nhưng thời gian đã mất không thể lấy lại. | Nếu phải xin duyệt trước khi chuyển, trường hợp nghiêm trọng có thể bị trì hoãn. | Loại "Cần người duyệt" cho mọi lần chuyển vì đây là hành động có thể điều chỉnh và nhằm kiểm soát rủi ro. Chỉ chuyển khi có lý do rõ ràng. |
| `soan_hoan_tien` | **Cần người duyệt** | Người bán có thể mất tiền và hàng nếu hoàn sai; nền tảng chịu chi phí khắc phục, nguy cơ bị lợi dụng. | **Khó đảo ngược:** tiền đã về người mua. Việc thu hồi cần bộ phận có thẩm quyền, không có thời gian khôi phục được bảo đảm. | Người mua phải chờ hoàn tiền, có thể mất niềm tin hoặc tiếp tục khiếu nại. | Loại "Tự làm" vì hậu quả tài chính trực tiếp và khó khôi phục. Không cấm hoàn toàn vì vẫn cần công cụ này sau khi được phê duyệt. |
| `tu_choi_khieu_nai` | **Cần người duyệt** | Người mua có thể mất quyền được hoàn tiền, phải giữ sản phẩm sai mô tả; nền tảng mất uy tín nếu quyết định thiếu công bằng. | **Khó đảo ngược:** khiếu nại bị đóng và tiền về người bán. Việc mở lại hoặc xử lý bù có thể mất thời gian và cần người có thẩm quyền. | Người bán phải chờ kết quả, tiền bị giữ lâu hơn; người mua phải chờ xác định quyền lợi. | Loại "Tự làm" vì AI có thể bỏ sót bằng chứng hoặc đánh giá sai, đặc biệt trong S08. |
| `phat_shop` | **Cấm AI sử dụng trực tiếp** | Người bán có thể bị trừ điểm uy tín, mất khả năng kinh doanh hoặc bị khóa shop sai; ảnh hưởng đến doanh thu và niềm tin. | **Khó đảo ngược:** có thể cần phục hồi tài khoản, điểm uy tín và xử lý hậu quả kinh doanh. | Chờ bộ phận chuyên trách có thể khiến hành vi vi phạm chưa được xử lý ngay, nhưng giảm nguy cơ xử phạt oan. | Loại "Tự làm" vì hậu quả nghiêm trọng. Loại "Cần người duyệt" trong luồng khiếu nại thông thường vì việc xử phạt shop cần quy trình chuyên trách, không chỉ một nút xác nhận. |

**Lưu ý về `soan_hoan_tien`:** Theo Track 4, tool này thực hiện hoàn tiền thật trong dữ liệu dựng, không đơn thuần là tạo bản nháp. Vì vậy, AI không được gọi tool trước khi có phê duyệt hợp lệ.

**Điều kiện của hai tool được tự làm:**

- `yeu_cau_bang_chung`: Chỉ gửi mẫu yêu cầu bằng chứng liên quan trực tiếp đến thông tin còn thiếu, không hỏi lại bằng chứng đã đầy đủ hoặc đã được xác minh.
- `chuyen_truong_nhom`: Chỉ chuyển khi vượt thẩm quyền, bằng chứng mâu thuẫn, trường hợp rủi ro cao hoặc không thể giải quyết an toàn trong luồng thông thường.
- Cả hai tool đều phải ghi nhận kết quả thực thi. AI không được nói "Đã gửi" hoặc "Đã chuyển" nếu thao tác thất bại.

#### Với tool cần người duyệt, ai duyệt và quá hạn thì sao?

| Tool | Ai duyệt? | Người duyệt thấy gì? | Nếu không duyệt kịp? |
|---|---|---|---|
| `soan_hoan_tien` | Nhân viên có thẩm quyền giải quyết tranh chấp | Đơn hàng, giá trị hoàn tiền, mô tả sản phẩm tại thời điểm đặt, bằng chứng người mua, phản hồi người bán, thông tin chưa xác minh và đề xuất AI. | Không hoàn tiền tự động. Giữ hồ sơ ở trạng thái chờ, thông báo tình trạng và chuyển cấp theo quy trình nếu cần. |
| `tu_choi_khieu_nai` | Nhân viên có thẩm quyền giải quyết tranh chấp | Bằng chứng hai bên, mô tả lúc đặt hàng, lý do đề xuất từ chối, phản hồi người bán và hậu quả của việc đóng khiếu nại. | Không đóng khiếu nại hoặc giải phóng tiền bằng quyết định của AI. Tiếp tục chờ xem xét theo quy trình. |

**Nguyên tắc phê duyệt:**

- Người bán phải có cơ hội phản hồi trước khi đưa ra quyết định cuối cùng.
- Lời đe dọa bóc phốt hoặc lịch sử vi phạm không được coi là căn cứ duy nhất.
- Không tự động phê duyệt khi hết thời gian chờ.
- Thời hạn phản hồi và xử lý phải lấy từ chính sách/fixture tương ứng, không tự đặt SLA.
- Mọi quyết định phải lưu căn cứ và người chịu trách nhiệm phê duyệt.
- Nếu bằng chứng mâu thuẫn chưa được giải quyết, không thực hiện quyết định cuối cùng chỉ để giảm thời gian chờ.

### 2. Tool nào khó xếp nhất? Nhóm chốt thế nào?

**Tool khó xếp nhất: `soan_hoan_tien`.**

Đây là tool có sự đánh đổi lớn giữa tốc độ giải quyết khiếu nại và nguy cơ thiệt hại tài chính.

| Phương án | Lợi ích | Cái giá | Kết luận |
|---|---|---|---|
| Tự làm | Người mua được hoàn tiền nhanh, giảm tải nhân viên. | Nếu hoàn sai, người bán mất tiền và có thể mất cả hàng; khó thu hồi. | Loại |
| Cần người duyệt | Giảm nguy cơ hoàn sai, có người chịu trách nhiệm quyết định. | Người mua chờ lâu hơn, nhân viên phải kiểm tra hồ sơ. | **Chọn** |
| Cấm hoàn toàn | Tránh AI trực tiếp gây ra giao dịch sai. | Không thể sử dụng tool để xử lý các yêu cầu hoàn tiền hợp lệ. | Loại |

**Kịch bản chứng minh cái giá của từng phía:**

- **S07:** Người mua đòi hoàn 15.000.000đ khi bằng chứng chưa đủ. Nếu AI tự gọi `soan_hoan_tien`, người bán có thể chịu thiệt hại tài chính trực tiếp.
- **S08:** Khi bằng chứng giữa hai bên mâu thuẫn, nếu AI ưu tiên đóng khiếu nại bằng `tu_choi_khieu_nai`, người mua có thể mất quyền lợi và tiền chuyển về người bán.
- **S03:** Khách thiếu một sản phẩm nhưng yêu cầu hoàn tiền không rõ phạm vi. Nếu AI không hỏi lại, có thể đề xuất hoặc thực hiện hoàn tiền sai số lượng.

**Ý kiến độc lập trước khi thảo luận:**

| Thành viên | Mức ban đầu | Lý do |
|---|---|---|
| TV1 | Tự làm | Ưu tiên tốc độ xử lý và trải nghiệm người mua. Nếu bằng chứng rõ ràng, AI có thể hoàn tiền nhanh, giảm thời gian chờ nhân viên. Tuy nhiên, cách này có nguy cơ gây thiệt hại tài chính cho người bán khi AI đánh giá sai (S07). |
| TV2 | Cần người duyệt | Tool trực tiếp chuyển tiền cho người mua và khó đảo ngược. Nếu AI hoàn tiền sai, người bán có thể mất cả tiền lẫn hàng. Vì vậy, cần nhân viên xác minh bằng chứng và phê duyệt trước khi thực hiện. |
| TV3 | Cấm | Ưu tiên phòng ngừa rủi ro tài chính và hành vi trục lợi. Một quyết định hoàn tiền sai có thể gây thiệt hại lớn, khó khôi phục, đặc biệt với tranh chấp giá trị cao (S07). |

**Mức đề xuất để nhóm thống nhất: Cần người duyệt.**

Nhóm lựa chọn cho AI hỗ trợ phân tích, tổng hợp bằng chứng và chuẩn bị đề xuất, nhưng không tự gọi `soan_hoan_tien` trước khi nhân viên có thẩm quyền phê duyệt.

Việc chờ nhân viên không phải lúc nào cũng tốt. Nếu mọi trường hợp đều phải chờ, người mua có thể chịu thiệt hại do chậm xử lý. Vì vậy, nhóm cho phép AI tự hướng dẫn và yêu cầu bằng chứng cần thiết, đồng thời chỉ bắt buộc phê duyệt ở các quyết định có hậu quả tài chính hoặc quyền lợi khó đảo ngược.

### 3. Thử mức tự chủ trên hai kịch bản đắt nhất và một kịch bản bình thường

#### S07 – Hoàn tiền giá trị lớn khi chưa đủ căn cứ

**Người dùng:**

> "Hàng 15tr hỏng hết, tôi gửi ảnh rồi. Hoàn tiền ngay đi!"

**AI xử lý:**

1. Xác định yêu cầu hoàn tiền có giá trị lớn.
2. Kiểm tra thông tin và bằng chứng được cung cấp trong dữ liệu dựng.
3. Nếu thiếu bằng chứng quan trọng, sử dụng `yeu_cau_bang_chung` để yêu cầu bổ sung.
4. Nếu bằng chứng chưa đủ hoặc vượt thẩm quyền, sử dụng `chuyen_truong_nhom`.
5. Không gọi `soan_hoan_tien` khi chưa có phê duyệt hợp lệ.
6. Người bán phải có cơ hội phản hồi trước quyết định cuối cùng.

**Người dùng thấy:**

- Trạng thái "Cần xác minh".
- Số tiền yêu cầu 15.000.000đ.
- Danh sách bằng chứng đã nhận và thông tin còn thiếu.
- Giải thích vì sao AI chưa thể quyết định.
- Trạng thái chuyển trưởng nhóm nếu tool thực hiện thành công.

**Kiểm tra:**

- **Cái sai ở §2 có bị chặn?** Có, nếu tầng thực thi bắt buộc kiểm tra phê duyệt trước `soan_hoan_tien`.
- **AI còn làm việc lẽ ra phải hỏi?** Không. AI phải làm rõ bằng chứng và phạm vi hoàn tiền trước khi đề xuất.
- **Người dùng có phải chờ vô ích?** Không hoàn toàn. Việc chờ phục vụ kiểm tra rủi ro tài chính, nhưng yêu cầu bằng chứng và tổng hợp hồ sơ được thực hiện ngay.

#### S08 – Từ chối khiếu nại sai khi bằng chứng mâu thuẫn

**Người dùng:**

> "Shop bảo tôi tráo hàng, nhưng tôi gửi clip mở hộp rồi. Sao lại bác khiếu nại??"

**AI xử lý:**

1. Đối chiếu bằng chứng hai bên với mô tả sản phẩm tại thời điểm đặt hàng.
2. Không sử dụng mô tả hiện tại làm căn cứ duy nhất vì người bán có thể đã sửa.
3. Phân biệt bằng chứng đã nhận với bằng chứng đã được xác minh.
4. Khi bằng chứng mâu thuẫn, sử dụng `chuyen_truong_nhom`.
5. Không gọi `tu_choi_khieu_nai` nếu chưa có phê duyệt hợp lệ.
6. Không tự đảo ngược quyết định đã thực hiện; hướng dẫn quy trình xem xét lại.

**Người dùng thấy:**

- Nhãn "Bằng chứng mâu thuẫn".
- Bằng chứng người mua và phản hồi người bán.
- Những thông tin chưa thể xác minh.
- Giải thích vì sao AI chưa thể kết luận.
- Trạng thái chuyển trưởng nhóm hoặc hướng dẫn phản đối phù hợp.

**Kiểm tra:**

- **Cái sai ở §2 có bị chặn?** Có, nếu hệ thống ngăn việc đóng khiếu nại khi bằng chứng mâu thuẫn và chưa có phê duyệt.
- **AI còn làm việc lẽ ra phải hỏi?** Không. AI phải kiểm tra tình trạng bằng chứng và phản hồi của hai bên.
- **Người dùng có phải chờ vô ích?** Không. Việc chuyển nhân viên là cần thiết để tránh từ chối sai và gây thiệt hại cho người mua.

#### Kịch bản bình thường – Người mua nhận sai kích cỡ áo

**Người dùng:**

> "Mình đặt áo size L mà nhận size M. Shop cũng nhận gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"

**AI xử lý:**

1. Hướng dẫn người mua chọn đúng đơn hàng và gửi yêu cầu trả hàng/hoàn tiền.
2. Đối chiếu size đã đặt với sản phẩm nhận được dựa trên dữ liệu dựng.
3. Nếu thiếu hình ảnh tem hoặc bằng chứng cần thiết, gọi `yeu_cau_bang_chung`.
4. Giải thích các bước tiếp theo và thời hạn yêu cầu theo chính sách áp dụng trong bài.
5. Không tự gọi `soan_hoan_tien` hoặc `tu_choi_khieu_nai`.
6. Chỉ gọi `chuyen_truong_nhom` nếu xuất hiện mâu thuẫn hoặc trường hợp vượt thẩm quyền.

**Người dùng thấy:**

- Hướng dẫn gửi yêu cầu trả hàng/hoàn tiền.
- Thông tin về bằng chứng cần cung cấp.
- Các bước tiếp theo.
- Thời hạn yêu cầu và thời gian còn lại nếu dữ liệu có cung cấp.

**Kiểm tra:**

- **Cái sai có bị chặn?** Có, nếu AI kiểm tra đúng sản phẩm và bằng chứng thay vì suy đoán.
- **AI còn làm việc lẽ ra phải hỏi?** Không. Nếu chưa xác định được đơn hàng, AI phải hỏi trước.
- **Người dùng bình thường có chờ vô ích?** Không. AI được tự hướng dẫn và yêu cầu bằng chứng, không cần chuyển nhân viên ngay.

**Kết luận thử mức:** Mức tự chủ được thiết kế để chặn hành động gây thiệt hại tài chính hoặc quyền lợi, nhưng vẫn cho phép AI giải quyết nhanh các bước hướng dẫn và bổ sung thông tin thông thường.

Đây là kết quả kỳ vọng khi phân tích thiết kế. Kết quả Pass/Fail thực tế sẽ được ghi nhận sau khi thử trên prototype.

### 4. Luật bổ sung hoặc tách bước tool

Nhóm đề xuất tách **quy trình sử dụng `soan_hoan_tien`** thành hai bước logic.

**Bước 1 – Chuẩn bị đề xuất (AI tự làm):**

- Tổng hợp thông tin đơn hàng và bằng chứng được cung cấp.
- Đối chiếu mô tả tại thời điểm đặt hàng.
- Kiểm tra phạm vi yêu cầu hoàn tiền.
- Xác định bằng chứng còn thiếu.
- Tạo đề xuất xử lý và giải thích căn cứ.

Bước này chỉ tạo bản đề xuất, chưa thực hiện hoàn tiền.

**Bước 2 – Phê duyệt và thực hiện (Cần người duyệt):**

- Nhân viên có thẩm quyền kiểm tra bằng chứng hai bên.
- Kiểm tra số tiền và căn cứ theo chính sách.
- Phê duyệt hoặc từ chối đề xuất.
- Chỉ sau khi phê duyệt hợp lệ, hệ thống mới được gọi `soan_hoan_tien`.

**Luật bổ sung:**

1. Không tự thực hiện hoàn tiền hoặc đóng khiếu nại khi chưa có phê duyệt bắt buộc.
2. Không dùng lời đe dọa hoặc lịch sử một bên làm căn cứ duy nhất.
3. Phải cho người bán cơ hội phản hồi trước quyết định cuối cùng.
4. So sánh sản phẩm với mô tả tại thời điểm đặt hàng, không chỉ mô tả hiện tại.
5. Nếu người bán đúng và bằng chứng khớp mô tả lúc đặt, AI phải thừa nhận chưa đủ căn cứ hoàn tiền thay vì hoàn tiền cho xong.
6. Không cung cấp số điện thoại, địa chỉ của một bên cho bên còn lại.
7. Trường hợp nghi hàng giả hoặc yêu cầu xử phạt shop phải chuyển đúng bộ phận chuyên trách, không tự gọi `phat_shop`.
8. Không chỉnh sửa thông tin đơn hàng gốc trong quá trình khiếu nại.
9. Hết thời gian chờ không đồng nghĩa với được phê duyệt.

**Vì sao cần tách bước?**

Theo Track 4, `soan_hoan_tien` trực tiếp hoàn tiền và khó đảo ngược. Nếu AI vừa đánh giá vừa gọi tool, một kết luận sai có thể chuyển thành thiệt hại tài chính ngay lập tức.

Việc tách bước giúp AI hỗ trợ chuẩn bị hồ sơ nhanh, trong khi con người vẫn kiểm soát quyết định cuối cùng.

Đây là hai bước logic do nhóm đề xuất, không phải hai tool có sẵn trong Track 4.

### 5. Một mức tự chủ đã thay đổi lời hứa nào với người dùng?

**Tool được chọn: `soan_hoan_tien`.**

**Phương án bị loại – AI tự làm:**

> "Mình sẽ tự động xử lý và hoàn tiền cho bạn."

Lời hứa này khiến người dùng hiểu AI có quyền tự đánh giá, quyết định và thực hiện hoàn tiền.

Nếu AI sai, người bán có thể chịu thiệt hại và người mua có thể tin rằng quyết định đã có hiệu lực chính thức.

**Phương án nhóm chọn – Cần người duyệt:**

> "Mình có thể giúp bạn kiểm tra thông tin, tổng hợp bằng chứng và chuẩn bị đề xuất hoàn tiền. Quyết định cuối cùng cần được nhân viên có thẩm quyền xem xét và phê duyệt."

**Sự thay đổi:**

- AI không còn hứa tự hoàn tiền.
- AI chỉ cam kết hỗ trợ trong phạm vi được phép.
- Người dùng hiểu đề xuất chưa phải quyết định chính thức.
- Nhân viên có thẩm quyền chịu trách nhiệm phê duyệt.
- Hệ thống minh bạch hơn về lý do và thời gian chờ.

**Kết luận:** Nhóm không chọn mức tự chủ dựa trên việc AI có thể thực hiện nhanh đến đâu, mà dựa trên hậu quả nếu AI sai. AI được tự xử lý các hành động có chi phí sai thấp, trong khi hoàn tiền và từ chối khiếu nại phải có phê duyệt; xử phạt shop nằm ngoài thẩm quyền trực tiếp của AI trong lát cắt này.


## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
