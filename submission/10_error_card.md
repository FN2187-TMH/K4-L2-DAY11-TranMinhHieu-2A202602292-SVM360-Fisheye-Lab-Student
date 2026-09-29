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

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: TODO
- Cách sửa và ai nhận việc (`owner`): TODO
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): TODO
