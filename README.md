# Sổ tay RAG — 35 kỹ thuật Retrieval-Augmented Generation (Tiếng Việt)

Tài liệu học tập tương tác bằng tiếng Việt về **35 kỹ thuật RAG**, diễn giải lại từ repo [NirDiamant/RAG_Techniques](https://github.com/NirDiamant/RAG_Techniques).

Mỗi kỹ thuật đi theo một mạch nhất quán: **Vấn đề nó giải quyết → Ý tưởng lõi → Sơ đồ trực quan → Demo mô phỏng → Pseudocode → Nên/Không nên dùng → Quiz kiểm tra**.

> 🔗 **[Xem trang web tại đây](https://mduongvandinh.github.io/rag-techniques-vi/)**

---

## Điểm khác biệt

Đây không phải bản dịch notebook. Tài liệu được viết lại để **dạy cách chẩn đoán**, không chỉ mô tả kỹ thuật:

- **Demo tương tác thật** — kéo slider để thấy ranh giới chunk thay đổi, kéo `α` để xem bảng xếp hạng BM25↔vector đổi chỗ, bấm nút để cross-encoder kéo tài liệu đúng từ vị trí #4 lên #1.
- **Ma trận "triệu chứng → kỹ thuật"** — cách kỹ sư thật sự chọn kỹ thuật, thay vì học tuần tự theo danh sách.
- **Trade-off ở mọi bài** — mỗi kỹ thuật đều có bảng so sánh độ phức tạp / chi phí / mức cải thiện, và phần "không nên dùng khi".
- **Ví dụ tiếng Việt** — các demo dùng tình huống quen thuộc với dev (tài liệu API, mã lỗi, cấu hình hệ thống) thay vì ví dụ dịch máy.

## Cấu trúc nội dung

| File | Nhóm | Kỹ thuật |
|------|------|----------|
| `index.html` | **Trang tổng quan** | Bản đồ pipeline, danh mục 35 kỹ thuật, ma trận tra cứu, lộ trình 3 cấp |
| `03-foundational.html` | 🌱 Nền tảng | Simple RAG · Chunk Size · Reliable RAG · Proposition Chunking · RAG với CSV/JSON |
| `01-query-enhancement.html` | 🔍 Nâng cấp truy vấn | Query Transformations (Rewrite/Step-back/Decompose) · HyDE · HyPE |
| `04-context-enrichment.html` | 📚 Làm giàu ngữ cảnh | Chunk Headers · Context Window · RSE · Contextual Compression · Document Augmentation |
| `02-retrieval.html` | 🚀 Truy xuất (lõi) | Semantic Chunking · Fusion Retrieval · Reranking |
| `05-advanced-retrieval.html` | 🚀 Truy xuất nâng cao | Hierarchical Indices · Dartboard · Multi-faceted Filtering · Multi-modal RAG |
| `06-iterative-adaptive.html` | 🔁 Vòng lặp & thích ứng | Retrieval with Feedback Loop · Adaptive Retrieval |
| `07-advanced-architectures.html` | 🏗️ Kiến trúc nâng cao | RAPTOR · Graph RAG · MS GraphRAG · Self-RAG · CRAG · Agentic RAG · MemoRAG · Controllable Agent |
| `08-evaluation.html` | 📊 Đánh giá & minh bạch | End-to-End Eval · DeepEval · GroUSE · Open-RAG-Eval · Explainable Retrieval |

## Lộ trình học gợi ý

**Cấp 1 — Nền tảng** (cần: hiểu embedding & vector search)
Simple RAG → Chunk Size → Reliable RAG → Query Transformations → Chunk Headers

**Cấp 2 — Trung cấp** (cần: đã chạy pipeline thật, biết đo recall)
HyDE → Semantic Chunking → Fusion Retrieval → Reranking → Contextual Compression → Đánh giá cơ bản

**Cấp 3 — Nâng cao** (cần: có bộ eval để đo lợi ích/chi phí)
RAPTOR → Graph RAG → Self-RAG → CRAG → Agentic RAG → GroUSE

> 💡 **Gợi ý quan trọng:** nếu bạn đang xây RAG thật, hãy đọc `08-evaluation.html` **trước**, không phải cuối. Không có bộ eval thì mọi kỹ thuật ở các bài khác chỉ là phỏng đoán — bạn không biết mình đang tiến hay lùi.

## Đặc điểm kỹ thuật

- **Self-contained hoàn toàn** — mỗi file là HTML đơn lẻ: vanilla JS + inline CSS + SVG.
- **Không CDN, không framework, không build step** — clone về mở bằng trình duyệt là chạy.
- **Chạy offline 100%** — không gọi API, không tracking, không phụ thuộc mạng.
- **Responsive** — đọc được trên điện thoại.
- Tôn trọng `prefers-reduced-motion`, có `role="img"` + `aria-label` cho sơ đồ SVG.

## Chạy local

```bash
https://github.com/mduongvandinh/rag-techniques-vi.git
cd rag-techniques-vi
```

Mở trực tiếp `index.html` bằng trình duyệt, hoặc chạy server tĩnh:

```bash
python3 -m http.server 8000
# rồi mở http://localhost:8000
```

## Nguồn & giấy phép

Nội dung được **diễn giải lại** (không sao chép code) từ [NirDiamant/RAG_Techniques](https://github.com/NirDiamant/RAG_Techniques) — kho kỹ thuật RAG với hơn 27k ⭐.

Repo gốc dùng **giấy phép phi thương mại (custom non-commercial license)**. Tài liệu này phục vụ mục đích **học tập, phi thương mại**. Trước khi tái sử dụng cho mục đích khác, vui lòng đọc điều khoản tại repo gốc.

Tài liệu này **không thay thế** notebook gốc — nó giúp bạn hiểu *tại sao* và *khi nào* dùng mỗi kỹ thuật. Muốn cài đặt thật, hãy đọc code ở repo gốc.

## Đóng góp

Phát hiện lỗi nội dung, thuật ngữ dịch chưa chuẩn, hay demo hiểu sai bản chất kỹ thuật? Rất hoan nghênh issue hoặc PR.
