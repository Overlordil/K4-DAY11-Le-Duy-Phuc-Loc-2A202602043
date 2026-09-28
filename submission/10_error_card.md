# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B2 | MISSING | 10 |
| center | B2 | SPURIOUS | 15 |
| center | B2 | STRUCTURE | 1 |
| center | C0 | MISSING | 1 |
| center | C0 | SPURIOUS | 2 |
| edge | B2 | SPURIOUS | 1 |
| mid | B2 | MISSING | 3 |
| mid | B2 | SPURIOUS | 7 |
| mid | C0 | MISSING | 1 |

## Top defects
- SPURIOUS: 25 (ví dụ frame adasind_019560.jpg)
- MISSING: 15 (ví dụ frame adasind_019560.jpg)
- STRUCTURE: 1 (ví dụ frame adasind_062370.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: `SPURIOUS` là nhóm lớn nhất (25), nhưng gộp nhiều round nên không có một nguyên nhân duy nhất. Trong B2, L1 Pedestrian và L3 Car ở `adasind_117120.jpg` bị compare đánh dấu thừa và có vùng chồng với box khác; đây là dấu hiệu cần kiểm tra hình học trên ảnh, không tự chứng minh chúng là duplicate. Các M-only gồm nhiều box rider/class mà model tách hoặc gán class khác, phù hợp với giới hạn model trên miền fisheye nhưng chỉ là quan sát của slice này.
- Cách sửa và ai nhận việc (`owner`): Annotator kiểm L1/L3 trên ảnh gốc theo R02 rồi chỉ rework nếu xác nhận box trùng/sai; QA adjudicate L6/M10 vì reference không có box; model errors ghi `keep_with_reason`, không sửa nhãn người chỉ để khớp model.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `adasind_117120.jpg` L1/L3/L6 trong `findings.csv`, `submission/r1_craft/compare.html`, `submission/r3_diag/model_compare.html`, `Screenshot_3.png` (xác nhận đúng frame), R02–R04; đối chiếu ảnh gốc trước quyết định cuối.
