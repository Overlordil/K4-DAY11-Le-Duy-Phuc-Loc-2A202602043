# Guideline patch

- **Rule mới đề xuất:** Khi làm K12, polygon viền và box của cùng một object phải được chọn cùng nhau và gán cùng `group_id`; chỉ tính fill ratio khi cặp cùng class, cùng group và thuộc cùng frame. Không dùng polygon K12 như một nhãn object bổ sung.
- **Áp dụng cho:** Các cặp box/polygon minh họa K12; không đổi taxonomy sáu class, thuộc tính hoặc quy tắc `ignore_region`.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R01–R11 chưa quy định quan hệ cấu trúc giữa box và polygon K12. Ở `adasind_062370.jpg`, QA ghi nhận box `L5` và polygon `ThreeWheeler` cùng vùng nhưng export không thể hiện group liên kết; điều này có thể khiến phép tính không biết hai shape là một object.
- **`rules_version` mới:** v1.1.0 (đề xuất; chỉ cập nhật phiên bản chính thức sau khi guideline owner duyệt).
- **Hiệu lực từ:** Round P2/K12 tiếp theo sau khi patch được duyệt; không áp dụng hồi tố để tự sửa export đã khóa.
