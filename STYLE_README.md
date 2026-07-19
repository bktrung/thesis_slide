# Chuẩn trình bày slide bảo vệ khóa luận

Tài liệu này rút ra từ việc phân tích slide mẫu `[KL_2025_TTNT012]_Slide.pdf` (khóa luận
cùng bộ môn, cùng giảng viên hướng dẫn), bổ sung các điều chỉnh cho khóa luận ViNeoBERT.
Mọi quy tắc dưới đây được cài đặt sẵn trong `slides/vineo-theme.sty`.

---

## 1. Bố cục tổng thể

| Thành phần | Quy định |
|---|---|
| Tỷ lệ khung | 16:9 (`aspectratio=169`) — rộng hơn slide mẫu (4:3), đủ chỗ cho bảng kết quả nhiều cột |
| Thanh bên trái | **Không dùng.** Toàn bộ bề ngang trang dành cho nội dung |
| Logo | Góc trên phải mỗi slide có tiêu đề |
| Chân trang | tên chương hiện tại \| ngày bảo vệ \| số trang / tổng số |
| Tiêu đề khung | **Xanh navy đậm** (thay cho xám đen của slide mẫu) |
| Cỡ chữ nền | 10pt |

**Đường kẻ dưới tiêu đề phải ngắn hơn khung chữ.** Logo nằm ở góc trên phải, ngay dải
tiêu đề, nên đường kẻ phải dừng lại trước logo (hiện chừa $\approx$0,9cm). Lưu ý kỹ
thuật: `\hrule` **không** tuân theo `rightskip` — nó luôn kéo hết bề ngang hộp và sẽ cắt
ngang qua logo. Vì vậy đường kẻ được vẽ bằng `\vrule` có bề rộng chỉ định, đặt trong
`\hbox` kèm `\nointerlineskip` (dùng `\rule` trần sẽ mở một đoạn văn mới và đẩy toàn bộ
nội dung slide xuống, gây tràn đáy).

**Vì sao bỏ thanh bên.** Slide mẫu dành 2cm mỗi trang cho thanh điều hướng — khoảng 14%
bề ngang, trên *mọi* slide. Bỏ nó, bề rộng khung chữ tăng từ 369,89pt lên **415,41pt**
($\approx$14,60cm), đủ để nâng cỡ chữ nền từ 9pt lên 10pt mà mật độ nội dung vẫn giữ
nguyên (tỷ lệ lấp đầy trung vị 86%). Vai trò định vị của thanh bên được thay bằng hai
thứ rẻ hơn về diện tích: **tên chương ở chân trang** (không tốn diện tích nội dung) và
**slide mục lục nhắc lại trước mỗi chương**.

### Mạch trình bày

Theo đúng mạch của slide mẫu — đây là mạch quen thuộc với hội đồng:

```
Trang bìa → Mục lục đầy đủ → [Mục lục nhắc lại ở đầu mỗi chương → nội dung chương]×5
          → Kết luận → Lời cảm ơn → Tài liệu tham khảo
```

Slide mục lục nhắc lại giữa các chương làm mờ các chương khác và tô đậm chương sắp trình
bày. Mục lục được đánh số (1, 2, 3.1, 3.2 . . . ) để hội đồng luôn biết đang ở đâu trong
35 phút trình bày — đây là vai trò định vị mà thanh bên từng đảm nhiệm.

---

## 2. Bảng màu

Bảng màu xoay quanh họ xanh dương chuyên nghiệp, một điểm nhấn đỏ để làm nổi số liệu.
Toàn bộ màu chữ đạt độ tương phản ≥ 7:1 trên nền trắng (chuẩn WCAG AAA), đọc được cả khi
máy chiếu bị nhạt màu.

| Vai trò | Màu | Mã | Dùng ở đâu |
|---|---|---|---|
| Tiêu đề khung, cấu trúc | Navy đậm | `#1F3864` | Frame title, chân trang, tiêu đề bảng |
| Nhấn phụ | Xanh thép | `#2E74B5` | Subsection, dấu đầu dòng, liên kết, caption |
| Nền khối / nền tiêu đề bảng | Xanh nhạt | `#DEEBF7` | Block, hàng tiêu đề bảng, ô nhấn mạnh |
| Chữ thường | Đen nhạt | `#212121` | Toàn bộ nội dung |
| Nhấn mạnh / số liệu chính | Đỏ trầm | `#B02A2A` | Kết quả tốt nhất, con số quyết định |
| Trích dẫn | Xám xanh | `#5B7A9D` | `[Tác giả, năm]` trên slide |

**Quy tắc dùng màu:** mỗi slide dùng tối đa **hai** màu nhấn. Màu đỏ chỉ dành cho con số
quan trọng nhất của slide đó — dùng nhiều thì mất tác dụng.

---

## 3. Quy tắc chống khoảng trắng thừa

Slide mẫu có nhiều trang chỉ 3–4 dòng chữ nằm lọt thỏm giữa trang. Các quy tắc sau bắt buộc:

1. **Không căn giữa theo chiều dọc.** Nội dung bám mép trên (`t` option), phần thừa dồn
   xuống dưới thay vì tạo hai khoảng trống trên–dưới.
2. **Mỗi slide nội dung chiếm ít nhất ~65% chiều cao khung.** Nếu không đủ, hoặc gộp với
   slide kế tiếp, hoặc bổ sung một hình minh họa / ví dụ cụ thể.
   *Ngoại lệ*: slide mục lục nhắc lại giữa chương và slide cảm ơn — các slide này thưa là
   có chủ đích, vì chúng đóng vai trò ngắt nhịp chứ không truyền tải nội dung.
3. **Slide có hình thì dùng hai cột**: hình một bên, 3–4 gạch đầu dòng diễn giải bên kia.
   Hình đứng một mình giữa trang trắng là dấu hiệu slide chưa xong.
4. **Slide công thức phải kèm một dòng "diễn giải"** bằng lời thường ngay dưới công thức.
5. Bảng rộng dùng `\small`/`\footnotesize` và kéo hết chiều ngang khung, không để lề thừa.
6. **Bảng đặt trong cột phải hẹp hơn cột đó.** Bề rộng khung chữ là 415,41pt
   ($\approx$14,6cm); một cột `0.56\textwidth` chỉ còn $\approx$8,2cm, mà tổng bề rộng bảng
   phải cộng thêm `2\tabcolsep` ($\approx$0,42cm) cho mỗi khe giữa cột. Bảng rộng quá sẽ
   *tràn sang cột bên cạnh và bị chữ của cột đó đè lên* — lỗi này không tạo cảnh báo
   nào từ LaTeX, chỉ phát hiện được khi xem hình.
7. **Cột bảng dùng `L{…}` (canh trái) thay cho `p{…}`.** Cột `p{}` canh đều hai bên nên ở
   bề rộng hẹp TeX giãn khoảng trắng thành các khe rất rõ giữa các từ.

---

## 4. Cách viết chữ trên slide

Hội đồng phản biện có thể **không cùng hướng nghiên cứu**. Vì vậy:

- **Không viết câu văn dài.** Gạch đầu dòng là cụm danh từ, tối đa 2 dòng.
- **Mỗi slide một ý.** Tiêu đề slide chính là ý đó, viết thành câu khẳng định được.
- **Giải thích thuật ngữ ngay lần đầu**: viết tiếng Việt kèm tiếng Anh trong ngoặc, ví dụ
  "mất thông tin (catastrophic forgetting)", "tập điểm neo (anchor set)".
- **Giữ nguyên tên riêng kỹ thuật**: NeoBERT, SALT, RoPE, SwiGLU, embedding, tokenizer.
- **Dẫn dắt bằng chữ in đậm**: "Vấn đề:", "Ý tưởng:", "Kết quả:" ở đầu nhóm gạch đầu dòng.
  Nếu dòng dẫn dắt đứng trên một **đoạn văn** (không phải danh sách), dùng `\lead{…}` chứ
  đừng dùng `\textbf{…}`: beamer đặt `\parskip` bằng 0 nên hai đoạn liền nhau dính vào
  nhau, đọc như một khối. Cũng tránh để đoạn ngay sau đó mở đầu bằng chữ in đậm — hai
  cụm in đậm liên tiếp vẫn đọc như một tiêu đề dù đã có khoảng cách.
- **Ưu tiên trực giác hơn hình thức toán học.** Công thức chỉ đưa lên slide khi nó *là*
  đóng góp; còn lại thay bằng sơ đồ hoặc một câu mô tả.

---

## 5. Trích dẫn — bắt buộc

Mọi mô hình, tập dữ liệu, kỹ thuật hoặc con số **không phải của nhóm** đều phải kèm trích
dẫn ngay trên slide, dạng `[Tác giả và cộng sự, năm]` in màu xám xanh:

> **RoPE**: mã hóa vị trí bằng phép quay [Su và cộng sự, 2021]

Lý do: hội đồng đánh giá cao slide phân tách rõ phần kế thừa và phần tự làm. Trích dẫn
trên slide cũng giúp trả lời nhanh câu hỏi "cái này lấy từ đâu?".

Cuối bộ slide có 2–3 trang tài liệu tham khảo đầy đủ (không tính vào 30–35 slide chính).

---

## 6. Hình và bảng

- Mọi hình/bảng đều **đánh số và có chú thích** (`Hình N:` / `Bảng N:`), chú thích màu
  xanh thép, đặt dưới hình.
- **Sơ đồ vẽ lại bằng TikZ** để đồng bộ màu với slide và nét luôn sắc.
- **Biểu đồ thực nghiệm trích thẳng từ PDF khóa luận** bằng `pdfimages`, lấy đúng đối
  tượng ảnh nhúng bên trong (`slides/figures/fig-*.png`, 189–577 ppi). Sáu biểu đồ này
  vốn đã là ảnh raster do matplotlib sinh ra trong khóa luận, nên trích đối tượng gốc cho
  chất lượng cao nhất có thể — tốt hơn cắt trang PDF, vì không phải ước lượng vùng cắt và
  không mất thêm độ phân giải.
- Sơ đồ TikZ có nguy cơ vượt bề ngang được bọc trong
  `\resizebox{\ifdim\width>\linewidth\linewidth\else\width\fi}{!}{…}` — chỉ thu nhỏ khi
  thực sự cần, không phóng to.
- Trong bảng kết quả, **in đậm** giá trị tốt nhất mỗi hàng; hàng của mô hình đề xuất tô
  nền xanh nhạt để mắt bắt ngay.

---

## 7. Kiểm tra trước khi bảo vệ

- [ ] Số slide nội dung nằm trong khoảng 30–35 (chưa tính tài liệu tham khảo).
- [ ] Không slide nào trống quá 1/3 khung.
- [ ] Mọi kỹ thuật/số liệu kế thừa đều có trích dẫn trên slide.
- [ ] Bảng đọc được khi chiếu — thử thu nhỏ PDF còn 50% vẫn phải đọc được.
- [ ] Tiêu đề khung màu navy, không phải xám đen.
- [ ] Biên dịch sạch: không thiếu tham chiếu, không lỗi tràn khung.
