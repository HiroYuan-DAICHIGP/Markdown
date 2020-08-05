Libraryに依存しない軽量Date-Picker「flatpickr」の備忘録
===

flatpickrとは？
---

>flatpickrは軽量かつ高機能なdate-pickerです。
>無駄がなく、UX-drivenで拡張可能であり、どのライブラリにも依存しません。 ミニマルなUIで多くのテーマがあります。 豊富なAPIとイベントはどんな環境にも適しています。
>"無駄がない"とは、小さいサイズでよりよいパフォーマンスを生むことを意味しており、 カレンダーに8つのライブラリをロードする必要が無いことを示しています。

参考サイト
- [公式サイト](https://flatpickr.js.org/)
- [公式サイトの日本語ローカライゼーション](https://tr.you84815.space/flatpickr/localization.html)

導入
---
flatpickrの導入は、サイトから直接ダウンロードする他にnpmとbowerにも対応しています。

### npm
```npm
npm install flatpickr
```

### bower
```bower
bower install flatpickr-calendar
```

### 非モジュール環境
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
<script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
```

利用方法
---
環境によってはimportやrequireが必要になります
```js
// commonjs
const flatpickr = require("flatpickr");

// es modules are recommended, if available, especially for typescript
import flatpickr from "flatpickr";
```

### 一番基本のPicker
```html
// HTML
<input class="flatpickr" type="text" placeholder="Select Date.." readonly="readonly">
<script type="text/javascript">flatpickr('.flatpickr');</script>
```

何も設定をしない場合は上記で動作します。
jsの関数flatpickrの第2引数に、設定を記述することができます。

```rb
// JavaScript
const config = {
  enableTime: true,
  dateFormat: "Y-m-d H:i",
}
flatpickr('.flatpickr', config);
```

enableTimeのプロパティをtrueに設定することで、カレンダーから時間の選択も可能になります。