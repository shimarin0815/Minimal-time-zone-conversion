# (オフィス向け) ミニマル・タイムゾーン変換
> JST（日本時間）を入力するだけで、海外の主要都市の時間をアナログ時計で瞬時に確認できるシングルページアプリケーションです。

海外の取引先や支社とのミーティング時間を調整する際に、「日本時間のXX時は、現地だと何時何日？」という問題を素早く解決するために作成されました。
``

---

## ✨ 主な機能

* **JST（日本時間）入力:** 基準となる日本時間を簡単に入力できます。（デフォルトで現在時刻が自動設定されます）
* **瞬時な時間変換:** 入力と同時に、登録された全都市の時間がリアルタイムで更新されます。
* **美しいアナログ時計UI:** 各都市の時間を、視覚的に理解しやすいアナログ時計で表示します。
* **日付の自動判定:** 変換後の時間が「昨日」「同日」「翌日」なのかを自動で計算し、表示します。

## 🚀 使い方

このアプリケーションは、単一のHTMLファイルで動作します。
サーバーへのデプロイや複雑なインストール作業は一切不要です。

1.  フォルダ内にある `index.html` ファイルを見つけます。
2.  `index.html` ファイルをダブルクリックして、お使いのWebブラウザ（Google Chrome, Edge, Safariなど）で開きます。
3.  JSTの時間を変更すると、各都市の時計が連動して動きます。

## 🔧 カスタマイズ方法 (都市の追加・変更)

表示する都市は、`index.html` ファイルを直接編集するだけで簡単に追加・変更できます。

1.  `index.html` をVS Codeなどのテキストエディタで開きます。
2.  ファイルの下部にある `<script>` タグ内に、`const cities = [...]` という設定箇所があります。

    ```javascript
    // 1. 表示したい都市をリストにする
    // name: 表示名
    // tz: IANAタイムゾーン名 (これで世界中の時間を正確に計算できる)
    // id: HTMLで識別するための名前 (なんでも良いが、他と被らないように)
    const cities = [
        { name: 'ロンドン', tz: 'Europe/London', id: 'ldn' },
        { name: 'ニューヨーク', tz: 'America/New_York', id: 'nyc' },
        { name: 'サンフランシスコ', tz: 'America/Los_Angeles', id: 'sfo' },
    ];
    ```

3.  この配列に、新しい都市のオブジェクト `{ name: '表示名', tz: 'IANAタイムゾーン名', id: 'ユニークなID' }` を追加します。

    **例：シドニー (オーストラリア) を追加する場合**

    ```javascript
    const cities = [
        { name: 'ロンドン', tz: 'Europe/London', id: 'ldn' },
        { name: 'ニューヨーク', tz: 'America/New_York', id: 'nyc' },
        { name: 'サンフランシスコ', tz: 'America/Los_Angeles', id: 'sfo' },
        { name: 'シドニー', tz: 'Australia/Sydney', id: 'syd' } // ← この行を追加
    ];
    ```

    > **ヒント:** `tz` に指定する「IANAタイムゾーン名」は、Wikipediaの [tz database time zonesの一覧](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) などで確認できます。（例: `America/Chicago`, `Asia/Singapore` など）

4.  ファイルを上書き保存し、ブラウザをリロード（再読み込み）すると、新しい都市の時計が追加されています。

## 🛠️ 技術スタック

* **HTML**
* **CSS** (Pure CSS / No Frameworks)
* **JavaScript** (Vanilla JS / No Libraries)

このアプリケーションは、依存関係のない単一ファイルで完結しているため、管理が容易です。
---
