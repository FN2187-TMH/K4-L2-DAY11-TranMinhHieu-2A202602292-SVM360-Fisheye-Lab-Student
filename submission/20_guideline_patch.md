# Guideline patch

- **Rule mới đề xuất:** Trước khi tạo hoặc giữ một box nằm sát vùng fisheye/ignore, phải kiểm tra object có phần nhìn thấy độc lập hay chỉ là thân xe, viền kính hoặc nền bị model/pre-fill kéo thành box. Nếu object thật bị cắt bởi mép ảnh thì giữ box theo visible extent và đặt `truncated=true`; nếu box nằm trong `ignore_region` mà không có object độc lập thì xóa và ghi `IGNORE_SCOPE`.
- **Áp dụng cho:** Box object ở edge/mid gần `lens_border`, `ego_body` và các ca `M_only`, `L_only`, `IGNORE_SCOPE`.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật hiện tại nêu cách dùng ignore và truncated nhưng chưa yêu cầu một bước quyết định rõ ràng khi box object chồng hoặc nằm sát ignore; điều này dễ tạo box thừa như `L7` ở `adasind_167700.jpg` hoặc giữ nhãn trong vùng ignore.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** Bắt đầu từ vòng `r2_qa` và áp dụng cho mọi rework sau đó.
