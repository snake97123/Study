# Appstoreにアプリを登録する方法をまとめる。
仕事で調べる必要があったので、わかったことをまとめていくようにする。

## アプリのスクリーンショットを撮影する。
アプリをシュミレーターに起動した後にcommand + Sでスクリーンショットを撮影することが可能になる。<br>

##### スクリーンショットの使用は決まっているため以下のサイトを参考にすること。
[Apple スクリーンショットの機能要件](https://help.apple.com/app-store-connect/?lang=ja-jp#/devd274dd925)

## App IDを作成する。

## アプリをApp Store Connectに登録する。
App Store ConnectとはApp Storeで販売するAppを管理するためのWebベースのツールセットのことである。<br>

1. AppStore Connectを開く
2. 左上の方にあるAppの隣の＋ボタンを押す。
3. 各項目の登録する。SKUに関しては用語集を参照する。

## アプリの一般情報の編集をする。
1. アプリのスクリーンショットの設定
2. Promotional Textの設定　
3. Descriptionの設定　アプリの説明
4. Keywordsの設定　AppStoreの検索キーワード
5. Support URLの入力。デベロッパWebサイトで表示されるページのURLを記載する。
6. Copyrightを記載する。著作権
7. Routing App Coverage Fileを添付する。　地図検索などのアプリなどを登録する際に必要になっているみたい。

## App Informationを設定する。
1. Content Rightsの設定　第三者の著作物を使用しているかしていないかで選択するものが変わる。
2. Age Ratingの設定　質問に答えていくことで対象年齢が設定されていく。
3. Category アプリのカテゴリーを設定します。

## Pricing and Availabilityを設定する。
1. Price Scheduleの設定　アプリの価格の設定を行う。
2. Tax Category 税金のカテゴリを設定できるみたい。詳しくは以下を参照<br>
[税金カテゴリの設定がApp Store Connectで利用可能に](https://developer.apple.com/jp/news/?id=2bbbudbw)
3. Pre-Orders 予約注文を設定できるみたい。
4. Availabilityの設定　アプリを使用できる地域を設定するみたい。
5. App Distribution Methods アプリの配布方法を設定することができるみたい。
## App Privacyを設定する

## アプリをアップロードする。

## アプリのビルド情報を編集する。

## アプリを申請する。

## 用語集
・SKU Stock keeping unitの略。決済などの管理に利用される番号。特に規則はない。ユーザーから見えることもないので、バンドルIDと一緒でも問題はない様子。<br>
・Promotional Text iOS11以降の端末で、App Storeの説明の上に表示されるテキスト。170文字。アプリの提出・審査なしで利用できるようです。<br>