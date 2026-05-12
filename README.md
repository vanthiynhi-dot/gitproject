# **ĐỀ TÀI: BANK CUSTOMER CHURN PREDICTION**
## Mô tả ngắn
Xây dựng và so sánh hiệu quả của các mô hình học máy trong việc dự đoán khả năng rời bỏ (churn). Quá trình thực hiện bao gồm các bước chính: tiền xử lý dữ liệu, lựa chọn biến đầu vào có ý nghĩa thống kê, huấn luyện và đánh giá mô hình. Cụ thể, bốn thuật toán được áp dụng gồm Logistic Regression, K-Nearest Neighbors (KNN), Random Forest và XGBoost. Mục tiêu của đề tài là dự đoán khả năng rời bỏ của khách hàng trong lĩnh vực ngân hàng dựa trên dữ liệu lịch sử và đặc điểm hành vi của họ. Từ các kết quả phân tích, nhóm nghiên cứu kỳ vọng đề xuất các định hướng chiến lược giữ chân phù hợp cho từng nhóm khách hàng. 
## Cài đặt các lệnh cần thiết
pip install pandas openpyxl scikit-learn imbalanced-learn joblib xgboost matplotlib seaborn shap
## Hướng dẫn sử dụng
- Tạo các biểu đồ trực quan hóa dữ liệu thô (phân phối, mối quan hệ giữa các biến danh mục và Rời bỏ) trong EDA.ipynb
- Thực hiện làm sạch, loại bỏ outliers, chia tập Train/Test/Val, và lưu bộ tiền xử lý
- Triển khai pipeline
- Thực hiện GridSearchCV trên 4 mô hình (Logistic Regression, KNN, Random Forest, XGBoost), chọn mô hình tốt nhất dựa trên AUC, và lưu Pipeline mô hình tốt nhất.
- Tạo biểu đồ Đường cong ROC so sánh hiệu suất phân loại của tất cả các mô hình đã huấn luyện.
- Tạo biểu đồ SHAP Summary Plot để giải thích các yếu tố nào là quan trọng nhất đối với dự đoán của mô hình tốt nhất.
## Cấu trúc dự án
MLML_BankCustomerChurnPrediction/
│
├──  README.md # File giới thiệu tổng quan dự án, hướng dẫn cài đặt và chạy code
├── requirements.txt # Liệt kê các thư viện cần thiết các bản version
│
├──  data/
│ ├── unprocessed/ # Chứa dữ liệu thô, không chỉnh sửa
│ └── processed/ # Chứa dữ liệu đã qua tiền xử lý
│
├──  notebooks/ # Chứa các file Jupyter Notebook cho EDA, thử nghiệm nhanh
│ ├── 1.0-EDA.ipynb
│ └── 2.0-model-prototyping.ipynb # Thử nghiệm, xây dựng và so sánh các mô hình
│
├── src/ # Chứa mã nguồn chính của dự án
│ ├── data_processing.py # Các hàm tiền xử lý dữ liệu
│ ├── train.py # Script để huấn luyện mô hình
│ └── predict.py # Script để đưa ra dự đoán từ mô hình đã lưu
│
├──  models/ # Chứa các file mô hình đã được huấn luyện và lưu lại 
│
└──  reports/ # Chứa báo cáo, hình ảnh, biểu đồ
 └── figures/ # Các biểu đồ, hình ảnh đã
