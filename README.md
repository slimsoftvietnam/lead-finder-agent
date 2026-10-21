# Lead Finder Agent

Skill nghiên cứu và chọn lọc khách hàng tiềm năng B2B, tìm đúng người liên hệ theo vai trò và chuẩn bị nội dung tiếp cận có dẫn chứng.

## Skill này hỗ trợ gì?

- Xác định tiêu chí phù hợp với sản phẩm, khách hàng lý tưởng và khu vực mục tiêu.
- Tìm công ty và người phụ trách phù hợp qua nhiều nguồn công khai, bao gồm LinkedIn khi có thể truy cập hợp lệ.
- Xác minh email công việc, số điện thoại công việc và hồ sơ nghề nghiệp; gắn nguồn cho từng thông tin.
- Khi được yêu cầu lead có thông tin liên hệ, ưu tiên người có cả email và số điện thoại trực tiếp đã xác minh. Không đoán thông tin hoặc thay liên hệ cá nhân bằng hotline/hộp thư chung.
- Chấm điểm mức phù hợp của công ty và người liên hệ riêng biệt; chuẩn bị Google Sheet, báo cáo HTML và bản nháp tiếp cận theo yêu cầu.

Mặc định nội dung trả cho người dùng bằng tiếng Việt. Kết quả nghiên cứu chỉ dùng thông tin nghề nghiệp công khai; một liên hệ công khai không đồng nghĩa với sự đồng ý nhận tiếp thị.

## Cấu trúc

- [`SKILL.md`](SKILL.md): hướng dẫn chính và quy tắc chọn nguồn, nghiên cứu, đánh giá, tiếp cận.
- [`references/research-workflow.md`](references/research-workflow.md): các bước nghiên cứu tài khoản, tìm người và kiểm tra kênh liên hệ.
- [`references/outreach-brand-voice-huong-v3.md`](references/outreach-brand-voice-huong-v3.md): hướng dẫn giọng văn chỉ áp dụng cho chiến dịch SlimAI khi người dùng chọn chiến dịch đó.
- [`agents/openai.yaml`](agents/openai.yaml): tên hiển thị và lời nhắc gợi ý trong giao diện Codex.

## Cài đặt

Đặt hoặc sao chép toàn bộ thư mục repository này vào thư mục skills mà Codex của bạn đang nạp. Với skill cấp dự án, cấu trúc thường dùng là:

```text
<dự-án>/.agents/skills/lead-finder-agent/
```

Đảm bảo `SKILL.md`, thư mục `agents/` và `references/` nằm cùng trong thư mục skill.

## Cách sử dụng

Gọi `$lead-finder-agent` và nêu ngắn gọn:

1. Sản phẩm/dịch vụ, đơn vị gửi và thông tin đã được xác nhận.
2. Ngành, quy mô, khu vực và chức danh cần tìm.
3. Số lượng lead mong muốn; có bắt buộc mỗi người phải có cả email và số điện thoại hay không.
4. Google Sheet hoặc danh sách hiện có cần cập nhật, nếu có.
5. Đầu ra cần nhận: danh sách, báo cáo, bản nháp email hay ghi chú LinkedIn.

Ví dụ:

> Dùng `$lead-finder-agent` tìm 10 người phụ trách đào tạo hoặc chuyển đổi số tại doanh nghiệp ở Hà Nội cho [sản phẩm]. Ưu tiên người có email công việc và số điện thoại trực tiếp công khai; cập nhật Google Sheet tôi chỉ định và chuẩn bị bản nháp email bằng tiếng Việt.

Skill sẽ báo rõ số người tìm được, mức độ xác minh từng kênh và những liên hệ chưa tìm thấy công khai. Không tự gửi email hoặc tin nhắn khi chưa được người dùng cho phép.

## Repo

Repository GitHub: [slimsoftvietnam/lead-finder-agent](https://github.com/slimsoftvietnam/lead-finder-agent)
