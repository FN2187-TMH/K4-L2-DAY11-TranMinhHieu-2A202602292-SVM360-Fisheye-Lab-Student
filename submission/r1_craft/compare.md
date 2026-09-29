# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_152940.jpg
- L2+R5 mid WRONG_CLASS
- R6 mid MISSING
## adasind_167700.jpg
- L4 mid IGNORE_SCOPE
- L5 mid IGNORE_SCOPE
- L7 mid SPURIOUS
- L8+R4 center WRONG_CLASS
- R2 mid MISSING
- R8 center MISSING
## adasind_212280.jpg
- L3 mid IGNORE_SCOPE
- L4+R3 edge WRONG_CLASS

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 10 | 8 | 2 | 1 |
| mid | 6 | 3 | 3 | 2 |
| edge | 2 | 1 | 1 | 1 |
