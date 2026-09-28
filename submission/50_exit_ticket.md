# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Cần policy riêng cho cross-camera: hai box có thể là hai quan sát hợp lệ của cùng vật, không tự động xem là duplicate hay gộp. Policy cần nêu khi giữ cả hai, hợp nhất hoặc để tầng sau xử lý, dựa trên timestamp, calibration và output đích.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera. Giữ cùng track ID khi có bằng chứng liên tục đó là cùng object; thêm keyframe khi hình học/vị trí thay đổi đáng kể theo guideline, và dùng Outside khi object rời khỏi field of view. Nối qua camera cần timestamp đồng bộ, calibration/geometry và policy identity cross-camera; thiếu các bằng chứng đó thì không tự ghép.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Ở `adasind_117120.jpg`, L6 Truck cùng vùng với M10 nhưng không có box reference; mình ghi là chưa phân xử và yêu cầu QA kiểm ảnh thay vì kết luận reference thiếu. Nếu làm lại, mình sẽ kiểm các box chồng lấn trên ảnh gốc trước khi khóa và kiểm group của cặp box/polygon K12 sớm hơn. (Sửa câu này nếu không phản ánh đúng trải nghiệm của bạn.)
