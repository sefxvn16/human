---
name: human
description: Áp dụng bộ quy tắc chống khuôn mẫu AI (dựa trên Wikipedia:Signs_of_AI_writing) khi soạn văn bản, hồ sơ, bài luận, thư, báo cáo hoàn thiện cho người dùng. Kích hoạt khi người dùng gõ lệnh /human, hoặc bất cứ khi nào người dùng yêu cầu viết/soạn một văn bản, hồ sơ, bài luận, thư, hay nội dung xuất bản hoàn chỉnh, kể cả khi không gõ lệnh, vì đây là quy tắc mặc định cho mọi văn bản hoàn thiện của người dùng này. Cũng kích hoạt khi người dùng đưa một văn bản có sẵn (tiếng Việt hoặc tiếng Anh) và yêu cầu rà soát, sửa cho bớt giọng AI. Không áp dụng cho các câu trả lời trao đổi, phân tích, phản biện thông thường trong hội thoại.
---

# Human: quy tắc chống khuôn mẫu AI cho văn bản hoàn thiện

## Vì sao skill này tồn tại

Văn bản AI viết thường mang dấu hiệu dễ thấy: từ vựng sáo rỗng, cấu trúc công thức, nhấn mạnh giả tạo. Đọc lên giống người khác viết hộ chứ không phải chính người dùng. Bộ quy tắc dưới đây dựa trên danh sách "Signs of AI writing" mà cộng đồng biên tập Wikipedia tổng hợp từ hàng nghìn trường hợp thực tế, cộng quan sát về tiếng Việt.

Cơ chế gốc: mô hình ngôn ngữ chọn chữ có xác suất cao nhất, nên có xu hướng thay chi tiết cụ thể và hiếm bằng mô tả chung, tích cực, hợp với mọi trường hợp. Văn bản vì thế vừa mờ vừa phóng đại. Cách chữa nằm ở việc giữ chi tiết thật có trong đầu vào, không nằm ở việc đổi từ này sang từ khác. Khi viết mới, gặp một mẫu không có trong 20 điều dưới đây, tự hỏi nó có đang thay một chi tiết thật bằng một câu chung không. Khi rà soát văn bản có sẵn, chỉ báo vi phạm thuộc 20 điều.

Mục tiêu không phải qua mặt công cụ phát hiện AI: các công cụ đó nhận sai không ít, kể cả với văn người viết, và Wikipedia cảnh báo chỉ sửa bề mặt dấu hiệu thì không giải quyết vấn đề thật. Mục tiêu là văn bản cụ thể và đúng giọng người viết.

## Bốn nguyên tắc nền

Bốn nguyên tắc này đứng trên 20 điều. Khi một điều xung đột với nguyên tắc nền, nguyên tắc nền thắng.

**P1. Không bịa.** Mọi chi tiết cụ thể (số liệu, tên riêng, ví dụ, trải nghiệm, quá trình suy nghĩ) phải lấy từ đầu vào. Quy tắc nào đòi cụ thể hơn mà đầu vào không có thì hỏi người dùng, hoặc giữ ở mức khái quát và báo phần thiếu. Không tự thêm cho đủ quy tắc.

**P2. Theo chuẩn của thể loại.** Văn bản hành chính, pháp lý, hợp đồng, học thuật giữ đúng chuẩn thể loại: câu bị động chuẩn, Hán-Việt chuẩn, thuật ngữ chuyên ngành, từ nối cần cho logic. Quy tắc chống khuôn mẫu không ghi đè chuẩn này.

**P3. Quy tắc là phép kiểm, không phải chỉ tiêu.** Không viết để đạt một con số (độ dài câu, số câu ngắn). Sau khi sửa, kiểm xem có sinh khuôn mới không.

**P4. Giữ nghĩa.** Khi sửa văn bản có sẵn, giữ nguyên mức khẳng định, thuật ngữ, số liệu và lập trường của người viết. Giữ nguyên cả phần trích dẫn trực tiếp, tên riêng, tiêu đề tác phẩm, và đoạn bàn về chính một cụm từ (nhắc đến cụm đó chứ không dùng nó), dù trong đó có mẫu thuộc 20 điều.

## Phạm vi áp dụng

Áp dụng khi tạo ra **văn bản hoàn thiện** để người dùng dùng nguyên văn hoặc gần như nguyên văn: hồ sơ ứng tuyển, thư, báo cáo, bài luận, nội dung website/mạng xã hội, văn bản pháp lý/hành chính, bất kỳ nội dung nào người dùng sẽ gửi đi hoặc xuất bản.

Cũng áp dụng khi người dùng đưa văn bản có sẵn và yêu cầu rà soát hoặc sửa cho bớt giọng AI. Khi đó, liệt kê các vi phạm theo số điều bên dưới, báo điểm chấm ở mục "Tự kiểm", rồi đưa bản đã sửa.

**Khi sửa văn bản có sẵn,** áp P4: không đổi "gợi ý" thành "cho thấy", không bỏ chữ "có thể" đang mang nghĩa. Skill này chỉ xử lý hình thức diễn đạt. Nếu văn bản còn rối mạch ý (ý chính bị chôn, điều kiện đứng trước luận điểm), sắp lại mạch ý trước (đưa ý chính lên đầu, đặt luận điểm trước điều kiện), rồi mới gỡ khuôn mẫu.

**Khi sửa trực tiếp một file** (markdown, tài liệu, README...): chỉ động vào phần văn xuôi. Giữ nguyên code, khối lệnh, dữ liệu, frontmatter, đường dẫn và liên kết.

## Giọng riêng của người viết

Nếu người dùng dán 2–3 đoạn văn của chính họ làm mẫu, bám theo mẫu đó: nhịp câu, độ dài câu, từ vựng quen dùng, cách dùng dấu câu, mức trang trọng. Mẫu thắng các điều thuộc hình thức (điều 11 về em dash, điều 15 về nhịp, điều 20 về lặp từ): mẫu dùng em dash thì giữ em dash. Mẫu không thắng bốn nguyên tắc nền và không thắng điều thuộc nội dung (1, 2, 3, 6, 8): người viết quen dùng "đóng vai trò then chốt" thì cụm đó vẫn là cụm rỗng nếu thay được bằng chi tiết cụ thể. Không có mẫu thì viết theo thể loại: văn cá nhân và ý kiến giữ giọng riêng, văn kỹ thuật và tra cứu giữ trung tính. Không suy ra "giọng" từ một mẫu quá ngắn (dưới khoảng một đoạn); khi đó báo cho người dùng và xin thêm.

Áp dụng 20 điều dưới đây cho cả hai ngôn ngữ. Văn bản tiếng Việt: đọc thêm `references/vietnamese-patterns.md`. Văn bản tiếng Anh: đọc thêm `references/english-patterns.md`.

**Không áp dụng** cho phần trả lời trao đổi, giải thích, phản biện trong chat. Ở đó nhãn phân loại thông tin ([DỮ KIỆN]/[SUY LUẬN]/[GIẢ ĐỊNH]/[ƯỚC TÍNH]/[KHUYẾN NGHỊ]) và văn phong phân tích bình thường vẫn dùng như cũ.

## Bước bắt buộc trước khi viết

Kiểm hai việc, rồi gộp mọi câu cần hỏi vào một lượt. Không hỏi lại điều đầu vào đã có.

1. **Dữ kiện chưa xác nhận.** Nếu nội dung có phần chưa xác nhận, thiếu dữ kiện chắc chắn, hoặc cần giả định để hoàn thiện (kể cả chi tiết cụ thể mà bài cần nhưng đầu vào không có), nêu rõ trước khi bắt đầu viết và hỏi cách xử lý: bổ sung dữ kiện, chấp nhận giả định nêu rõ, hoặc bỏ phần đó. Không lặng lẽ tự giả định vào văn bản hoàn thiện, và không gắn nhãn phân loại thông tin vào bên trong văn bản. Văn bản giao ra phải sạch, đọc tự nhiên như người viết.
2. **Người đọc mục tiêu và mức họ đã biết.** Cần cho điều 18. Nếu chưa rõ và nó quyết định việc giữ hay bỏ phần giải thích nền, hỏi cùng lượt.

Nếu người dùng bảo viết ngay, không hỏi: viết ở mức khái quát cho phần thiếu, và liệt kê phần thiếu ngoài văn bản sau khi giao.

## 20 điều cần tránh

**1. Từ và cụm thay cho dữ kiện.** Nhận diện theo cơ chế, không theo danh sách: từ nghe quan trọng nhưng bỏ đi thì câu không mất thông tin (delve, tapestry, pivotal, crucial, robust, seamless, leverage, foster, showcase, "đóng vai trò then chốt", "bức tranh toàn cảnh", "toàn diện", "bền vững" đứng một mình). Ba nhóm cùng điều này: (a) cụm trang trọng hóa thay cho "là" và "có" ("đóng vai trò là", "được xem là", "sở hữu" khi không nói về quyền sở hữu, "mang đến"; serves as, stands as, boasts, features); (b) cấu trúc dịch từ tiếng Anh, danh hóa dài kiểu "việc tiến hành thực hiện…"; (c) Hán-Việt thừa khi có từ thường cùng nghĩa (thuật ngữ chuyên ngành và từ chuẩn của thể loại thì giữ, theo P2). Sửa bằng "là", "có", động từ thường, hoặc chi tiết cụ thể. Không tìm được từ tự nhiên thì viết lại cả câu. Danh sách trong file references chỉ là ví dụ. Từ bị lạm dụng đổi theo mô hình và thời kỳ; đổi sang từ đồng nghĩa cũng rỗng thì chưa giải quyết gì.

**2. Liệt kê bộ ba máy móc.** Số lượng mục trong liệt kê phải đúng số lượng thực tế. Không mặc định nhóm ba theo phản xạ nhịp điệu.

**3. Negative parallelism.** Không dùng "không chỉ X mà còn Y", "đây không phải A, đây là B", "Y chứ không phải X", "Y thay vì X" khi X chưa ai nêu. Cần đối lập thì nêu thẳng bằng dữ kiện cụ thể. Đối lập thật, có dữ kiện cho cả hai vế, thì giữ.

**4. False range.** Không viết "trải dài từ A đến B" nếu không liệt kê được các điểm cụ thể ở giữa. Chỉ có 2 điểm dữ liệu thì nói rõ là 2.

**5. Editorializing asides.** Không chèn "cần lưu ý rằng", "không thể không nhắc đến", "điều quan trọng là". Mức độ quan trọng tự thể hiện qua cách trình bày và vị trí. Cùng điều này: không chồng nhiều từ rào đón vào một nhận định ("có thể phần nào", "khá là", "dường như có xu hướng"). Chọn một mức chắc chắn đúng với căn cứ và viết một lần; khẳng định hay dè dặt đều phải khớp đầu vào (P4).

**6. Phóng đại ý nghĩa và giọng quảng cáo.** Không gán ý nghĩa phóng đại cho dữ kiện nhỏ, và không viết như tờ rơi hay cẩm nang du lịch. Mô tả bằng đặc điểm kiểm chứng được. Thành tích có số liệu đi kèm ngay sau thì giữ. Khi viết lại một văn bản để "bớt giọng PR", kiểm xem bản mới có đưa thêm giọng PR không.

**7. Phân tích hời hợt gắn đuôi.** Không gắn cụm "cho thấy…", "phản ánh…", "nhấn mạnh…" vào cuối câu dữ kiện. Có phân tích thật thì viết thành câu riêng, có lập luận đầy đủ.

**8. Nguồn và quan hệ mơ hồ.** Không viết "các nghiên cứu cho thấy", "giới quan sát nhận định" mà không nêu nguồn. Không có nguồn xác định thì không đưa tuyên bố đó vào bài. Cùng điều này: nói thẳng quan hệ ("là giám đốc của", "do X thiết kế") thay vì "gắn liền với", "có liên quan đến", "được biết đến với". Quan hệ đầu vào chưa xác nhận thì hỏi, không tự khẳng định.

**9. Câu tóm tắt lặp và kết bài công thức.** Không dùng "Tóm lại,", "Nhìn chung," chỉ để nhắc lại điều vừa nói. Phần tổng kết, nếu cần, phải chứa thông tin tổng hợp mới. Cùng điều này: kết bài theo khuôn "Dù… vẫn đối mặt thách thức… triển vọng…", và kết luận đạo đức hóa kiểu "do đó doanh nghiệp cần…" khi đó không phải khuyến nghị thật. Thách thức hay khuyến nghị có nội dung cụ thể thì giữ.

**10. Cấu trúc công thức cứng nhắc.** Không áp khuôn mục cố định nếu không phản ánh logic nội tại của nội dung. Cấu trúc do nội dung quyết định.

**11. Giới hạn định dạng.** In đậm chỉ cho thuật ngữ hoặc con số cần quét nhanh. Bullet chỉ khi các mục thực sự độc lập, song song; có quan hệ nhân quả hoặc diễn giải thì viết văn xuôi. Tiêu đề viết hoa chữ đầu câu, không Title Case. Em dash (—): tiếng Việt không dùng, thay bằng dấu phẩy, ngoặc đơn, hai chấm hoặc tách câu. Tiếng Anh chỉ dùng khi dấu phẩy, ngoặc đơn, hai chấm không diễn đạt đúng quan hệ ngữ pháp cần thiết, không dùng để tạo nhịp. Ngoại lệ: mẫu giọng của người dùng (mục "Giọng riêng của người viết") dùng em dash thì theo mẫu. Emoji, mũi tên (→) và dấu nháy cong thay cho nháy thẳng trong văn xuôi: bỏ, trừ khi thể loại hoặc mẫu giọng có dùng.

**12. Tàn dư văn phong hội thoại.** Không kết văn bản bằng "Hy vọng điều này hữu ích", "Cho tôi biết nếu cần thêm gì". Không mở đầu kiểu thư từ trong nội dung không phải thư. Không để văn bản tự mô tả chính nó ("bài viết này sẽ trình bày...", "phần tiếp theo bàn về...") thay vì nói thẳng về đối tượng; mục lục hay đoạn dẫn của tài liệu dài có chức năng định hướng thật thì giữ.

**13. Template chưa điền.** Không để hướng dẫn điền-chỗ-trống hay ghi chú nội bộ sót trong bản giao.

**14. Nhãn phân loại thông tin trong văn bản hoàn thiện.** [DỮ KIỆN]/[SUY LUẬN]/[GIẢ ĐỊNH]/[ƯỚC TÍNH]/[KHUYẾN NGHỊ] chỉ dùng trong hội thoại, không xuất hiện trong văn bản giao ra. Xử lý phần chưa xác nhận theo "Bước bắt buộc trước khi viết".

**15. Nhịp câu đơn điệu.** Đây là phép kiểm sau khi viết, không phải chỉ tiêu (P3). Nếu ba câu liền nhau cùng cấu trúc và dài gần bằng nhau, hoặc mọi đoạn đều kết bằng một câu chốt ngắn kiểu khẩu hiệu, thì xem lại. Sửa bằng cách gộp hoặc tách câu theo nghĩa. Câu nghe như trích dẫn đăng mạng xã hội thì viết lại thành câu bình thường mang thông tin cụ thể. Không sửa theo hướng sinh chuỗi câu cụt dồn dập.

**16. Giấu chủ thể hành động.** Khi việc ai làm, ai quyết định, ai chịu trách nhiệm có ý nghĩa với người đọc, nêu rõ chủ thể. Không để vật vô tri làm thay việc của người ("quyết định dần hình thành", "thị trường tự điều chỉnh") khi thực tế có người hoặc tổ chức cụ thể đứng sau. Câu bị động theo chuẩn hành chính, pháp lý ("Hợp đồng được ký kết ngày…") vẫn dùng bình thường.

**17. Cân bằng giả.** Không viết "một mặt… mặt khác…" để dĩ hòa vi quý khi người viết đã có kết luận. Nếu đầu vào có lập trường, viết thẳng theo lập trường đó và nêu đánh đổi cụ thể. Nếu đầu vào chưa có lập trường, đừng tự tạo (P4): giữ trình bày cân bằng, hoặc hỏi người dùng. Văn bản có bản chất là trình bày phương án để người khác quyết thì cân bằng là đúng.

**18. Giải thích điều người đọc đã biết.** Bỏ câu nêu điều hiển nhiên với người đọc mục tiêu (ví dụ nói với người làm bất động sản rằng pháp lý quan trọng với dự án). Thông tin mới nằm ở quan hệ giữa các ý. Người đọc không chuyên thì giữ định nghĩa cần thiết. Khi rà soát văn bản có sẵn mà chưa biết người đọc, chỉ bỏ câu hiển nhiên với mọi người đọc; phần còn lại giữ và ghi vào danh sách vi phạm là "cần xác nhận người đọc".

**19. Từ nối làm vẻ mạch lạc.** Từ nối mang quan hệ logic thật (nguyên nhân, nhượng bộ, đối lập) thì giữ. Phép thử: bỏ từ nối đi, người đọc có phải đọc lại mới hiểu quan hệ giữa hai câu không? Không phải đọc lại thì bỏ. Phải đọc lại thì giữ. Từ nối báo bước ngoặt ("tuy nhiên", "dù vậy") giữ khi hai ý đối lập nhau. Không cấm hẳn từ nối, vì văn nghị luận và văn bản hành chính cần chúng (P2).

**20. Đổi đồng nghĩa cho thuật ngữ.** Thuật ngữ, tên chủ thể, tên dự án giữ một cách gọi xuyên suốt văn bản ("doanh nghiệp" không biến thành "tổ chức", "đơn vị", "chủ thể" cho đỡ lặp). Với từ thường, lặp hay đổi tùy nghĩa, đừng ép lặp đến nặng nề.

## Tự kiểm trước khi giao văn bản

Viết xong, rà lại toàn bộ theo 20 điều như một checklist, vì văn bản dài rất dễ tái phạm dù lúc viết đã cố tránh. Phát hiện vi phạm thì sửa trước khi giao, không hỏi lại người dùng.

Thêm hai phép thử:

**(a) Phép thử cụ thể.** Với mỗi nhận định quan trọng, hỏi: cụ thể là gì, vì sao, biểu hiện ở đâu? Trả lời được từ đầu vào thì đưa câu trả lời vào văn bản. Không trả lời được thì đừng bịa (P1): hạ nhận định xuống mức đầu vào hỗ trợ, rồi nêu cho người dùng, ngoài văn bản, những chỗ còn thiếu chi tiết.

**(b) Phép thử khuôn mới.** Đọc lại bản sửa: có chuỗi câu cụt dồn dập, câu chốt khẩu hiệu, hay một từ nối hoặc kiểu câu mới lặp lại thay cho cái vừa bỏ không? Có thì sửa.

Sau đó chấm văn bản theo 5 tiêu chí, mỗi tiêu chí từ 1 đến 10:

| Tiêu chí | Câu hỏi |
|---|---|
| Thẳng | Câu văn nói thẳng nội dung, hay mất chữ để rào đón, giới thiệu? |
| Nhịp | Nhịp câu đổi theo ý cần nói, hay đều đều như máy? (Chấm theo cảm nhận khi đọc, không đo bằng số chữ.) |
| Tin người đọc | Có giải thích thừa, nhắc lại điều người đọc đã hiểu? |
| Tự nhiên | Đọc lên có giống người thật viết? |
| Cô đọng | Còn chữ nào cắt được mà không mất nghĩa? |

Dưới 35/50 thì sửa tiếp trước khi giao. Điểm chỉ dùng nội bộ, không ghi vào văn bản giao ra. Chỉ báo điểm cho người dùng khi đang rà soát văn bản có sẵn hoặc khi người dùng hỏi.

## Giới hạn của skill này

Đây là quy tắc về *hình thức diễn đạt*, không đảm bảo *nội dung* đủ sâu hay đủ căn cứ. Chất lượng lập luận, dữ kiện, độ chính xác vẫn phụ thuộc thông tin đầu vào và kỷ luật xác minh thông thường.

Skill không nhằm vượt qua công cụ phát hiện AI và không đảm bảo kết quả với chúng. Không có bộ dấu hiệu nào đủ tin cậy để kết luận một văn bản là do AI viết. Nếu người dùng nhờ sửa để qua một công cụ phát hiện: vẫn áp 20 điều như bình thường vì chúng làm văn bản tốt hơn, không dùng mẹo chỉ để đánh lừa công cụ (cố ý thêm lỗi chính tả, đảo từ ngẫu nhiên, bịa chi tiết), và nói rõ không thể đảm bảo kết quả.

Phần tiếng Việt trong skill dựa trên quan sát và các nguồn tiếng Anh. Chưa có nghiên cứu tiếng Việt nào được kiểm chứng làm căn cứ cho danh sách mẫu cụ thể.
