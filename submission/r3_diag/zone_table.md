# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 10 | 2 | 1 | 2 | 3 | WRONG_CLASS (1) |
| mid | 6 | 3 | 2 | 2 | 3 | MISSING (2) |
| edge | 2 | 1 | 1 | 2 | 3 | WRONG_CLASS (1) |

## Nhận xét

- Người gán nhãn (L) gãy nhiều nhất ở zone `mid`: 3 ca missing + 2 ca spurious = 5 ca. Model (M) có tổng 5 ca ở mỗi zone (`center`: 2 missing + 3 thừa; `mid`: 2 missing + 3 thừa; `edge`: 2 missing + 3 thừa), nên bảng này không cho thấy một zone riêng biệt mà model gãy nhiều hơn.
- Giả thuyết: các ca của L ở `mid` có thể đến từ việc bỏ sót vật thể hoặc đặt box chưa ổn định trong vùng bị che/méo, còn các ca model thừa có thể do box dự đoán nhạy với nền và biên fisheye. Đây chỉ là giả thuyết cần đối chiếu từng ảnh và object_ref; slice chỉ có ba frame nên không đủ đại diện cho toàn bộ camera, điều kiện sáng, mức che khuất hoặc các zone khác.
