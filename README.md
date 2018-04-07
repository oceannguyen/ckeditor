# CKFinder Tool

## Cấu hình resources' public URL và thư mục upload

Trong file ```config.xml```:

* **baseURL**: Chỉ định địa chỉ URL công bố resources xử lý bởi CKFinder
Ví dụ: project ```lapmangcapquang``` khi deploy có port là 8080, và muốn dùng địa chỉ ```http://localhost:8080/lapmangcapquang/public/resources/``` để lấy files từ server, ta khái báo như sau:

```
<baseURL>/CKFinderJava/userfiles/</baseURL>
```

* **baseDir**: Chỉ định đường dẫn thư mục local được CKFinder sử dụng để tìm/xử lý các files trên server. Folder đó phải được gán đầy đủ quyền cho CKFinder xử lý files. Ví dụ khai báo như sau:

```
E:/study/workspace/lapmangcapquang/target/classes/static/uploadmedia/
```

> Lưu ý: Ký tự ```/``` cuối cần phải chỉ định.


## JavaScript Integration

* Bước 1 Tải CKFinder

```javascript
<head>
	...
	<script type="text/javascript" src="/ckfinder/ckfinder.js"></script>
</head>
```

[CKFinder APIs](https://docs-old.ckeditor.com/ckfinder_2.x_api/)

* Bước 2 Tạo CKFinder instance

```javascript
<script type="text/javascript">
var finder = new CKFinder();
finder.basePath = '/ckfinder/';
finder.create();
</script>
```

Để mở popup, sử dụng method sau:
```javascript
<script type="text/javascript">
var finder = new CKFinder();
finder.basePath = '/ckfinder/';
finder.popup();
</script>
```

Thảm khảo sample mẫu ở ```_samples/popup.html```

**Cấu hình tùy chọn**

Có thể cấu hình CKFinder trong file ```config.js``` (chi tiết tại [JavaScript Configuration](https://docs-old.ckeditor.com/CKFinder_2.x/Developers_Guide/Java/Configuration#JavaScript_Configuration)). Ngoài ra ta có thể cấu hình của object như sau:

```javascript
<script type="text/javascript">
var finder = new CKFinder();
finder.basePath = '/ckfinder/';
// Setting custom width and user language.
finder.create({ width : 700, language : 'de' });
</script>
```

hoặc:

```javascript
<script type="text/javascript">
var finder = new CKFinder();
finder.basePath = '/ckfinder/';
// Setting custom width and user language.
finder.width = 700;
finder.language = 'de';
finder.create();
</script>
```
