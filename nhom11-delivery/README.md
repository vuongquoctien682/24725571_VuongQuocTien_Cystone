# Bản dự án Nhóm 11 đã sửa

Thư mục này chứa bản bàn giao theo yêu cầu của chủ kho. Nội dung bài tập có sẵn trong kho được giữ nguyên.

## Tải tệp

- [Toàn bộ dự án: Nhom11_DaSua.zip](Nhom11_DaSua.zip?raw=true)
- [Báo cáo Word: Nhom11_BaoCao_DaSua.docx](Nhom11_BaoCao_DaSua.docx?raw=true)
- [Danh sách thay đổi và giới hạn](Nhom11_NhungThayDoi.md)

Nếu GitHub hiển thị trang xem tệp, chọn **Download raw file**. ZIP chứa đầy đủ mã nguồn, notebook, dữ liệu, model, Docker và báo cáo cập nhật.

## Kiểm thử

Đã chạy 10 notebook (85 cell code, không có error output); ghi/đọc 10.000 dòng qua SQLite và MongoDB; kiểm tra các tab PCA, K-Means, Regression, Classification, Database trên Docker. Bảng kết quả, log và ảnh chụp nằm trong `report/validation/` của ZIP.

Dữ liệu raw, giao dịch mô phỏng và ngân hàng nhận xét gốc được giữ nguyên. Bản kiểm tra không gọi lại Ollama để xác minh lịch sử sinh nhận xét. Các giới hạn của dữ liệu mô phỏng và đánh giá mô hình được ghi trong báo cáo.

Trước khi nộp, mở Word cập nhật mục lục và kiểm tra ngắt trang. Chạy lại `docker compose up --build` trên máy thuyết trình theo README trong ZIP.

SHA256SUMS.txt dùng để kiểm tra toàn vẹn tệp tải về.
