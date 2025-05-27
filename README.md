# pyJianYingDraft
### Công cụ tạo và xuất bản nháp JianYing bằng Python nhẹ, linh hoạt, dễ sử dụng, xây dựng quy trình chỉnh sửa/trộn video tự động hoàn toàn!

> ℹ Chào mừng bạn bổ sung phương thức giải mã cho các tệp tin nháp phiên bản 6+ cho dự án này.

> 🧪 Dự án này vẫn đang được cập nhật nhanh chóng, chào mừng bạn ⭐️ dự án này để tiếp tục theo dõi!

> 📢 Chào mừng bạn tham gia [Máy chủ Discord](https://discord.gg/WfHgGQvhyW) để thảo luận về cách sử dụng hoặc các tính năng mới.

## Ý tưởng sử dụng
![Ý tưởng sử dụng](readme_assets/使用思路.jpg)

# Danh sách tính năng
> ℹ Nếu không có ghi chú thêm, thường chỉ được thử nghiệm trên phiên bản 5.9.

> Các tính năng được đánh dấu ☑️ **đã hoàn thành**, các tính năng được đánh dấu ⬜ **chưa hoàn thành**.

### Chế độ Mẫu (Template Mode)
> ⚠️ Các phiên bản JianYing 6+ đã mã hóa tệp `draft_content.json`, do đó **loạt tính năng này hiện chỉ hỗ trợ các phiên bản JianYing 5.9 trở xuống**.

- ☑️ [Tải](#tải-mẫu) tệp `draft_content.json` (chưa mã hóa) làm mẫu.
- ☑️ [Thay thế material của các đoạn âm thanh/video](#thay-thế-material-dựa-trên-tên)
- ☑️ [Sửa đổi nội dung text của các đoạn text](#thay-thế-nội-dung-đoạn-text)
- ☑️ [Nhập toàn bộ các track âm thanh/video/text từ bản nháp mẫu vào một bản nháp khác](#nhập-các-track-từ-bản-nháp-mẫu)
- ☑️ [Trích xuất thông tin meta của các sticker/khung thoại/chữ nghệ thuật xuất hiện trong mẫu](#trích-xuất-siêu-dữ-liệu-material)

### Xuất hàng loạt
> ⚠️ Các phiên bản JianYing 7+ đã ẩn các control, do đó **loạt tính năng này hiện chỉ hỗ trợ các phiên bản JianYing 6 trở xuống**.

- ☑️ Điều khiển JianYing mở bản nháp được chỉ định.
- ☑️ [Xuất bản nháp đến vị trí được chỉ định](#xuất-hàng-loạt-bản-nháp)
- ☑️ Điều chỉnh độ phân giải và tốc độ khung hình khi xuất.
- Cảm ơn `@litter jump` đã cung cấp một phần ý tưởng.

### Video và Hình ảnh
> ℹ Các tính năng tạo bản nháp sau đây (âm thanh/video, sticker, text, hiệu ứng, v.v.) hỗ trợ tất cả các phiên bản JianYing 5 trở lên.

- ☑️ Thêm material video/hình ảnh cục bộ, và [tùy chỉnh thời gian, thời lượng hoặc tốc độ phát của đoạn](#cắt-xén-material-và-thay-đổi-tốc-độ-tổng-thể)
- ☑️ [Điều chỉnh tổng thể video](#điều-chỉnh-tổng-thể-video) (xoay, thu phóng, độ sáng, v.v.) và [tạo keyframe](#keyframe)
- ☑️ [Animation vào/ra/kết hợp](#thêm-animation-cho-đoạn) cho các đoạn video
- ☑️ Thêm [mask](#mask), [hiệu ứng đoạn](#thêm-hiệu-ứng-đoạn) và [bộ lọc (filter)](#thêm-bộ-lọc-đoạn)
- ☑️ (Tính năng thưởng khi dự án đạt 700⭐️) Điền nền video [(Mã ví dụ)](demo.py)
### Sticker
- ☑️ [Thêm sticker](#trích-xuất-siêu-dữ-liệu-material) dựa trên thông tin meta
- ☑️ Tạo [keyframe](#keyframe) cho sticker
### Âm thanh (Audio)
- ☑️ Thêm material âm thanh cục bộ, và [tùy chỉnh thời gian, thời lượng hoặc tốc độ phát của đoạn](#cắt-xén-material-và-thay-đổi-tốc-độ-tổng-thể)
- ☑️ Điều chỉnh thời lượng mờ dần vào/ra [(Mã ví dụ)](demo.py), điều chỉnh âm lượng [(Mã ví dụ)](demo.py) và [keyframe](#keyframe) của nó
- ☑️ Thêm [hiệu ứng âm thanh cảnh](#thêm-hiệu-ứng-đoạn) cho đoạn âm thanh, và thiết lập thông số
### Track (Rãnh)
- ☑️ [Thêm track](#thao-tác-đa-track) và [thêm đoạn vào track được chỉ định](#thao-tác-đa-track)
- ☑️ Tùy chỉnh [quan hệ lớp (layer)](#thao-tác-đa-track) của các track video/bộ lọc/hiệu ứng
### Hiệu ứng (Effects), Bộ lọc (Filters) và Chuyển cảnh (Transitions)
- ☑️ [Hiệu ứng](#thêm-hiệu-ứng-đoạn), [bộ lọc](#thêm-bộ-lọc-đoạn) và [animation](#thêm-animation-cho-đoạn) gắn liền với đoạn
- ☑️ [Hiệu ứng và bộ lọc trên track độc lập](#hiệu-ứng-và-bộ-lọc-trên-track-độc-lập)
- ☑️ Thêm chuyển cảnh [(Mã ví dụ)](demo.py), và tùy chỉnh thời lượng của nó
### Văn bản (Text) và Phụ đề (Subtitles)
- ☑️ [Thêm text, thiết lập font chữ và style](#thêm-text), sửa đổi [cài đặt vị trí và xoay](#điều-chỉnh-tổng-thể-video) của đoạn text
- ☑️ [Keyframe](#keyframe) và [animation](#thêm-animation-cho-đoạn) của text
- ☑️ Viền chữ và nền chữ
- ☑️ Hiệu ứng khung thoại chữ và hiệu ứng chữ nghệ thuật [(Mã ví dụ)](demo.py)
- ☑️ [Nhập tệp `.srt`](#nhập-phụ-đề) để tạo phụ đề và thiết lập định dạng hàng loạt

# Cài đặt
pyJianYingDraft hiện đã hỗ trợ cài đặt qua pip (không bao gồm demo), khuyến nghị sử dụng phiên bản Python 3.8 hoặc 3.11 đã được thử nghiệm trong quá trình phát triển.
```
pip install pyJianYingDraft
```

> ℹ Nếu gặp lỗi import sau khi cài đặt, có thể liên quan đến vấn đề tương thích của uiautomation, xem [issue liên quan](https://github.com/GuanYixuan/pyJianYingDraft/issues/12)

# Bắt đầu nhanh
Ví dụ `demo.py` sẽ tạo một tệp nháp JianYing chứa material âm thanh/video và một dòng text, đồng thời thêm hiệu ứng mờ dần âm thanh, animation vào video, hiệu ứng chuyển cảnh và khung thoại/chữ nghệ thuật cho text.

Cách thực hiện ví dụ này như sau:
1.  Trong JianYing, **tạo một bản nháp trống**, tìm **đường dẫn thư mục** tương ứng của nó (tương tự `.../JianyingPro Drafts/9月5日`)
2.  **Quay lại trang chủ JianYing** hoặc thoát JianYing
3.  Thay đổi giá trị của biến `DUMP_PATH` trong mã thành **đường dẫn `draft_content.json` trong thư mục bản nháp**, sau đó chạy `demo.py`
4.  Bây giờ, **mở lại bản nháp này** trong JianYing, bạn sẽ thấy một timeline tương tự như sau:

![Bắt đầu nhanh](readme_assets/快速上手.png)

Bạn có thể kiểm tra kỹ cài đặt âm lượng của đoạn âm thanh, thời lượng hiệu ứng mờ dần vào và hiệu ứng animation vào của đoạn video, v.v., xem có khớp với cài đặt trong mã ở trên không.

# Tài liệu sử dụng

> ℹ Phần tài liệu nên chọn đọc các tính năng bạn quan tâm từ mục [Danh sách tính năng](#danh-sách-tính-năng), thay vì đọc theo thứ tự.

### Chế độ Mẫu (Template Mode)
Để giữ lại một số tính năng phức tạp (hiệu ứng text, đoạn kết hợp...), bạn có thể tải một bản nháp JianYing hiện có làm mẫu, sau đó nhập nội dung của nó vào một bản nháp khác, hoặc trực tiếp **thay thế nội dung của một số đoạn trong đó**.

Hiện tại cung cấp **ba chức năng thay thế**:
- [Thay thế material dựa trên tên](#thay-thế-material-dựa-trên-tên): Thay thế trực tiếp material, ảnh hưởng tự nhiên đến tất cả các đoạn tham chiếu đến material đó.
- [Thay thế material dựa trên đoạn](#thay-thế-material-dựa-trên-đoạn): Thay thế material của một đoạn cụ thể, đồng thời chọn lại phạm vi material mà nó tham chiếu.
- [Thay thế nội dung đoạn text](#thay-thế-nội-dung-đoạn-text): Giữ lại tất cả định dạng text, nhưng thay thế nội dung của nó.

Ngoài ra, đối với một số tính năng không có tên cụ thể (sticker, chữ nghệ thuật, v.v.), cung cấp chức năng [Trích xuất siêu dữ liệu material](#trích-xuất-siêu-dữ-liệu-material) để trích xuất `resource_id` của chúng.

> ⚠️ Do các phiên bản JianYing 6+ đã mã hóa tệp nháp, nên **tạm thời không hỗ trợ tải các tệp nháp từ phiên bản 6+** làm mẫu.

> ℹ Nếu xảy ra tình trạng mất nội dung mẫu, hoan nghênh phản hồi.

#### Tải Mẫu
Khuyến nghị sử dụng `Draft_folder` để quản lý thư mục nháp của JianYing (có thể tra cứu trong `Cài đặt chung` - `Vị trí bản nháp` của JianYing), điều này giúp dễ dàng tạo bản nháp mới dựa trên mẫu hiện có.

```python
import pyJianYingDraft as draft

draft_folder = draft.Draft_folder("<Thư mục bản nháp JianYing>")  # Thường có dạng ".../JianyingPro Drafts"
script = draft_folder.duplicate_as_template("Mẫu bản nháp", "Bản nháp mới")  # Sao chép "Mẫu bản nháp", đặt tên là "Bản nháp mới", đồng thời mở bản nháp mới để chỉnh sửa

# Chỉnh sửa đối tượng Script_file được trả về, ví dụ: thay thế material, thêm track, đoạn, v.v.

script.save()  # Lưu "Bản nháp mới" của bạn
```

Để tương thích tối đa với các tính năng phức tạp trong mẫu, **các track được nhập và các track được tạo bởi pyJianYingDraft là riêng biệt**, cụ thể:

- Ngoài các chức năng thay thế được đề cập dưới đây, không thể thêm đoạn, chuyển cảnh, mờ dần vào/ra, hiệu ứng, v.v. vào các track được nhập.
- **Vẫn có thể tạo track mới và thêm đoạn, v.v. vào đó**, giống như chế độ không dùng mẫu.

> ℹ Hạn chế của track nhập có thể sẽ được loại bỏ dần trong các phiên bản tiếp theo.

#### Trích xuất siêu dữ liệu material
Đối với đối tượng `Script_file` được nhập, có thể gọi phương thức `inspect_material` để trích xuất `resource_id` của một số material.
`Draft_folder` cũng có các phương thức tương ứng để trích xuất siêu dữ liệu material của bản nháp được chỉ định.

```python
import pyJianYingDraft as draft

draft_folder = draft.Draft_folder("<Thư mục bản nháp JianYing>")
draft_folder.inspect_material("Tên bản nháp")

# Hoặc
script = draft_folder.load_template("Tên bản nháp")
script.inspect_material()
```

Đầu ra của mã trên có thể tương tự như

```
Material sticker:
        Resource id: 7405878923323641129 'Lá phong vẽ tay mùa thu'
        Resource id: 7429353555447893260 'Khuyến mãi mua sắm thương mại điện tử/Wow'
        Resource id: 7437707455267671315 'Chữ trang trí vlog mùa đông tuyết rơi winter vẽ nguệch ngoạc'
        Resource id: 7343931192204463401 'Trái tim'
Hiệu ứng khung thoại text:
        Effect id: 763870 ,Resource id: 6838834573413978631 'Tiêu đề 59'
Hiệu ứng chữ nghệ thuật:
        Resource id: 7342020000812731658 'Chữ nghệ thuật đường nét vẽ tay nhiều màu'
```

Siêu dữ liệu trong đó có thể được sử dụng để thêm material tương ứng (ví dụ: thông qua tham số `resource_id` của `Sticker_segment`)

#### Thay thế material dựa trên tên
Phương pháp này sẽ thay thế chính material đó, mà không sửa đổi trực tiếp các đoạn.

> ℹ Do material có tên (mặc định là tên tệp cục bộ), việc định vị bằng phương pháp thay thế này tương đối thuận tiện.

> ℹ Do không liên quan đến việc sửa đổi phạm vi thời gian, phương pháp thay thế này **đặc biệt phù hợp với material hình ảnh**, và hầu như không gây ra vấn đề tương thích.

Lấy ví dụ về bản nháp trong [Bắt đầu nhanh](#bắt-đầu-nhanh), giả sử chúng ta muốn sử dụng material âm thanh mới, có thể:
```python
new_material = draft.Audio_material("<Đường dẫn material âm thanh mới>")
script.replace_material_by_name("audio.mp3", new_material)  # Thay thế material có tên "audio.mp3"
```

Sau khi thay thế material mới, phần được cắt xén của đoạn vẫn là 5 giây đầu của material, và âm lượng, mờ dần vào/ra, tốc độ phát, v.v. vẫn được giữ nguyên.

#### Thay thế material dựa trên đoạn
Phương pháp này sẽ thay thế material của một **đoạn cụ thể**, đồng thời có thể **chọn lại phạm vi material mà nó tham chiếu** và **co giãn đoạn trên timeline dựa trên thời lượng mới**.

> ℹ Do các đoạn không có tên, nên thường cần **dựa vào chỉ số của đoạn để định vị**.

Quá trình này gồm hai bước: **chọn track** và **thay thế material**, lấy ví dụ thay thế material âm thanh ở trên:
```python
from pyJianYingDraft import trange, Shrink_mode, Extend_mode

audio_track = script.get_imported_track(
    draft.Track_type.audio,                # Chọn track âm thanh được nhập
    #name="audio",                         # Nếu track có tên, tốt nhất nên sử dụng tên để định vị
    index=0                                # Cũng có thể dùng chỉ số để định vị, 0 biểu thị track cùng loại ở tầng thấp nhất
)

script.replace_material_by_seg(
    audio_track, 0, new_material,          # Chọn đoạn có chỉ số 0 trong audio_track, tức là đoạn đầu tiên
    #source_timerange=None,                # Nếu không chỉ định, mặc định sử dụng toàn bộ material
    source_timerange=trange("0s", "10s"),  # Ở đây chỉ định cắt xén 10 giây đầu của material (lưu ý thời lượng đoạn gốc là 5 giây)
    handle_shrink=Shrink_mode.cut_tail,    # Nếu đoạn cần rút ngắn, thực hiện bằng cách dịch chuyển điểm kết thúc về phía trước
    handle_extend=Extend_mode.push_tail    # Nếu đoạn cần kéo dài, thực hiện bằng cách dịch chuyển điểm kết thúc về phía sau, cho phép dịch chuyển các đoạn tiếp theo nếu cần
)
```

Từ ví dụ có thể thấy, phương pháp thay thế này có thể gây ra thay đổi thời lượng của đoạn, do đó có thể sử dụng các tham số `handle_shrink` và `handle_extend` để chỉ định cách xử lý khi đoạn bị rút ngắn và kéo dài.

> ℹ Khi không chỉ định rõ `handle_shrink` và `handle_extend`, cách xử lý mặc định như sau:
> - Material mới ngắn hơn material gốc, dịch chuyển điểm kết thúc của đoạn về phía trước, sao cho độ dài đoạn khớp với độ dài material mới.
> - Material mới dài hơn material gốc, cắt xén phạm vi material, giữ nguyên độ dài ban đầu của đoạn.

Danh sách các cách xử lý cụ thể có thể tham khảo định nghĩa của các lớp enum `Shrink_mode` và `Extend_mode`.

> ℹ Hiện tại, việc thay thế các đoạn có animation vào/ra kết hợp sẽ không tự động làm mới thời gian animation.

#### Thay thế nội dung đoạn text
Phương pháp này sẽ thay thế nội dung của một **đoạn text cụ thể**, nhưng giữ lại tất cả định dạng của nó.

Quá trình này cũng gồm hai bước **chọn track** và **thay thế nội dung**: trong đó "chọn track" có thể tham khảo ví dụ trong [Thay thế material dựa trên đoạn](#thay-thế-material-dựa-trên-đoạn).

Sau đây giả định chúng ta đã chọn được track text `text_track` phù hợp, thì chỉ cần:
```python
script.replace_text(
    text_track, 0,  # Chọn đoạn có chỉ số 0 trong text_track, tức là đoạn đầu tiên
    "Nội dung text mới"     # Nội dung text mới
)
```

#### Nhập các track từ bản nháp mẫu

Chức năng này sẽ sao chép theo đúng nghĩa đen các track được chỉ định từ bản nháp mẫu sang bản nháp mới, phù hợp để ghép nối nhiều bản nháp mẫu.

> ℹ **Hiện chỉ hỗ trợ nhập các track âm thanh/video/text**, phạm vi hỗ trợ sẽ tiếp tục được mở rộng trong tương lai.

> ⚠️ Phương pháp này sẽ giữ lại id của các đoạn và material của chúng, do đó **không hỗ trợ nhập cùng một track nhiều lần vào cùng một bản nháp**.

Ví dụ
```python
source_script = draft_folder.load_template("<Mẫu>")  # Tải bản nháp mẫu
target_script = draft.Script_file(1920, 1080)      # Tạo bản nháp mới

# Chọn một track text trong mẫu
text_track = script.get_imported_track(
    draft.Track_type.text,                # Chọn track text được nhập
    #name="text",                         # Nếu track có tên, tốt nhất nên sử dụng tên để định vị
    index=0                               # Cũng có thể dùng chỉ số để định vị, 0 biểu thị track cùng loại ở tầng thấp nhất
)

# Nhập track text vào bản nháp mới
target_script.import_track(
    source_script, text_track,
    offset=target_script.duration,  # Track được nhập sẽ được đặt ở cuối bản nháp mới
    new_name="imported_text",       # Tên track mới (tùy chọn)
    relative_index=1,               # Vị trí tương đối so với tất cả các track text, giá trị càng lớn càng gần tiền cảnh, có thể là số âm
)
```

### Xuất hàng loạt bản nháp
Là bước cuối cùng trong toàn bộ quy trình tự động hóa, dự án này cung cấp chức năng xuất hàng loạt bản nháp cơ bản.

> ⚠️ Các phiên bản JianYing 7+ đã ẩn các control, do đó chức năng này hiện **chỉ hỗ trợ các phiên bản JianYing 6 trở xuống**.

> ⚠️ Phần chức năng này phụ thuộc vào thư viện `uiautomation`, do đó hiện **chỉ hỗ trợ chạy trên hệ điều hành Windows**.

> ℹ Chương trình xuất sẽ đưa cửa sổ JianYing lên trên cùng, và cần điều khiển con trỏ để nhấp chuột, **khuyến nghị chạy vào thời gian rảnh/ban đêm**.

> ℹ Phần chức năng này **đã được thử nghiệm thành công trên JianYing Professional phiên bản 5.9 và 6.8**.

> ℹ Có người dùng phản ánh một số phiên bản Python (như 3.13) `uiautomation` sẽ gặp vấn đề phụ thuộc, khuyến nghị sử dụng 3.8, 3.10 hoặc 3.11, [chi tiết xem tại đây](https://github.com/GuanYixuan/pyJianYingDraft/issues/12)

> ⚠️ Vui lòng **xác nhận có quyền xuất bản nháp liên quan (không sử dụng tính năng VIP hoặc đã kích hoạt VIP)**, nếu không có thể rơi vào vòng lặp vô hạn.

Việc xuất sử dụng lớp `Jianying_controller`, cách sử dụng cụ thể như sau:

```python
import pyJianYingDraft as draft
from pyJianYingDraft import Export_resolution, Export_framerate

# Trước đó cần mở JianYing, và đang ở trang danh mục
ctrl = draft.Jianying_controller()

# Sau đó có thể xuất bản nháp có tên được chỉ định, lưu ý sau khi xuất xong video mới được cắt (đổi tên) đến vị trí được chỉ định
ctrl.export_draft("Tên bản nháp cần xuất", "<Đường dẫn xuất>")  # "Đường dẫn xuất" có thể trỏ đến thư mục hoặc trực tiếp đến tệp

# Nếu muốn điều chỉnh độ phân giải hoặc tốc độ khung hình, có thể sử dụng tham số `resolution` và `framerate`
ctrl.export_draft("Tên bản nháp cần xuất", "<Đường dẫn xuất>",
                  resolution=Export_resolution.RES_1080P,
                  framerate=Export_framerate.FR_24)
```

Lặp lại thao tác xuất đơn lẻ ở trên để thực hiện xuất hàng loạt, tương tự như mã sau:
```python
draft_names = ...
export_folder = ...
for name in draft_names:
    ctrl.export_draft(name, os.path.join(export_folder, name, ".mp4"))
```

### Thời gian và Track

#### Định dạng thời gian
**JianYing (và dự án này) đều sử dụng đơn vị micro giây để lưu trữ thời gian**, nhưng điều này không thuận tiện cho việc nhập liệu, do đó chúng tôi đã thêm một dạng thời gian "chuỗi ký tự", hầu hết các tham số thời gian đều hỗ trợ cả hai dạng này:
- Dạng micro giây: biểu thị bằng `int`, thích hợp cho tính toán
- Dạng chuỗi ký tự: biểu thị bằng `str`, ví dụ `"1.5s"`, `"1h3m12s"`, v.v., dễ nhập liệu

Nếu bạn muốn chuyển đổi rõ ràng từ dạng chuỗi ký tự sang dạng micro giây, có thể sử dụng hàm `tim`; hàm `trange` là một hàm tạo `Timerange` tiện lợi hỗ trợ nhập liệu dạng chuỗi ký tự.

> ⚠️ Lưu ý tham số thứ hai của `trange` là **thời lượng**, không phải thời điểm kết thúc.

Ví dụ:
```python
import pyJianYingDraft as draft
from pyJianYingDraft import SEC, tim, trange

# 1 giây
assert 1000000 == SEC == tim("1s") == tim("0.01666667m")

# 0~1 phút
assert draft.Timerange(0, 60*SEC) == trange("0s", "1m") == trange("0s", "0.5m30s")

# 2 giây sau khi đoạn bắt đầu
seg: draft.Video_segment
assert seg.target_timerange.start + 2*SEC == seg.target_timerange.start + tim("2s")
```

#### Cắt xén Material và Thay đổi tốc độ tổng thể
Việc cắt xén và thay đổi tốc độ đều được thiết lập khi tạo `Segment`, cụ thể là thông qua các tham số `target_timerange`, `source_timerange` và `speed`.
> ℹ Hiện tại chưa hỗ trợ thiết lập thay đổi tốc độ theo đường cong (curve).

Sau đây lấy `Video_segment` làm ví dụ, cách sử dụng `Audio_segment` tương tự:
```python
import os
import pyJianYingDraft as draft
from pyJianYingDraft import trange, SEC

# Tạo tệp nháp và ba track
script = draft.Script_file(1080, 1080)
for i in range(3, 0, -1): # Thứ tự ngược
    script.add_track(draft.Track_type.video, "%d" % i)

# Đọc material video
tutorial_asset_dir = os.path.join(os.path.dirname(__file__), 'readme_assets', 'tutorial')
mat = draft.Video_material(os.path.join(tutorial_asset_dir, 'video.mp4'))

# Thời lượng material video là 5s
print("Video material length: %f s" % (mat.duration / SEC))

# Không chỉ định source_timerange, tự động cắt xén đoạn có độ dài bằng material từ đầu
seg11 = draft.Video_segment(mat, trange("0s", "4s"))              # Tự động cắt xén 4 giây đầu của material (4s biểu thị thời lượng)
seg2  = draft.Video_segment(mat, trange("0s", "4s"), speed=1.25)  # Tự động cắt xén 4*1.25=5 giây đầu của material
seg4  = draft.Video_segment(mat, trange("0s", "3s"), speed=3.0)   # Cắt xén 3*3.0=9 giây đầu, material không đủ dài nên báo lỗi

# Chỉ định source_timerange, cắt xén đoạn được chỉ định của material, tự động thiết lập tốc độ
seg12 = draft.Video_segment(mat, trange("4s", "1s"),
                            source_timerange=trange(0, "4s"))     # Phát hết material trong 1s, tốc độ tự động thiết lập thành 5.0

# Đồng thời chỉ định source_timerange và speed, cắt xén đoạn được chỉ định của material, và ghi đè duration của target_timerange dựa trên tốc độ phát
seg3  = draft.Video_segment(mat, trange("1s", "66666h"),
                            source_timerange=trange(0, "5s"),
                            speed=2.0) # Phát hết material dài 5s với tốc độ 2x, duration của target_timerange tự động thiết lập thành 2.5s

# Thêm đoạn vào track
script.add_segment(seg11, "1").add_segment(seg12, "1")
script.add_segment(seg2, "2")
script.add_segment(seg3, "3")

# Lưu bản nháp
script.dump("*Thư mục dự án bản nháp của bạn*/draft_content.json")
```

#### Thao tác đa Track
Hiện tại phương thức `Script_file.add_track` đã hỗ trợ tạo nhiều track cùng loại, và hỗ trợ tùy chỉnh thứ tự của chúng:
```python
script.add_track(draft.Track_type.video,
                 track_name="Tiền cảnh",       # Tên track
                 relative_index=2)        # Vị trí tương đối trong tất cả các track video
script.add_track(draft.Track_type.video,
                 track_name="Hậu cảnh",
                 relative_index=1)        # Do 1<2, nên track tiền cảnh nằm ở phía trên hơn
```

Sau khi tạo nhiều track cùng loại, khi thêm đoạn phải chỉ định track đích, ví dụ:
```python
script.add_segment(video_segment, "Hậu cảnh")
```

### Điều chỉnh tổng thể Video
Mỗi đoạn video có thể được thiết lập riêng các thuộc tính cắt xén, xoay, lật, thu phóng, độ trong suốt, độ sáng, v.v., các thiết lập này được truyền qua tham số `clip_settings` trong hàm tạo `Video_segment`.
> ℹ Keyframe có độ ưu tiên cao hơn điều chỉnh tổng thể, do đó keyframe sẽ ghi đè các thiết lập tương ứng của điều chỉnh tổng thể.

Ví dụ dưới đây sẽ tạo một đoạn video, và thiết lập độ mờ của nó là 0.5, bật lật ngang:
```python
from pyJianYingDraft import Clip_settings
video_segment = draft.Video_segment(video_material,
                                    draft.Timerange(0, video_material.duration),      # Bằng độ dài material
                                    clip_settings=Clip_settings(alpha=0.5,            # Độ mờ là 0.5
                                                                flip_horizontal=True) # Bật lật ngang
                                    )
```

Giải thích chi tiết hơn về các tham số có thể xem trong hàm tạo của `Clip_settings`.

### Keyframe
Keyframe là các cặp "thời điểm-giá trị" gắn liền với **đoạn**, do đó để tạo keyframe chỉ cần chỉ định thời điểm **tương đối so với đầu đoạn**, giá trị và thuộc tính được kiểm soát trong phương thức `add_keyframe`.
> ℹ Hiện tại không hỗ trợ thiết lập keyframe cho các tham số hiệu ứng hoặc bộ lọc.

Ví dụ dưới đây thử sử dụng hai keyframe độ mờ để mô phỏng hiệu ứng mờ dần ra của video:
```python
import os
import pyJianYingDraft as draft
from pyJianYingDraft import Keyframe_property, SEC

# Tạo bản nháp và track video
script = draft.Script_file(1080, 1080)
script.add_track(draft.Track_type.video)
tutorial_asset_dir = os.path.join(os.path.dirname(__file__), 'readme_assets', 'tutorial')

# Tạo đoạn video
video_material = draft.Video_material(os.path.join(tutorial_asset_dir, 'video.mp4'))
video_segment = draft.Video_segment(video_material,
                                    draft.Timerange(0, video_material.duration)) # Bằng độ dài material

# Thêm hai keyframe độ mờ để tạo hiệu ứng mờ dần ra 1s
video_segment.add_keyframe(Keyframe_property.alpha, video_segment.duration - SEC, 1.0) # Hoàn toàn không mờ trước khi kết thúc 1s
video_segment.add_keyframe(Keyframe_property.alpha, video_segment.duration, 0.0) # Hoàn toàn mờ khi đoạn kết thúc

# Thêm đoạn vào track
script.add_segment(video_segment)

# Lưu bản nháp
script.dump("*Thư mục dự án bản nháp của bạn*/draft_content.json")
```

Ngoài `alpha`, `Keyframe_property` còn có các thuộc tính như di chuyển, xoay, thu phóng, âm lượng, độ bão hòa, v.v., tất cả chúng đều có thể thiết lập keyframe.
Keyframe của các đoạn text và sticker cũng có thể được thiết lập bằng phương pháp tương tự, nhưng lưu ý chúng chỉ hỗ trợ các thuộc tính liên quan đến vị trí và kích thước.

Đối với đoạn âm thanh, hiện chỉ có thể thiết lập keyframe cho âm lượng, lúc này bạn không cần chỉ định `Keyframe_property`.
```python
audio_segment: draft.Audio_segment
audio_segment.add_keyframe("0s", 0.6) # Âm lượng khi đoạn bắt đầu là 60%
```

### Mask
Việc thêm mask rất đơn giản: gọi phương thức `add_mask` của `Video_segment` là được:
```python
from pyJianYingDraft import Mask_type

# Thêm một mask tuyến tính, điểm trung tâm ở pixel (100, 0) của material, xoay 45 độ theo chiều kim đồng hồ
video_segment1.add_mask(Mask_type.线性, center_x=100, rotation=45)
# Thêm một mask hình tròn, đường kính chiếm 50% material
video_segment2.add_mask(Mask_type.圆形, size=0.5)
```
Trong đó:
- `Mask_type` lưu trữ các loại mask có sẵn của JianYing.
- Các tham số `center_x` và `center_y` biểu thị tọa độ điểm trung tâm của mask, có ý nghĩa tương tự như trong JianYing.
- `rotation`, `feather`, `round_corner` lần lượt biểu thị các tham số xoay, làm mờ biên, bo góc, có ý nghĩa tương tự như trong JianYing.
- Tham số `size` biểu thị "kích thước chính" của mask (chiều cao phần hiển thị của gương/đường kính hình tròn/chiều cao trái tim, v.v.) chiếm tỷ lệ bao nhiêu so với material.

Giải thích chi tiết hơn về các tham số vui lòng xem chú thích của phương thức `add_mask`.

### Hiệu ứng (Effects), Animation và Bộ lọc (Filters)
#### Loại Hiệu ứng (Effect Type)
Các loại **hiệu ứng** hiện được hỗ trợ được định nghĩa bởi các lớp enum sau:
- Âm thanh: `Audio_scene_effect_type` (Hiệu ứng âm thanh cảnh)
- Video: `Video_scene_effect_type` (Hiệu ứng hình ảnh), `Video_character_effect_type` (Hiệu ứng nhân vật)

Các loại **animation** hiện được hỗ trợ được định nghĩa bởi các lớp enum sau:
- Video: `Intro_type` (Vào), `Outro_type` (Ra), `Group_animation_type` (Animation kết hợp)
- Text: `Text_intro` (Vào), `Text_outro` (Ra), `Text_loop_anim` (Animation lặp)

Loại **bộ lọc (filter)** được lưu trữ trong `Filter_type`, chỉ có hiệu lực đối với các đoạn video.

Các thành viên trong các lớp enum ở trên (thường) được **đặt tên trực tiếp theo tên hiệu ứng hoặc bộ lọc**, và có chú thích các tham số tương ứng, ví dụ:

![Loại Hiệu ứng](readme_assets/片段特效_annotation.jpg)

Bạn cũng có thể sử dụng phương thức `from_name` để lấy một thành viên cụ thể, phương thức này bỏ qua chữ hoa/thường, dấu cách và dấu gạch dưới, ví dụ:

```python
assert Video_scene_effect_type.from_name("__全息 扫描__") == Video_scene_effect_type.全息扫描
```

#### Thêm hiệu ứng đoạn
Phương thức để thêm hiệu ứng là `segment.add_effect()`, nó nhận loại hiệu ứng và một mảng tham số, thứ tự của mảng tham số **khớp với thứ tự tham số trong chú thích của loại hiệu ứng**, nhưng **không nhất thiết phải khớp với thứ tự tham số trong JianYing**.

Ví dụ dưới đây thêm một hiệu ứng `全息扫描` (Quét Hologram) cho đoạn video, và chỉ định tham số `氛围` (Không khí) của nó là 100 (trong JianYing), các tham số khác mặc định:
```python
from pyJianYingDraft import Video_scene_effect_type

video_segment.add_effect(Video_scene_effect_type.全息扫描,
                         [None, None, 100.0]) # Không thiết lập hai tham số đầu, tham số thứ ba (Không khí) là 100, các tham số khác cũng không thiết lập
```
Phương pháp thêm hiệu ứng cho đoạn âm thanh tương tự như đoạn video.

#### Thêm bộ lọc đoạn
Phương pháp thêm bộ lọc tương tự như hiệu ứng, sử dụng phương thức `Video_segment.add_filter()`.
Khác với hiệu ứng, bộ lọc chỉ hỗ trợ một tham số "cường độ bộ lọc", và chỉ có hiệu lực khi bộ lọc được chọn có thể điều chỉnh cường độ.

```python
from pyJianYingDraft import Filter_type

video_segment1.add_filter(Filter_type.原生肤, 10)  # Thiết lập cường độ "原生肤" (Da gốc) là 10
video_segment2.add_filter(Filter_type.冰雪世界, 50)  # Thiết lập cường độ "冰雪世界" (Thế giới băng tuyết) là 50
```

#### Hiệu ứng và bộ lọc trên track độc lập
Ngoài việc thêm hiệu ứng và bộ lọc cho các đoạn video, bạn cũng có thể tạo các track hiệu ứng và track bộ lọc độc lập, và thêm các đoạn hiệu ứng và bộ lọc vào đó.

Đầu tiên sử dụng phương thức `Script_file.add_track()` để tạo track hiệu ứng hoặc track bộ lọc. Nếu cần chỉ định thứ tự, vui lòng tham khảo [Thao tác đa Track](#thao-tác-đa-track).
```python
script.add_track(draft.Track_type.effect, "my_effect")  # Tạo track hiệu ứng có tên "my_effect"
script.add_track(draft.Track_type.filter, "my_filter")  # Tạo track bộ lọc có tên "my_filter"
```

Tiếp theo có thể sử dụng các phương thức `add_effect` và `add_filter` để thêm đoạn vào các track này:
```python
from pyJianYingDraft import Video_scene_effect_type, Filter_type, trange

# Thêm một hiệu ứng "胶片闪切" (Film Flash Cut) vào track hiệu ứng, kéo dài 5 giây, và thiết lập các tham số của nó
script.add_effect(Video_scene_effect_type.胶片闪切, trange("0s", "5s"),
                  track_name="my_effect",  # Có thể bỏ qua khi chỉ có một track hiệu ứng
                  params=[50, None, 80])  # Thiết lập tốc độ là 50, giữ cường độ mặc định (100), thiết lập kết cấu là 80

# Thêm một bộ lọc "哈苏蓝" (Hasselblad Blue) vào track bộ lọc, kéo dài toàn bộ video, cường độ là 70
script.add_filter(Filter_type.哈苏蓝, trange(0, script.duration),
                  track_name="my_filter",  # Có thể bỏ qua khi chỉ có một track bộ lọc
                  intensity=70)
```

#### Thêm animation cho đoạn
Phương thức để thêm animation là `segment.add_animation()`, nó chỉ nhận một loại animation làm tham số, thời lượng của animation được quyết định bởi giá trị mặc định của nó. Nếu cần thêm nhiều animation, có thể gọi phương thức này nhiều lần cho cùng một đoạn.

> ℹ Khi thiết lập đồng thời animation lặp và animation vào/ra cho **đoạn text**, vui lòng **thêm animation vào/ra trước rồi mới thêm animation lặp**.

Sau đây là ví dụ thêm ba loại animation cho một đoạn text:
```python
from pyJianYingDraft import Text_intro, Text_outro, Text_loop_anim

text_seg.add_animation(Text_intro.复古打字机).add_animation(Text_outro.弹簧)
text_seg.add_animation(Text_loop_anim.色差故障)  # Chú ý: Animation lặp phải được thêm sau animation vào/ra
```

### Văn bản (Text) và Phụ đề (Subtitles)
#### Thêm Text
Việc thêm text tương tự như thêm đoạn video/âm thanh, chỉ cần tạo đối tượng `Text_segment` và sử dụng `add_segment` để thêm vào `Script_file`.
Các thiết lập **font chữ**, **style chữ** và **điều chỉnh hình ảnh** của nó có thể được thiết lập lần lượt thông qua các tham số `font`, `style` và `clip_settings`.

Ví dụ:
```python
import pyJianYingDraft as draft
from pyJianYingDraft import Font_type, Text_style, Clip_settings

# Text màu xanh nhạt có gạch chân, vị trí và kích thước tương tự phụ đề
seg1 = draft.Text_segment("Subtitle", trange("0s", "10s"),
                          font=Font_type.文轩体,
                          style=Text_style(size=5.0, color=(0.7, 0.7, 1.0), underline=True, align=1),
                          clip_settings=Clip_settings(transform_y=-0.8))
```

Giải thích chi tiết hơn về các tham số có thể xem trong hàm tạo của `Text_style` và `Clip_settings`.

#### Nhập Phụ đề
> ℹ Hiện chỉ hỗ trợ nhập tệp phụ đề **định dạng SRT**.

Nhập phụ đề về bản chất là tạo một loạt text dựa trên dấu thời gian và nội dung của mỗi dòng phụ đề, và thêm chúng vào track. Quá trình này được thực hiện thông qua `Script_file.import_srt`.

Ví dụ:
```python
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
```
