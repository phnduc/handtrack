# Retrolens - Bộ Lọc & Cổng Không Gian Nhận Diện Bàn Tay (Hand Tracking)

Ứng dụng bộ lọc camera tương tác sử dụng cử chỉ bàn tay (hand tracking) với MediaPipe và OpenCV. Bạn có thể tạo một "cổng không gian" bằng các ngón tay để áp dụng nhiều bộ lọc thú vị (Mono, Dual-Tone, Pixelate, Invert, Sepia, Blur, Thermal, Sketch, Glitch, Neon, Galaxy).

## Yêu Cầu Hệ Thống
- Python 3.9 trở lên
- Webcam

## Hướng Dẫn Cài Đặt và Chạy

### 1. Clone Repository
Tải repository này về máy và chuyển vào thư mục dự án:
```bash
git clone <URL_GITHUB_CUA_BAN>
cd python-handtrack-main
```

### 2. Tạo Môi Trường Ảo (Virtual Environment)
Sử dụng môi trường ảo để các thư viện không bị xung đột với các dự án Python khác:
```bash
# Dành cho Windows
python -m venv .venv
.venv\Scripts\activate

# Dành cho macOS / Linux
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Cài Đặt Các Thư Viện Phụ Thuộc
Cài đặt tất cả các thư viện cần thiết bằng lệnh:
```bash
pip install -r requirements.txt
```

Hoặc cài đặt thủ công:
```bash
pip install opencv-python mediapipe numpy
```

*(Lưu ý trên macOS: Nếu gặp lỗi biên dịch MediaPipe, bạn có thể chạy: `pip install --no-compile -r requirements.txt`)*

### 4. Đảm Bảo Đã Có Các Model MediaPipe
Ứng dụng cần 2 tệp model của MediaPipe (đã có sẵn trong thư mục dự án):
1. `hand_landmarker.task` (Nhận diện các khớp và điểm mốc trên bàn tay)
2. `selfie_segmenter.tflite` (Phân đoạn hình ảnh / tách nền cho bộ lọc Galaxy)

Đảm bảo hai tệp này nằm cùng thư mục với file `main.py`.

### 5. Chạy Ứng Dụng
Khởi động chương trình bằng lệnh:
```bash
python main.py
```
*(Hoặc `.venv/bin/python main.py` nếu chạy trực tiếp qua môi trường ảo trên macOS/Linux)*

## Hướng Dẫn Sử Dụng Tính Năng

- **Mở Cổng Không Gian (Portal):** Giơ đầu ngón trỏ và ngón cái của **cả hai bàn tay** trước camera (tổng cộng 4 ngón tay). Một cổng đa giác sẽ được tạo giữa 4 ngón tay, và hiệu ứng bộ lọc sẽ xuất hiện bên trong cổng.
- **Đổi Bộ Lọc:** Đưa đầu **ngón trỏ của hai bàn tay** chạm hoặc lại gần nhau. Mỗi lần chạm sẽ tự động chuyển sang bộ lọc tiếp theo.
- **Thoát Ứng Dụng:** Nhấp chuột vào cửa sổ hiển thị camera và nhấn phím **`q`** trên bàn phím để dừng chương trình.

---
**Lưu ý:** Đảm bảo không gian có đủ ánh sáng để camera có thể nhận diện bàn tay một cách chính xác nhất.
