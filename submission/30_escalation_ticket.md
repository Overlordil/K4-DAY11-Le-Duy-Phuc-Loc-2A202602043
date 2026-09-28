# Escalation ticket

## Ticket 1

- **Frame:** `adasind_062370.jpg` (`R7` ThreeWheeler và `R8` Truck chỉ có ở teaching reference; R7 chồng phần lớn lên box ThreeWheeler khác).
- **Ảnh chụp:** `submission/screenshots/Screenshot_1.png` (xác nhận ảnh này đúng frame trước khi nộp).
- **Expected impact:** Nếu box reference trùng hoặc sai class được tính như object độc lập, số missing theo zone và kết luận từ teaching reference của frame này sẽ sai.
- **Owner:** `qa`
- **Recommendation:** Soi ảnh gốc độc lập để xác nhận R7 là object riêng hay box trùng, xác nhận R8 có object đủ ngưỡng trong vùng hợp lệ, rồi cập nhật/ghi lý do cho reference trước khi dùng các ca này làm chuẩn so sánh.

## Ticket 2

- **Frame:** `adasind_086220.jpg` (`L3` Bike chồng vùng `L2/R1` ThreeWheeler; `M7` Car chỉ có ở model).
- **Ảnh chụp:** `submission/screenshots/Screenshot_2.png` (xác nhận ảnh này đúng frame trước khi nộp).
- **Expected impact:** Nếu chưa phân biệt được box Bike là object riêng hay box chồng, quyết định sửa nhãn và cách diễn giải false positive của model có thể sai.
- **Owner:** `qa`
- **Recommendation:** Đối chiếu ảnh gốc ở độ phóng đại đủ đọc; xác nhận object, phần nhìn thấy và chiều cao theo R01/R02 trước khi phân loại finding L3 hoặc M7.

## Ticket 3

- **Frame:** `adasind_117120.jpg` (`L6` Truck và `M10` Truck khớp vùng nhưng teaching reference không có box tương ứng).
- **Ảnh chụp:** `submission/screenshots/Screenshot_3.png` (xác nhận ảnh này đúng frame trước khi nộp).
- **Expected impact:** Nếu object thật bị bỏ khỏi reference, số spurious của annotator/model và ma trận so sánh class Truck sẽ bị lệch; nếu đó là box nhầm thì không nên sửa reference.
- **Owner:** `qa`
- **Recommendation:** Nhờ reviewer thứ hai kiểm ảnh gốc và vùng ignore, xác nhận object/class theo taxonomy; chỉ sửa reference sau khi có quyết định kèm ảnh và lý do.
