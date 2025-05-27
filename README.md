import pyJianYingDraft as draft

script = draft.Script_file(1080, 1080)

# Nhập phụ đề vào track có tên "subtitle", nếu track không tồn tại sẽ tự động tạo
# Không chỉ định style và clip_settings, mặc định sẽ mô phỏng style khi JianYing nhập phụ đề
script.import_srt("subtitle.srt", track_name="subtitle", time_offset="1.5s")  # Phụ đề dịch chuyển toàn bộ về sau 1.5 giây

# Có thể sử dụng các tham số `text_style` và `clip_settings` để điều chỉnh style của phụ đề, ý nghĩa của các tham số trên tương tự như trong `Text_segment()`
script.import_srt("subtitle.srt", track_name="subtitle",
                  text_style=draft.Text_style(size=10.0, color=(1.0, 0.0, 0.0))
                  clip_settings=draft.Clip_settings(transform_y=0.8))  # Đặt phụ đề ở phía trên màn hình

# Nếu cần style phức tạp hơn hoặc muốn áp dụng animation cho phụ đề, có thể truyền một đối tượng `Text_segment` làm tham chiếu style cho tham số `style_reference` (bỏ qua thiết lập text và độ dài đoạn của nó)
# Chú ý thời gian animation sẽ không được điều chỉnh theo độ dài đoạn phụ đề, do đó khi đoạn phụ đề quá ngắn có thể xuất hiện hiệu ứng kỳ lạ
script.import_srt("subtitle.srt", track_name="subtitle", style_reference=seg1)  # Lấy text trong mục "Thêm Text" ở trên làm tham chiếu

# Mặc định sẽ không sử dụng thiết lập `clip_settings` trong đoạn `style_reference`, nếu cần thì vui lòng truyền rõ ràng `clip_settings=None`
script.import_srt("subtitle.srt", track_name="subtitle", style_reference=seg1, clip_settings=None)  # Tương đương clip_settings=seg1.clip_settings
