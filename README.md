# Tahoma di Asino
 Repository hướng zẫn cách zùng mã **Javascript** dể hiển thị phông ***Tahoma*** mới cho các trang web ngoài **Quán Bựa**, trong dự án **Vietnamese writing problems: Chữ giùn cảitạo** của **An Hoàng Trung Tướng**, aka. **Zì Giùn**.

>Chi bộ sẽ không cần cài dặt phông mới mà vẫn nghe dược cách mạng trong lòng dịch. Chỉ cần copy zòng text **<1kB** mang di muôn nơi.


>Trình zuyệt máy tính hỗ trợ:
>- Thủ công dùng **Console**: TẤT CẢ. Có thể gặp bug `Paste` với một số phiên bản `Firefox`, hãy cập nhật `Firefox` mới.
>- Thủ công dùng **Bookmarklet**: `>IE9, Chrome, Opera, Cốc cốc, Firefox, Tor...`.
>- Tự động: `Chrome, Opera, Cốc cốc, Firefox, Tor,...`

***Tahoma*** mới chỉ dược Zì cung cấp **Regular**, các ký tự ở dạng Thin **Bold** _Italic_ **_Bold Italic_** nghe sẽ không dẹp cho lắm, zù vẫn theo qui chuẩn.

>Chú ý: Có thể gặp lỗi `Content Security Policy` trên một số trang do thiếu thẻ `<meta/>`. Dang khắc phục...

___
## Hướng dẫn sử zụng mã Javascript dể thay dổi phông trên mọi website trần gian

Hiện tại có 2 cách, tự dộng và thủ công.

### 1. Bookmarklet (thủ công)
Sử zụng doạn mã sau (copy):
```javascript
javascript:var fontLink="https://raw.githubusercontent.com/antoniushoang/fonts/master/TAHOMA.",css="@font-face {font-family:Tahoma;src: url('"+fontLink+"eot');src:url('"+fontLink+"eot?#iefix') format('embedded-opentype'),url('"+fontLink+"woff') format('woff');font-weight:normal;font-style:normal;}*{font-family: Tahoma !important;}",head=document.head||document.getElementsByTagName("head")[0],style=document.createElement("style");style.type="text/css",style.styleSheet?style.styleSheet.cssText=css:style.appendChild(document.createTextNode(css)),head.appendChild(style);
```
- Chi bộ có thể nhấn `F12` trên trình duyệt để mở `Inspect`, chuyển sang tab `Console`, `Paste` doạn mã, `Enter` là có thể chạy được ngay.

Hoặc:

- Trên thanh **Bookmark** của **Chrome** hoặc **Firefox**, chuột phải và tạo trang mới (**Add page...**) với **URL** là doạn mã ở trên (paste).
- Sau dó lưu lại (**Save**). Dây chính là một **Bookmarklet**.
- Mở một lá cải Zùn bất kì. Nhấn vào **Bookmarklet** vừa tạo và hưởng thụ thành quả.

>[VIDEO HƯỚNG ZẪN](https://www.youtube.com/watch?v=W0ZEWSDHjG4) `bật Subtitle (CC) dể hiểu rõ hơn`.

___

### 2. Tampermonkey (tự dộng)
[Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo) sử dụng cho **Chrome CốcCốc Opera**, **add-on** tương tự trên **Firefox** có tên [Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/).

Mời cài dặt. Sau day sẽ chỉ có hướng zẫn cho **Tampermonkey**, thế mới thích.

Sử zụng doạn mã sau (copy):
```javascript
// ==UserScript==
// @name         TalaScript
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  VJK
// @author       Bú zù
// @include        http://*/*
// @include        https://*/*
// @grant        none
// ==/UserScript==

(function() {
    var fontLink = "https://raw.githubusercontent.com/antoniushoang/fonts/master/TAHOMA.",
	css = "@font-face {font-family:Tahoma;src: url('" +
        fontLink + "eot');src:url('" +
        fontLink + "eot?#iefix') format('embedded-opentype'),url('" +
        fontLink + "woff') format('woff');font-weight:normal;font-style:normal;}" + 
        "*{font-family: Tahoma !important;}",
        head = document.head || document.getElementsByTagName("head")[0],
        style = document.createElement("style");
    style.type = "text/css";
    if (style.styleSheet){
        style.styleSheet.cssText = css;
    } else {
        style.appendChild(document.createTextNode(css));
    }
    head.appendChild(style);
})();

```
- Trên **Chrome**, click chuột vào icon của **Tampermonkey**, chọn thêm một script mới (**Add new script...**)
- Thay thế bằng doạn mã ở trên, sau đó lưu lại (icon :floppy_disk:). Tiếp tục hưởng thụ thành quả khi mở một trang lá cải Zùn bất kì.

>[VIDEO HƯỚNG ZẪN](https://www.youtube.com/watch?v=pTwvUxymOnw) `bật Subtitle (CC) dể hiểu rõ hơn`.

Chi bộ lưu í, doạn mã `// @include http://*/*` hoặc `//@match  http://*/*` giúp cài dặt các website sẽ dược áp zụng, ở đây là toàn bộ các trang `http`.

Nếu chỉ muốn sử zụng tại **Faceboook**, hãy chuyển sang `// @include https://facebook.com/*` và xóa các zòng `@include` - `@match` còn lại.

___

##Quán Bựa - An Hoàng Trung Tướng
 
 Vietnamese writing problems: Chữ giùn cảitạo
 
 [#1](http://an-hoang-trung-tuong-2014.blogspot.com/2016/07/vietnamese-writing-problems-chu-giun.html)
 [#2](http://an-hoang-trung-tuong-2014.blogspot.com/2016/08/vietnamese-writing-problems-chu-giun.html)
 
 Comics: vietnamese new writing concept
 
 [#1](http://an-hoang-trung-tuong-2014.blogspot.com/2016/08/comics-vietnamese-new-writing-concept-1.html)
 [#2](http://an-hoang-trung-tuong-2014.blogspot.com/2016/09/comics-vietnamese-new-writing-concept-2.html)
 [#3](http://an-hoang-trung-tuong-2014.blogspot.com/2016/09/comics-vietnamese-new-writing-concept-3.html)
 [#4](http://an-hoang-trung-tuong-2014.blogspot.com/2016/09/comics-vietnamese-new-writing-concept-4.html)
