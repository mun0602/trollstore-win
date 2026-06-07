# TrollRestore Windows GUI

Bộ cài đặt TrollStore tự động và bảo mật chạy trực tiếp dưới dạng giao diện đồ họa WPF trên Windows (.NET 8.0).

## Tính năng
- Giao diện Dark-theme cao cấp, bo góc tròn không viền.
- Đăng nhập xác thực thiết bị (mật khẩu mặc định: `1305`).
- Tích hợp sẵn tiến trình cài đặt TrollStore độc lập (không cần cài đặt Python trên máy khách).
- Hỗ trợ chẩn đoán kết nối USB, cung cấp link tải iTunes Driver và UsbDk nhanh chóng.
- Theo dõi logs cài đặt thời gian thực và sao chép logs nhanh vào Clipboard.

## Hướng dẫn sử dụng
1. Tải bản phát hành mới nhất từ mục Releases hoặc Artifacts của GitHub Actions.
2. Giải nén toàn bộ thư mục và chạy file `TrollRestoreWin.exe`.
3. Kết nối iPhone/iPad qua cáp USB, chọn **Tin cậy (Trust)** và nhập mật khẩu **1305** trên giao diện để tiếp tục.

## Hướng dẫn Build (Dành cho nhà phát triển)
Yêu cầu:
- Windows OS
- .NET 8.0 SDK
- Python 3.10+ & PyInstaller

Biên dịch CLI (PyInstaller):
```bash
pip install -r requirements.txt
pyinstaller TrollRestore.spec
```
Sau đó copy file `TrollRestore.exe` trong thư mục `dist/` vào thư mục gốc dự án.

Biên dịch WPF GUI:
```bash
dotnet publish TrollRestoreWin.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:PublishReadyToRun=true -o publish/
```
Toàn bộ sản phẩm hoàn chỉnh sẽ nằm trong thư mục `publish/`.
