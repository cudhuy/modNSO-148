# NSO 148 Mod & JavaME E72 Development Workspace

Bộ môi trường phát triển (Workspace) toàn diện dùng để lập trình, tùy biến (build) và vận hành các bản Mod game **Ninja School Online (NSO) phiên bản 148 (Java)**. Dự án được cấu hình tối ưu cho giao diện Nokia E72 và tích hợp sẵn bộ công cụ hỗ trợ treo game số lượng lớn trên hệ điều hành Windows.

---

## 📁 Thành phần dự án (Project Components)

Dự án này được chia làm hai phần chính: Môi trường lập trình (Build Environment) và Bộ tài nguyên vận hành game (Game Package).

### 1. JavaME Build E72 (Môi trường phát triển)
*   **Eclipse IDE & J2ME Plugin:** Trình mã nguồn và quản lý dự án, đã tích hợp plugin hỗ trợ phát triển ứng dụng di động cổ điển (JavaME).
*   **Java Development Kit (JDK 1.8):** Phiên bản Java ổn định và tương thích tốt nhất để biên dịch các project JavaME/J2ME cũ mà không bị lỗi thư viện.
*   **Sun Java Wireless Toolkit (WTK) & Oracle JavaME SDK:** Bộ công cụ cấu hình thiết bị giả lập, tiền biên dịch (preverify) và đóng gói mã nguồn thành file `.jar` hoàn chỉnh.

### 2. NSO 148 Package (Mã nguồn & Công cụ vận hành)
*   **Source Code Mod NSO 148:** Toàn bộ mã nguồn bản mod 148, cho phép can thiệp sâu để viết thêm tính năng (Auto chat, tàn sát, quạt buff, né anticheat...).
*   **MicroEmulator (Tối ưu hóa):** Trình giả lập Java siêu nhẹ trên PC, ngốn cực ít tài nguyên.
    *   *Bản E72 X1:* Cấu hình chuẩn độ phân giải màn hình ngang ($320 \times 240$) và map phím đặc trưng của Nokia E72.
    *   *Bản X5:* Phiên bản tối ưu sẵn để nhân bản ứng dụng, hỗ trợ mở nhiều tab game cùng lúc.
*   **Search.exe:** Công cụ (Tool Auto Search) hỗ trợ tự động quét các cửa sổ MicroEmulator đang chạy, cho phép quản lý tập trung và ra lệnh đồng loạt (Multi-control) cho dàn tài khoản clone.

---

## 🚀 Hướng dẫn thiết lập nhanh (Quick Start)

1.  **Cài đặt môi trường:** Cài đặt `JDK 1.8` và cấu hình biến môi trường (`JAVA_HOME`) trên Windows.
2.  **Import Source Code:** Mở `Eclipse`, trỏ Workspace về thư mục chứa mã nguồn Mod NSO 148. Hãy đảm bảo đã thêm đường dẫn của `Wireless Toolkit (WTK)` vào phần quản lý Device trong Preferences của Eclipse.
3.  **Build & Run:** Thực hiện chỉnh sửa code theo nhu cầu, tiến hành Build dự án để xuất ra file `.jar`. Sử dụng `MicroEmulator` để chạy thử nghiệm.

---

## ⚠️ Lưu ý quan trọng về Bảo mật (Security Notice)

*   **Về file `search.exe`:** Do cơ chế hoạt động của tool là thực hiện ghi nhớ và can thiệp sâu vào cửa sổ ứng dụng khác (Process Hooking / Window Searching), **Windows Defender hoặc các phần mềm diệt virus sẽ nhận diện nhầm file này là Trojan/Virus** và tự động xóa.
*   **Khuyến nghị:** 
    *   Nên thêm file này vào danh sách loại trừ (Exclusion) của trình diệt virus nếu bạn tin tưởng nguồn gốc mã nguồn.
    *   Để đảm bảo an toàn tuyệt đối cho máy tính cá nhân, khuyến khích chạy toàn bộ gói vận hành game (`MicroEmulator` + `search.exe`) bên trong **Máy ảo (VMware / VirtualBox)** hoặc **VPS Windows** riêng biệt.
