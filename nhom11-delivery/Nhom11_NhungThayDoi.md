# Các thay đổi chính

Bản sửa giữ nguyên các file raw, giao dịch mô phỏng và ngân hàng nhận xét của ZIP gốc. File ZIP gốc không bị ghi đè.

- Thống nhất Python3.12 và scikit-learn1.8.0; bổ sung dependencies thực sự cần, tách requirements cho phân tích.
- Sửa đường dẫn Windows trong notebook sang tìm thư mục dự án; thêm link nguồn đầu code; xác thực concat/merge, khóa và row counts.
- Sửa EDA gán lại DataFrame làm mất xử lý trước đó. Phân biệt khuyết cấu trúc và missing ngẫu nhiên; không tự điền rating Tesco bằng rating Tiki hoặc dùng0/False cho unknown.10 Category chuyển Unknown; rating sản phẩm0/chưa đánh giá thành NaN. Biến số cốt lõi giữ nguyên.
- Bổ sung thống kê, missingno/before-after, IQR/Z-score, crosstab, biểu đồ và giải thích gắn với mô hình; xuất bảng/ảnh có thể kiểm tra.
- PCA lưu đúng đối tượng9 thành phần. K-Means đối chứng trên3PC (89,9281%), vẫn chọn nonPCA K3 theo quy tắc.
- Hồi quy xuất đúng tên `.joblib` mà app đọc; chỉ số mới từ thực thi:R²0,8139285,RMSE2.413.807,62VND.
- Cả hồi quy/phân lớp chọn model trên validation rồi đánh giá test. Phân lớp chọn LogisticRegression theo validation; cung cấp report đầy đủ cả2 mô hình và majority baseline, không che giấu kết quả thấp.
- Thay đường chạy CSDL phụ thuộc SQLServer/Atlas cá nhân bằng SQLite(SQL)+MongoDB local/Compose; giữ script SQLServer như lựa chọn bổ sung. Không lưu URI chứa mật khẩu; đối chiếu dữ liệu đọc ngược và import idempotent.
- Docker tự khởi tạo hai CSDL rồi chạy Streamlit; app có tab Database để đọc thực tế. Có2 volume persistent,network nội bộ,healthcheck.
- Chạy kiểm tra4 chức năng model bằng AppTest; kiểm tra thêm cả5 tab bằng Chromium trên Docker và chụp minh chứng thật.
- Cập nhật DOCX: thêm Stage1/EDA, thay bảng/ảnh/kết luận cũ, bổ sung minh chứng CSDL và Docker; phân biệt6.559 sản phẩm catalogue với6.556 sản phẩm đủ giá.

## Kiểm chứng đã thực hiện

10 notebook đã có lượt chạy mới,85 cell code có execution_count,0 error outputs. Notebook02 xác minh dữ liệu snapshot, không sinh lại bằng LLM. Xem `report/validation/notebook_inventory.json`, bảng kết quả mô hình trong `notebooks/figures/` và `notebooks/results/`.

SQL+MongoDB:10.000 dòng39 cột mỗi bên,khớp từng giá trị với master_dataset; lặp import thành công. Docker image chứa code/model/data đúng bản bàn giao,hai service healthy. AppTest và browser tests đều pass.

## Giới hạn còn lại

- Không xác minh lại các lần gọi Ollama lịch sử; cần log chạy LLM thật nếu giảng viên yêu cầu.
- Các giao dịch/Rating là mô phỏng; mô hình không được xem là sản phẩm dự đoán thị trường đáng tin cậy.
- Quy tắc cắt10 Revenue cực lớn từ EDA toàn tập được giữ để so sánh benchmark cũ; với dữ liệu thật cần xác định xử lý từ train và giữ nguyên target test.
- SQLServer tùy chọn chưa chạy lại; luồng đã kiểm tra dùng SQLite và MongoDB.
- DOCX kiểm tra nội dung/XML/ảnh; cần cập nhật mục lục và xem lại bố cục trong Word trước khi nộp. Không có slide đi kèm.
