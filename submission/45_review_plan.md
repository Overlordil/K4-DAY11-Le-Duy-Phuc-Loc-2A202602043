# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| B2-center · `adasind_062370.jpg` | 2 reference-only (`R7`, `R8`); 5 model-only | Có box reference chưa được L ghép và nhiều box model-only; riêng R7 chồng phần lớn với box ThreeWheeler khác nên cần adjudication trước khi gọi là missing. | Ảnh gốc, compare/model overlay, `local_quality_conflicts.csv`, screenshot đúng frame và quyết định QA. |
| B2-center · `adasind_117120.jpg` | 3 L-only (`L1`, `L3`, `L6`); `L6+M10` không có R; 4 model-only | Các box L1/L3 cần kiểm tra hình học/chồng lấn; L6 và M10 cùng vùng nhưng reference không có box nên chưa rõ lỗi thuộc nhãn hay reference. | Ảnh gốc, overlay L/R/M, `findings.csv`, screenshot đúng frame và quyết định QA. |

Giới hạn của kết luận từ ba frame ADASIND: đây chỉ là một slice nhỏ của một camera; frame không độc lập về nội dung, teaching reference chưa phải gold set, và các box máy/annotator-only phải được xác minh trên ảnh. Kết quả không ước lượng được tỷ lệ lỗi của toàn ADASIND hay bốn camera SVM.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv`: kiểm đủ 8 ô camera × normal/hard, tổng đúng 200; rà timestamp/scene để tránh tính nhiều frame liền nhau của cùng một tình huống như các mẫu độc lập. Hard được oversample để tìm failure mode; muốn ước lượng tỷ lệ lỗi population cần lưu xác suất lấy mẫu và dùng trọng số phù hợp. Kế hoạch hiện tại giúp tìm ca cần review, không tự đo tỷ lệ lỗi.
