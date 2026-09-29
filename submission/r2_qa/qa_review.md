# QA review · B2-center

Mã khóa: 8A01-4B64

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_062370.jpg | L1 | R05 | Box L1 ThreeWheeler bị mép trái khung hình cắt ngang, cần xác nhận đã chọn attribute truncated |
| adasind_062370.jpg | L5 | R04 | Xe van chở người được phân loại là Car đúng theo quy ước R04, nhưng viền box phía trước chưa ôm sát đầu xe (R02) |
| adasind_062370.jpg | — | R07 | Xuất hiện phần tay lái/người lái xe camera ở góc dưới bên trái nhưng chưa vẽ polygon ignore_region (ego_body) |
| adasind_086220.jpg | L2 | R02 | Box L2 ThreeWheeler chưa ôm sát viền mui/trần xe phía trên (dư/thiếu khoảng trống) |
| adasind_086220.jpg | L1 | R03 | Người điều khiển gộp chung với xe thành 1 box Bike duy nhất là chuẩn theo luật rider R03 |
| adasind_086220.jpg | — | R07 | Thiếu polygon ignore_region với lý do ego_body cho phần tay lái xe camera ở góc dưới bên trái |
| adasind_117120.jpg | L5 | R05 | L5 ThreeWheeler bị người đi bộ L6 đứng che một phần phía trước, cần đảm bảo đã tích chọn attribute occluded |
| adasind_117120.jpg | — | R01 | Xe ô tô/xe tải màu trắng ở xa dải đường chính có chiều cao >= 40px nhưng bị sót không gán box |
| adasind_117120.jpg | — | R07 | Thiếu polygon ignore_region (reason ego_body) cho phần đồng hồ/tay lái xe ego xuất hiện rõ ở góc dưới bên trái |
