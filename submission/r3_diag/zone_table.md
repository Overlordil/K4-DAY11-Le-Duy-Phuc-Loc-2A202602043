# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 13 | 3 | 3 | 7 | 10 | MISSING (3) |
| mid | 6 | 0 | 1 | 3 | 5 | SPURIOUS (1) |
| edge | 1 | 0 | 0 | 0 | 1 | — |

## Nhận xét

- `center` có nhiều sai khác nhất ở cả L và M: L có 3 missing và 3 spurious; M có 7 missing và 10 thừa. Ở `mid`, L có 0 missing/1 spurious, M có 3 missing/5 thừa. `edge` chỉ có 1 đối tượng tham chiếu: L không có sai khác, M có 1 box thừa.
- Một giả thuyết cần kiểm thêm là các frame `center` có nhiều đối tượng hoặc che khuất hơn, khiến phát hiện và ghép box khó hơn; số liệu này chưa chứng minh méo fisheye là nguyên nhân. Slice chỉ có ba frame, teaching reference chưa phải gold set, và zone là bin theo vị trí ảnh chứ không cho biết khoảng cách tới xe, nên không thể khái quát thành hiệu năng tổng thể.
