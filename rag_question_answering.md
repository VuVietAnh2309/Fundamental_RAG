Question & Answering about RAG

Q1: Explain the requirement of RAG when LLMs are already powerful.
Trả lời: LLMs mạnh mẽ nhưng bị giới hạn bởi knowledge cutoff (kiến thức tĩnh), nên không thể trả lời các truy vấn liên quan đến sự kiện mới nhất hoặc dữ liệu không có trong tập huấn luyện. RAG giải quyết vấn đề này bằng cách truy xuất ngữ cảnh liên quan từ các nguồn kiến thức bên ngoài, giúp LLMs cung cấp các phản hồi chính xác.

Q2: Is RAG still relevant in the era of long context LLMS?
(Liệu RAG còn phù hợp trong thời đại LLMs ngữ cảnh dài?)
Trả lời: RAG vẫn quan trọng ngay cả với LLMs có ngữ cảnh dài vì LLMs ngữ cảnh dài không có RAG gặp 3 vấn đề: "lost in the middle" (khó tìm thông tin liên quan trong ngữ cảnh lớn), chi phí API cao, và độ trễ tăng. RAG giải quyết các vấn đề này bằng cách cung cấp thông tin liên quan nhất từ các nguồn kiến thức bên ngoài, giúp phản hồi chính xác và tiết kiệm chi phí.

Q3: What are the fundamental challenges of RAG systems?
Trả lời:
Các thách thức cơ bản của hệ thống RAG bao gồm: 
- **Khả năng mở rộng (Scalability)** khi tìm kiếm và truy xuất nhanh chóng từ các nguồn kiến thức lớn, 
- **Độ trễ (Latency)** do quá trình hai bước (truy xuất sau đó sinh ra), 
- **Nguy cơ Ảo giác (Hallucination Risk)** ngay cả với dữ liệu được truy xuất, và **Thiên vị và Nhiễu (Bias and Noise)** từ nội dung được truy xuất.

Q4: Explain R, A, and G in RAG.
Trả lời: RAG là viết tắt của Retrieval-Augmented Generation. "R" (Retrieval) là quá trình tìm kiếm và lấy thông tin liên quan nhất từ các nguồn kiến thức bên ngoài cho truy vấn của người dùng. "A" (Augmented) là việc đưa ngữ cảnh liên quan được truy xuất vào prompt của LLM cùng với truy vấn và hướng dẫn. "G" (Generation) là giai đoạn LLM sinh ra xử lý prompt để tạo ra phản hồi mạch lạc, chính xác và có ngữ cảnh liên quan.

Q5: How does RAG help reduce hallucinations in LLM generated responses?
Trả lời: RAG giúp giảm ảo giác bằng cách thêm một hệ thống truy xuất bên ngoài, kéo thông tin thực tế, cập nhật từ các nguồn kiến thức đáng tin cậy. Việc kết hợp truy xuất với sinh ra đảm bảo câu trả lời chính xác hơn, ít bịa đặt hoặc thông tin sai lệch hơn, tăng độ tin cậy của đầu ra.

Q6: Can you give examples of real-world applications where RAG systems have demonstrated value?
Trả lời: Các công cụ tìm kiếm AI là một ví dụ tuyệt vời. Chúng cung cấp câu trả lời chính xác, liên quan bằng cách kết hợp truy xuất thông tin với AI sinh ra. Ví dụ, các nền tảng tìm kiếm AI dựa trên RAG như Perplexity AI cải thiện trải nghiệm người dùng bằng cách lấy thông tin gần đây và liên quan nhất từ các cơ sở kiến thức lớn và trả lại theo định dạng mà người dùng muốn.

Q7: What is the purpose of character overlap during chunking in a RAG pipeline?
Trả lời: Trong pipeline RAG, chunk overlap (độ chồng chéo giữa các đoạn) trong quá trình phân đoạn đảm bảo tính liên tục về ngữ cảnh và ngăn ngừa mất mát thông tin tại ranh giới các đoạn. Điều này cải thiện độ chính xác của truy xuất và duy trì tính mạch lạc trong văn bản đưa vào LLM. Thông thường, độ chồng chéo khoảng 10-20% kích thước đoạn được sử dụng.

Q8: Explain the steps in the indexing process in a RAG pipeline.
Trả lời: 
Quá trình lập chỉ mục trong pipeline RAG gồm 4 bước: 
- **Parsing** (trích xuất nội dung tài liệu), 
- **Chunking** (chia nội dung thành các đoạn nhỏ hơn), 
- **Encoding** (sử dụng mô hình embedding để chuyển đoạn thành vector số)
- **Storing** (lưu trữ các embedding này vào cơ sở dữ liệu vector để tìm kiếm và truy xuất hiệu quả). 
=> Tất cả các bước này được thực hiện offline.

Q9: Explain the importance of chunking in RAG.
Trả lời: Chunking (Phân đoạn) rất quan trọng vì nó chia văn bản lớn thành các đoạn nhỏ hơn, có ý nghĩa ngữ nghĩa (semantically coherent). Phân đoạn đúng cách giúp tìm kiếm thông tin liên quan hiệu quả bằng cách tạo ra các đoạn tập trung, duy trì ngữ cảnh và tránh nhiễu không liên quan. Chọn kích thước đoạn phù hợp cân bằng giữa chi tiết và ngữ cảnh, tối ưu hóa độ chính xác truy xuất và hiệu quả tính toán.

Q10: How do you choose the chunk size for a RAG system?
Trả lời:
Chọn kích thước đoạn cho hệ thống RAG liên quan đến việc cân bằng giữa **độ chi tiết (granularity)**, **tính đầy đủ của ngữ cảnh (context completeness)**, và **hiệu quả tính toán (computational efficiency)**. Các đoạn nhỏ (ví dụ: 100-200 token) cho phép truy xuất chính xác nhưng có thể thiếu ngữ cảnh. Các đoạn lớn (ví dụ: 500-1000 token) cung cấp nhiều ngữ cảnh hơn nhưng tốn nhiều tính toán hơn và có khả năng gây nhiễu. Kích thước tối ưu phụ thuộc vào trường hợp sử dụng, cấu trúc tài liệu, mô hình embedding và mô hình sinh ra (LLM).	