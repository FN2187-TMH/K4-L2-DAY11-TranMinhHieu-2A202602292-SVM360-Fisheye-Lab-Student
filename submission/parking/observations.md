# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Nằm ngang kéo dài xuyên suốt bãi đỗ xe ở dải giữa ảnh (màu xanh lá cây/màu vàng), đánh dấu đường ranh giới kéo dài của các dãy ô đỗ xe nằm ngang.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Các vạch dọc màu vàng chia từng ô đỗ xe đơn lẻ (ngang và chéo) ở giữa bãi đỗ và các vạch trắng ở góc dưới không được vẽ riêng lẻ từng vạch, vì yêu cầu dán nhãn chỉ tập trung vẽ đường ranh giới tổng thể/đường trục chính (`parking_line`) cho cả dải ô đỗ.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Polygon `free_space` (khung viền xanh lá) bao trọn toàn bộ khoảng không gian trống/đường di chuyển phía trước và dải ô đỗ chính; dừng lại ở mép dưới ảnh và ranh giới phía xa gần mép cây xanh; không bị che bởi vật thể lớn nào ngoại trừ chiếc xe ô tô màu đỏ ở phía xa bên trái.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): không có