📌 1. Bài toán

Tên bài toán: Dự đoán khả năng vỡ nợ (tín dụng xấu) của khách hàng dựa trên dữ liệu Give Me Some Credit (Kaggle).

Mục tiêu:

Dự đoán xác suất một khách hàng sẽ bị vỡ nợ (SeriousDlqin2yrs = 1) trong vòng 2 năm tới.

Hỗ trợ ngân hàng / tổ chức tài chính ra quyết định cho vay.

Đặc điểm dữ liệu:

150,000 khách hàng.

Các thuộc tính: độ tuổi, thu nhập hàng tháng, số người phụ thuộc, số lần trễ hạn, tỷ lệ nợ,…

Biến mục tiêu: TARGET (1 = xấu, 0 = tốt).

Dữ liệu mất cân bằng (≈ 93% tốt, 7% xấu).

📌 2. Thuật toán

Sử dụng XGBoost (Extreme Gradient Boosting) – một thuật toán ensemble boosting tree mạnh mẽ cho dữ liệu tabular.

Lý do chọn:

Hiệu quả cao với dữ liệu có nhiều đặc trưng số.

Xử lý tốt mất cân bằng lớp với tham số scale_pos_weight.

Hỗ trợ early stopping, regularization, feature importance.

Ngoài ra có sử dụng:

RandomizedSearchCV (sklearn) để tìm siêu tham số tối ưu.

SHAP (tùy chọn) để giải thích mô hình.

📌 3. Công cụ & thư viện

Ngôn ngữ: Python

Công cụ & thư viện chính:

pandas, numpy: xử lý dữ liệu.

matplotlib, seaborn: trực quan hóa.

scikit-learn: pipeline, tiền xử lý, train/test split, cross-validation.

xgboost: huấn luyện mô hình.

joblib: lưu/trích xuất mô hình.

flask: xây dựng ứng dụng web demo.

📌 4. Quy trình giải quyết

Tiền xử lý dữ liệu:

Xử lý giá trị thiếu (SimpleImputer – median).

Chuẩn hóa dữ liệu (StandardScaler).

Loại bỏ trùng lặp, clip tuổi trong khoảng hợp lý.

Chia dữ liệu: train / validation / test.

Huấn luyện baseline model với XGBoost.

Tối ưu siêu tham số bằng RandomizedSearchCV.

Huấn luyện final model với early stopping.

Đánh giá mô hình: ROC-AUC, confusion matrix, classification report.

Trực quan hóa: ROC curve, feature importance.

Triển khai ứng dụng web: nhập chỉ số → dự đoán → hiển thị kết quả.

<img width="1896" height="877" alt="image" src="https://github.com/user-attachments/assets/2e8a37ae-29c7-4437-b167-48fca2bdae56" />
