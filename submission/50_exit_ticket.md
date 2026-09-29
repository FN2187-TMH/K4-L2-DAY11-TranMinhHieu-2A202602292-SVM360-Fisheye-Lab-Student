# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Cần policy seam riêng, không tự gọi là `DUPLICATE`: cùng một vật có thể xuất hiện hợp lệ ở hai camera. Chỉ nối thành một identity khi có timestamp đồng bộ, calibration và policy cross-camera; ở ảnh 2D giữ hai box độc lập.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera. Giữ cùng track ID khi object liên tục trên cùng camera và visible; thêm keyframe khi hình dáng/vị trí thay đổi đáng kể; dùng Outside khi object ra khỏi vùng nhìn thấy theo rule. Trước khi nối qua camera cần timestamp, intrinsic/extrinsic calibration, vùng seam và policy output/BEV đã được xác nhận.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Ở `adasind_152940.jpg`, `L2` bị learner gán `Car` trong khi reference là `Truck`, còn `R6` bị bỏ sót; mình ghi finding theo ảnh và tách phần rework khỏi các ca model/reference cần escalate. Nếu làm lại, mình sẽ kiểm tra H=40, class và ignore_region theo từng frame trước khi khóa, sau đó mới đối chiếu model/reference.
