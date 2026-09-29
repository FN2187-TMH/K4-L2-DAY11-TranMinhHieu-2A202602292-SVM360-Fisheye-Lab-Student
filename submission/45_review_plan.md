# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `B3-center / adasind_167700.jpg` | 7 ca: 2 MISSING, 2 SPURIOUS, 1 WRONG_CLASS và 2 IGNORE_SCOPE liên quan | Nhiều ca mid/center, có cả object thừa, object thiếu và sai class; ưu tiên kiểm lại trước khi rework | `findings.csv`, `local_quality_conflicts.csv`, `model_compare.html`, ảnh gốc và rule R02/R04/R07 |
| `B3-center / adasind_152940.jpg` | 3 MISSING, 1 WRONG_CLASS và nhiều M_only trong model comparison | Có vật nhỏ gần nhau và object ở mép phải; dễ nhầm missing với box/model disagreement | `findings.csv`, `local_quality_conflicts.csv`, `model_compare.html`, ảnh gốc và overlay |

Giới hạn của kết luận từ ba frame ADASIND: Đây chỉ là một slice của một camera và không đại diện cho các điều kiện sáng, tốc độ, mật độ vật thể hoặc bốn camera SVM; số lỗi không thể dùng để ước lượng tỷ lệ lỗi toàn hệ thống.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Đếm đủ 8 ô camera × normal/hard, kiểm tra tổng 200 frame và phân bố theo timestamp/cảnh; tránh lấy liên tiếp quá nhiều frame từ cùng một đoạn, đồng thời giữ các ca seam, ánh sáng xấu, che khuất và méo biên. Kế hoạch này chỉ tạo độ phủ để chọn ca review, chưa có gold label độc lập nên không đo được tỷ lệ lỗi.
