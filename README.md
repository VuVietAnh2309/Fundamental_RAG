# 🧠 RAG Knowledge — 100 Questions & Fundamentals

> Bộ ghi chú và 100 câu hỏi tự học về Retrieval-Augmented Generation (RAG).  
> Mục tiêu: Hiểu sâu cách RAG hoạt động, các thành phần, và cách tối ưu hóa thực tế.

---

## 📖 Giới thiệu

**RAG (Retrieval-Augmented Generation)** là kiến trúc giúp mô hình ngôn ngữ (LLM)  
kết hợp **kiến thức bên ngoài** thông qua cơ chế *retrieval* trước khi sinh câu trả lời.  
Điều này giúp mô hình:
- Giảm hallucination,
- Cập nhật thông tin mà không cần fine-tuning,
- Giải thích được nguồn tri thức.

---

## 📂 Cấu trúc tài liệu

| File | Nội dung |
|------|-----------|
| **rag_question_answering.md** | Danh sách 100 câu hỏi — từ cơ bản đến nâng cao |
| **fundamentals/RAG_Pipeline.md** | Giải thích chi tiết pipeline retrieval–generation |
| **fundamentals/Embeddings.md** | Kiến thức về vector embedding và lưu trữ |
| **fundamentals/Retrieval_Strategies.md** | So sánh dense, sparse và hybrid retrieval |
| **fundamentals/Generation.md** | Cách tạo prompt và kiểm soát groundedness |
| **fundamentals/Evaluation.md** | Các thước đo đánh giá chất lượng RAG |
| **fundamentals/Advanced_Topics.md** | Tài liệu về Self-RAG, GraphRAG, Multi-hop |
| **fundamentals/References.md** | Tổng hợp papers, blog, và benchmark hữu ích |

---

## 🧩 Cách sử dụng

- Đọc **rag_question_answering.md** để ôn tập nhanh toàn bộ 100 câu hỏi.  
- Khi gặp khái niệm khó, mở file tương ứng trong thư mục `fundamentals/` để xem chi tiết.  
- Có thể dùng [Obsidian](https://obsidian.md) hoặc [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) để đọc dễ hơn.

---

## 🌱 Hướng phát triển

- Thêm ví dụ code (FAISS, LlamaIndex, LangChain)
- Thêm file `Applied_RAG.md`: các use case (QA, doc assistant, search system)
- Thêm `Evaluation_Case_Study.md`: ví dụ đo độ groundedness thực tế
