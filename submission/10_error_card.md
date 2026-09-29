# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B3 | MISSING | 5 |
| center | B3 | SPURIOUS | 4 |
| center | B3 | WRONG_CLASS | 1 |
| center | C0 | SPURIOUS | 1 |
| edge | B3 | MISSING | 2 |
| edge | B3 | SPURIOUS | 3 |
| edge | B3 | WRONG_CLASS | 1 |
| mid | B2 | ATTRIBUTE | 1 |
| mid | B2 | BOX_GEOMETRY | 1 |
| mid | B3 | IGNORE_SCOPE | 3 |
| mid | B3 | MISSING | 6 |
| mid | B3 | SPURIOUS | 6 |
| mid | B3 | WRONG_CLASS | 1 |
| unknown | B2 | IGNORE_SCOPE | 1 |

## Top defects
- SPURIOUS: 14 (ví dụ frame adasind_019560.jpg)
- MISSING: 13 (ví dụ frame adasind_152940.jpg)
- IGNORE_SCOPE: 4 (ví dụ frame adasind_167700.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: `SPURIOUS` cao nhất (14) cho thấy có xu hướng vẽ box ngoài object hoặc giữ box trong vùng ignore; ví dụ `adasind_167700.jpg` có `L7` là `L_only`, còn `M_only` xuất hiện ở các ca model không có đối tượng tương ứng. `MISSING` cũng cao (13), với `R5+M9` và `R6` ở `adasind_152940.jpg` cho thấy cần soát lại vật nhỏ và vật bị che thay vì chỉ dựa vào prefill.
- Cách sửa và ai nhận việc (`owner`): Annotator rework các dòng `action=rework` và kiểm tra lại H=40, class, geometry và ignore_region trên ảnh gốc. Các dòng `M_only` giữ `action=escalate` cho `ai_team`; các xung đột label/reference chuyển `qa` xác minh.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `submission/findings.csv` các dòng `r3_diag` của `adasind_152940.jpg`, `adasind_167700.jpg` và `adasind_212280.jpg`; `submission/r3_diag/local_quality_conflicts.csv`; `submission/r3_diag/model_compare.html`; đối chiếu R02, R04 và R07 trong `docs/02-rules-vi.md`.
