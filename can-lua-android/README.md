# Sổ Cân Lúa

App Android ghi số cân từng bao. Cứ 5 bao thành một thẻ, tự cộng tổng thẻ, tổng bao, tổng kg, thành tiền theo giá lúa. Chạy không cần mạng, dữ liệu lưu trong bộ nhớ của app.

## Tải APK

Vào mục **Releases** của repo này, tải file `SoCanLua.apk` ở bản "mới nhất", mở file trên điện thoại và cài đặt (cho phép cài app từ nguồn này nếu máy hỏi).

Mỗi lần có thay đổi được đẩy lên nhánh `main`, GitHub tự build lại và thay file APK trong Releases. Mọi bản đều dùng cùng một khoá ký nên cài đè lên bản cũ được và không mất dữ liệu. Không gỡ app trước khi cài bản mới, vì gỡ app sẽ xoá dữ liệu.

## Cập nhật app

Trong app, bấm nút mũi tên tải xuống ở góc trên màn hình chính. App kiểm tra bản mới trên mục Releases của repo, nếu có thì bấm **Tải bản mới**, mở file vừa tải để cài đè. Khi mở app, nếu có bản mới sẽ hiện chấm đỏ trên nút này.

Để kiểm tra được, repo cần để chế độ **Public**. Repo Private thì app không đọc được Releases.

Cùng màn hình đó có **Nhật ký lỗi**: app tự ghi lại lỗi, bấm **Sao chép lỗi** rồi gửi để biết sửa ở đâu.

## Cấu trúc

- `www/index.html`: toàn bộ giao diện và logic (một file duy nhất).
- `android/`: dự án Android do Capacitor tạo.
- `keystore/debug.keystore`: khoá ký cố định cho bản build (xem ghi chú bên dưới).
- `.github/workflows/build-apk.yml`: quy trình build APK tự động.

## Sửa giao diện

Sửa `www/index.html`, rồi đẩy lên `main`. GitHub sẽ build lại APK.

## Ghi chú về khoá ký

File `keystore/debug.keystore` là khoá ký bản debug (mật khẩu mặc định `android`). Vì cần để repo Public cho tính năng cập nhật, ai cũng có thể lấy khoá này. Với app dùng cá nhân thì rủi ro thấp (chỉ nguy hiểm nếu bạn bị lừa cài một file APK lạ). Muốn chặt hơn thì chuyển khoá vào GitHub Secrets.
