---
slug: "thuat-ngu-quan-ly-danh-muc"
title: "Các thuật ngữ quan trọng trong quản lý danh mục"
description: "Bộ giải thích ngắn gọn các chỉ số đánh giá hiệu quả danh mục — IRR, TWR, MWR, XIRR — hiểu nhanh để không tự ảo tưởng về lợi nhuận."
date: 2025-11-26
author: "Mage"
tags: ["đầu-tư", "danh-mục"]
featured: false
editable: false
---

## 1. **IRR (Internal Rate of Return)**  
Tỷ suất hoàn vốn nội bộ — hay nói đơn giản là **mức tăng trưởng của dòng tiền bạn ném vào danh mục**, có tính đến thời điểm nạp tiền.

- **Ý nghĩa:** đo hiệu quả dựa trên *dòng tiền thực tế* vào/ra.  
- **Ưu điểm:** phản ánh đúng hiệu quả nếu bạn nạp tiền không đều (DCA, nạp lúc thị trường crash…).  
- **Nhược điểm:** dễ bị lệch nếu danh mục còn đang chạy (chưa “kết thúc”).

**Hiểu nhanh:** IRR trả lời câu hỏi:  
> *"Tôi bỏ tiền vào từng thời điểm khác nhau. Tính gộp lại thì danh mục của tôi đang tăng theo tốc độ % bao nhiêu?"*

---

## 2. **TWR / TWRR (Time-Weighted Rate of Return)**  
Tỷ suất lợi nhuận theo thời gian — phiên bản “đo hiệu quả thuần túy của danh mục”, **không cho bạn lấy lý do vì nạp tiền sai thời điểm**.

- **Ý nghĩa:** loại bỏ ảnh hưởng từ dòng tiền vào/ra, chỉ đo hiệu quả tăng trưởng của tài sản.  
- **Ưu điểm:** so sánh portfolio với quỹ/ETF rất chính xác.  
- **Nhược:** bạn DCA sai thời điểm? Ráng chịu, TWR không quan tâm.

**Hiểu nhanh:**  
> *"Nếu tôi gửi danh mục cho một quản lý quỹ, và không nộp rút gì, thì danh mục tự nó tăng trưởng bao nhiêu phần trăm?"*

---

## 3. **MWR (Money-Weighted Return)**  
Giống IRR. Hai thằng gần như một, chỉ khác tên gọi tùy tài liệu.  
Nói vậy để bạn đỡ bị hù.

---

## 4. **XIRR**  
Phiên bản IRR dành cho dòng tiền **không đều ngày** — ví dụ: bạn nạp ngày 4, ngày 17, rút ngày 23… Excel dùng XIRR để tính.

---

## 5. **NAV (Net Asset Value)**  
Giá trị tài sản ròng của danh mục/quỹ.  
Dùng để theo dõi ETF hoặc quỹ chủ động.

---

## 6. **Cost Basis (Giá vốn)**  
Số tiền bạn đã bỏ vào trung bình.  
DCA nhiều năm ⇒ cost basis đẹp hoặc thảm hại tùy duyên.

---

## 7. **MTD / YTD (Month-to-Date / Year-to-Date)**  
Lợi nhuận tính từ đầu tháng / đầu năm tới hiện tại.

---

## 7. **Standard Deviation (Độ lệch chuẩn)**
Cách tính volatility phổ thông. Cao nghĩa là lợi nhuận lúc cao chót vót, lúc tụt như tụt mood.

---

## 8. **Max Drawdown (MDD)**
Cú rơi sâu nhất của danh mục từ đỉnh xuống đáy.  
Nó đo **nỗi đau tối đa** mà bạn từng chịu.

- MDD -10% ⇒ danh mục khá lành.  
- MDD -30% ⇒ bình thường với người chơi cổ phiếu.  
- MDD -60% ⇒ bạn nên xem lại cuộc đời.

**Hiểu nhanh:** MDD cho bạn biết lúc xấu nhất danh mục đã tát bạn mạnh đến mức nào.

---

## 9. **Calmar Ratio**
`Lợi nhuận năm / Max Drawdown`  
Dùng để xem lợi nhuận có xứng đáng với mức đau không.  
Cao ⇒ ratio đẹp.  
Thấp ⇒ danh mục trade như phê thuốc.

---

## 10. **Sharpe Ratio**
`(Lợi nhuận – Lãi suất phi rủi ro) / Độ biến động`

Nó đo xem lợi nhuận có **xứng đáng với rủi ro bạn chịu** không.

- > 1: sống được  
- > 2: ổn  
- > 3: huyền thoại (hoặc backtest lừa đảo)

Nhược điểm: Sharpe phạt cả biến động **tăng** và **giảm** như nhau — hơi ngu.

---

## 11. **Sortino Ratio**
Sharpe Ratio nhưng **không phạt biến động tăng**, chỉ phạt biến động giảm (downside deviation).  
Tức là đo rủi ro *xấu* thật sự.

Sortino > Sharpe là bình thường.  
Sortino thấp mà Sharpe cao ⇒ danh mục của bạn tăng giảm thất thường theo kiểu toxic.

---

## 12. **Semi-Variance**
Đo biến động **chỉ tính những tháng lỗ**.  
Rất hữu ích để biết danh mục có tệ thật hay chỉ thỉnh thoảng nhảy múa cho vui.

**Hiểu nhanh:** nó đo phần “đau” chứ không đo phần “phê”.

---

## 13. **Beta**
Đo danh mục chạy theo thị trường mạnh cỡ nào.

- Beta = 1 ⇒ chạy ngang thị trường  
- Beta > 1 ⇒ tâm hồn lắc mạnh hơn index  
- Beta < 1 ⇒ danh mục hiền lành  
- Beta âm ⇒ danh mục ngược đời (kiểu hedge)

---

## 14. **Alpha**
Lợi nhuận vượt benchmark (tính theo risk-adjusted).  
Nhiều người khoe alpha thực ra đang khoe... may mắn.

---

## 15. **Correlation (Tương quan)**
Đo các tài sản trong danh mục “đi chung” hay “chia tay”.

- 1.0 ⇒ dính như keo  
- 0 ⇒ chẳng liên quan  
- -1 ⇒ khi một thằng vui thì thằng kia chắn chắn buồn

Dùng để xem danh mục có thực sự đa dạng hóa hay chỉ đa dạng hóa *tên mã*.

---

## 16. **Tracking Error**
Đo xem danh mục lệch bao xa so với benchmark.  
Nếu bạn claim “đánh bại VNIndex”, tracking error thấp mà lợi nhuận thấp… thì bạn chẳng đánh bại gì cả.

---

## 17. **R-squared**
Đo xem lợi nhuận danh mục có bao nhiêu % đến từ việc chạy theo thị trường.  
R² cao: danh mục chỉ là index clone.  
R² thấp: danh mục có cá tính — tốt hay ngu tùy bro.

---

# Kết  
Nhớ đơn giản thế này:

- **IRR/MWR = đo hiệu quả đầu tư có tính đến bạn nạp rút tiền lúc nào.**  
- **TWR = đo hiệu quả thuần của danh mục, không quan tâm bạn phá game lúc nạp tiền.**
- **MDD, Vol, Sharpe/Sortino ⇒ đo rủi ro thật.**  
- **Beta, Alpha, Corr ⇒ đo danh mục có não hay không.**
---
