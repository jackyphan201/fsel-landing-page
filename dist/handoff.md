# FSEL Learning Universe — Bàn giao high-fidelity
Ngày: 10/11/2026. Trạng thái: bản thiết kế HTML tương tác để review; chưa phải bản production đã duyệt.

## Đầu ra
- `dist/index.html`: trang chủ ưu tiên người học.
- `dist/campus.html`: trang Campus responsive.
- `dist/review.html`: thư viện 30 ảnh trạng thái (15 trạng thái × desktop/mobile).
- `evidence/index-*.png`, `evidence/campus-*.png`: ảnh toàn trang ở 1440, 768, 390, 320px.
- `dist/assets/asset-manifest.json`: nguồn tài nguyên được dùng.
- `dist/content.js`: nội dung học liệu, mốc câu hỏi, đáp án và phản hồi mẫu.

## Nguồn và các quyết định thiết kế
- Người dùng xác nhận Campus đã triển khai; đồng thời cho phép dùng nội dung trên thiết kế khi hỏi về clip, bộ Speaking và frame Campus. Xác nhận này không xác định frame nào khớp phiên bản live.
- DESIGN.md trong thư mục cung cấp: palette #1A2237 / #242F4B / #2970FF, Inter, H1 60/36, H2 36/28, các trạng thái demo và cấu trúc trang.
- Skill áp dụng: design-taste-frontend (Taste), Sites; ImageGen được cân nhắc theo yêu cầu nhưng không gọi vì có artwork gốc đủ dùng. Không dùng skill wireframe.
- Direction One motif, seed 1418627434: các hành tinh Learn là dấu ấn xuyên suốt, đưa người học từ hình ảnh khám phá đến thao tác học. Giữ logo, icon, artwork và raster UI gốc. Ngoại lệ Taste: bo góc 8/16px, palette và typography theo DESIGN.md; screenshot sản phẩm giữ màu nguồn; không dùng ảnh stock hay số liệu mới.
- Hero dùng Learn course panel gốc, không dựng lại dashboard. Marketing layout được thiết kế mới.

## Tài nguyên đã thu thập
Website https://fsel.edu.vn/ được đọc bằng Scrapling ngày 10/11/2026. Đã tải các ảnh được tham chiếu trực tiếp trên trang chủ, ảnh nền CSS, font và SVG inline; không crawl tài khoản LMS hay mọi trang bên ngoài. Danh mục đầy đủ ở evidence/web-assets.json.
Logo trắng lấy nguyên SVG footer của website. Thông tin liên hệ và trích lời Quang T. lấy từ trang public. Câu trích trong bản dựng là đoạn rút gọn; xem website snapshot trong evidence/website.html để đối chiếu toàn văn. Không thêm đối tác, kết quả học hoặc số lượng người dùng.
Artwork và raster UI trích trực tiếp từ archive .fig; không coi embedded image là bằng chứng phiên bản live. Manifest ghi archive và hash gốc. Các tệp tham chiếu không bị chỉnh sửa.

## Demo Video — giới hạn cần biết
Có đủ luồng: ban đầu, phát, dừng ở câu hỏi, đúng/sai, lời giải, tiếp tục, hoàn thành, làm lại, lỗi tải.
Chưa tìm được clip bài giảng gốc gắn đúng câu hỏi trong tài nguyên đã kiểm tra. File MP4 hiện tại là cảnh tĩnh 12 giây mã hóa từ screenshot `lesson-screen.png`, không âm thanh, không giả giọng giáo viên. Nhãn trên demo nêu rõ cảnh thiết kế minh họa. Câu hỏi lựa chọn được biên soạn từ mô tả hiển thị của Unit 1 “Nice to meet you”: giới thiệu bản thân với thông tin cá nhân và nghề nghiệp. Đây KHÔNG phải bộ câu hỏi–đáp án gốc của video FSEL.
Cần thay bằng clip, phụ đề, mốc tương tác và câu hỏi/đáp án cùng bài được duyệt để đáp ứng đầy đủ yêu cầu Video Lesson thực.

## Demo Speaking
Đề `Let’s talk about your hometown or village.` và bản chép lời `I grew up in the vibrant town of Avalor...` được tìm trong LMS_WEB_V1.2.2.fig. Phản hồi FC được trích từ cụm nội dung thiết kế lân cận cùng bản chép lời (evidence/fig-strings.txt, vùng 384071–384230). Không hiển thị điểm số, không tự đánh giá phát âm, không gán phản hồi mẫu cho bản ghi người dùng. Chưa có audio bài mẫu gốc; hiện khám phá bằng bản chép lời và mở từng phần nhận xét.
Thu âm bằng MediaRecorder, có thời gian, dừng, phát lại qua audio controls, xóa, thu lại; quyền mic bị từ chối/thiết bị không hỗ trợ vẫn xem được mẫu. Giới hạn ghi 3 phút. Tắt mic khi dừng, chuyển demo/chế độ, ẩn tab hoặc rời trang. Thu âm chỉ giữ trong bộ nhớ phiên, không gửi máy chủ. Object URL được thu hồi khi xóa/rời demo.
Phản hồi trích trong thiết kế mang tính band descriptor chung; chưa xác minh là kết quả đánh giá thật của chính đoạn audio. Cần bộ audio + transcript + phản hồi đã liên kết để nghiệm thu nội dung hoàn chỉnh.

## Campus
Copy chỉ giới hạn ba nhóm nêu trong DESIGN.md: chương trình học, quản lý lớp, theo dõi tiến độ theo vai trò. Không tuyên bố mọi trường cùng cấu hình.
Màn hình đang dùng là raster có thật từ các bộ Learn, LMS_WEB_V1.2.2 và LMS Admin Update 1.1. CHƯA xác minh đây là frame Campus đang triển khai. Riêng ảnh báo cáo Admin là báo cáo đầu vào theo địa bàn, chưa đủ chứng minh báo cáo Campus. Do đó trang Campus là bản bố cục review; cần thay/đối chiếu frame Campus đúng phiên bản trước khi công bố marketing. Các số trong screenshot là dữ liệu minh họa của nguồn, không phải kết quả FSEL.
Form có kiểm tra trường bắt buộc/email, mở email để người dùng tự gửi tới địa chỉ liên hệ public. Không gửi tự động, không hiển thị tiếp nhận thành công. Chưa có API tiếp nhận lead.
Dungeon of Doom không xuất hiện: có file concept nhưng không có xác nhận trạng thái công bố.

## Danh sách còn thiếu / chưa xác minh
1. Clip Video Lesson gốc, phụ đề, câu hỏi/đáp án và mốc tương tác đã duyệt.
2. Audio bài nói mẫu, transcript và phản hồi tương ứng có thể xác minh.
3. Frame Campus live desktop/mobile và dữ liệu demo được phép dùng; mapping vai trò–tính năng.
4. Endpoint tiếp nhận form và xác nhận tiếp nhận thực tế, nếu cần gửi ngay trên web.
5. URL chính sách hiện hành: không tự tạo đường dẫn chính sách. Footer hiện chưa có liên kết chính sách.
6. Quyền tái sử dụng testimonial public trong bản marketing mới cần chủ sở hữu nội dung xác nhận nếu xuất bản rộng rãi.
7. Brand phê duyệt theme tối; DESIGN.md ghi theme là đề xuất.

## Kiểm tra đã thực hiện
Chrome qua Playwright: trang chủ/Campus ở 320, 390, 768, 1440px; không tràn ngang, không pageerror. Thu–dừng–phát lại–xóa đã chạy với thiết bị microphone mô phỏng của Chrome. Đây không phải kiểm thử microphone vật lý hay Safari/iOS.
Đã tạo ảnh các trạng thái Video và Speaking. Các nhánh xin quyền/từ chối/không hỗ trợ được mô phỏng trong kiểm thử, không phải thay đổi quyền thiết bị người dùng.
Taste Inspector đã chạy; vòng đầu báo ít motion, headline tablet và cảnh báo tương phản nút. Đã bổ sung chuyển động theo section có reduced-motion và điều chỉnh tablet. Vòng Inspector cuối hết lỗi headline tablet nhưng vẫn đánh dấu still-page (3 motion được bộ đo nhận diện); không báo PASS toàn bộ. Màu nút #2970FF + trắng theo DESIGN.md có tương phản xấp xỉ 4.3:1: chưa đạt 4.5:1 cho nhãn 16px; giữ token yêu cầu, cần quyết định token trước production.
Đánh giá hình ảnh nội bộ: bố cục rõ, artwork đúng thương hiệu; nội dung screenshot trên mobile nhỏ nên hỗ trợ mở ảnh đầy đủ. Chưa coi đây là human Design Approval, QA approval hay chứng nhận accessibility.

## Chạy tại máy
Phục vụ thư mục dist qua localhost hoặc HTTPS để microphone hoạt động. Mở file trực tiếp có thể không hỗ trợ quyền mic trên một số trình duyệt.

Đánh giá hình ảnh nội bộ theo rubric Taste: Design 7/10, Usability 7/10, Creativity 7/10, Content 5/10; tổng 6.8/10 (40/30/20/10). Giới hạn chính là học liệu thay thế và chưa xác minh frame Campus, không phải thang nghiệm thu FSEL.
