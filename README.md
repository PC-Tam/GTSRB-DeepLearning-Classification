# GTSRB Deep Learning Classification

Dự án phân loại Biển báo giao thông Đức (German Traffic Sign Recognition Benchmark - GTSRB) sử dụng Deep Learning, cụ thể là các mô hình **ResNet50** và **Vision Transformer (ViT)**.

## Cấu trúc dự án

- `notebooks/`: Chứa các Jupyter Notebook thực thi theo từng giai đoạn:
  - `section1_preprocessing.ipynb`: Tải dataset từ Kaggle, tiền xử lý và chia tách tập Train/Val.
  - `section2_resnet50.ipynb`: Huấn luyện và đánh giá mô hình ResNet50.
  - `section3_vit.ipynb`: Huấn luyện và đánh giá mô hình Vision Transformer (ViT).
  - `section4_demo.ipynb`: Giao diện người dùng (UI) Gradio để thử nghiệm nhận diện biển báo trực tiếp.
- `src/`: Các mã nguồn Python chứa định nghĩa Model, Dataset, Transforms và Inference.
- `configs/`: Chứa các file cấu hình `json` cho dữ liệu và các mô hình.
- `checkpoints/`: Nơi lưu trữ trọng số (`.pth`) của các mô hình tốt nhất sau khi huấn luyện.
- `history/`: Lưu trữ lịch sử huấn luyện (`.csv`, `.json`) và báo cáo đánh giá (Classification Report, Confusion Matrix).
- `assets/`: Lưu trữ các hình ảnh, biểu đồ Loss/Accuracy và ảnh Demo.

## Cài đặt & Chạy dự án

1. Cài đặt các thư viện cần thiết:
   ```bash
   pip install -r requirements.txt
   ```

2. Tải dữ liệu:
   Mở và chạy toàn bộ **`section1_preprocessing.ipynb`**. Notebook này sẽ yêu cầu tài khoản Kaggle (`kaggle.json`) để tải tự động bộ dữ liệu GTSRB về máy và xử lý.

3. Huấn luyện mô hình:
   Chạy các notebook **`section2_resnet50.ipynb`** hoặc **`section3_vit.ipynb`** để bắt đầu huấn luyện. Kết quả và trọng số sẽ được tự động lưu vào `checkpoints/` và `history/`.

4. Chạy giao diện Demo:
   Mở **`section4_demo.ipynb`** và chạy để trải nghiệm nhận diện biển báo trên giao diện web Gradio.

## Kết quả (ResNet50)
*Mô hình sử dụng ResNet50 Pretrained (chỉ train lớp FC cuối).*
- Biểu đồ Loss & Accuracy được lưu trong thư mục `assets/`
- Thông số chi tiết trên tập Validation được ghi tại `history/classification_report_resnet.txt`