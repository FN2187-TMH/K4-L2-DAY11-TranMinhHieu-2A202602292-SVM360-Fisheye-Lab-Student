# Escalation ticket

## Ticket 1

- **Frame:** `adasind_212280.jpg`, object `L4+M6` (`LM_noR`) và `R3` (`R_only`); tham chiếu thêm các `M_only` trong `adasind_152940.jpg`.
- **Ảnh chụp:** `submission/r3_diag/model_compare.html` và bảng conflict `submission/r3_diag/local_quality_conflicts.csv`.
- **Expected impact:** Có thể tạo false positive của model và làm sai class/độ phủ object ở vùng edge; nếu dùng reference chưa xác minh để rework thì có nguy cơ đưa nhãn sai vào bản khóa.
- **Owner:** `qa` phối hợp `ai_team`.
- **Recommendation:** Review độc lập trên ảnh gốc theo R02/R04/R07; xác nhận Bus hay Car và xem box `LM_noR` có phải reference defect không. Chỉ cập nhật annotation sau khi có quyết định; giữ `action=escalate` cho các M_only chưa đủ bằng chứng.
