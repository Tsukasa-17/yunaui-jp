# YunaUI 日本語化 1.1.4j（非公式）

> **お知らせ：YunaUI 1.1.5 から、日本語化が公式に取り込まれました。**
> これから使う場合は、公式の [YunaUI 1.1.5 以降](https://github.com/YunasXI/yunaui/releases/tag/1.1.5) を入れてください。このリポジトリの導入は不要です。
> このリポジトリは、今後の翻訳の追加や、公式へ取り込んでもらう修正を作るための作業場所として残しています。
> 現在の作業版は公式 1.1.21 がベースです（変更点は `CHANGES_JP.md`、公式との差分は `patch/orig1121_to_jp.patch`）。
> 戦闘ログの色分けのテストと解析データ取得のため、`/yui jpcf` で診断ログ（jpdebug.log）を出力できます（もう一度打つとオフ）。
> 以下は 1.1.4j までの古い説明です。


Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui

YunaUI 1.1.4（Ashita v4 / VanaCore 用 HUD アドオン）の画面を日本語で表示するための、非公式の日本語化パッチです。
日本語訳と辞書: Tsukasa

## バージョン
- 1.1.4j（公式 YunaUI 1.1.4 用）。パッチを当てると、設定パネルの下部のバージョン表示が `v1.1.4j` になります。

## 入れ方
1. 公式の YunaUI **1.1.4** を入れる（https://github.com/YunasXI/yunaui ）。
2. [v1.1.4j のリリース](https://github.com/Tsukasa-17/yunaui-jp/releases/tag/v1.1.4j)から `yunaui_jp_1.1.4j.zip` をダウンロードして展開する。
3. 展開して出てきたファイルを、公式の yunaui フォルダ（例: `addons/vanacore/yunaui`）にまるごとコピーして上書きする。
4. ゲームを再起動する。日本語にならないときは、チャットで `/yui lang ja` と入力する。

## できること
- 設定画面・各ウィンドウの表示を日本語化（辞書に無い文字列は英語のまま）。
- アイテム名・装備名・ミニマップの出口名・トレジャープールの名前をゲームの日本語名で表示。
- 日本語表示のときはメイリオで描画（Windows に入っているフォントを参照します）。
- ミニマップ内の文字だけ拡大（既定 1.3 倍）。
- 英語表示のときは公式と同じ動作です。

## コマンド
- `/yui lang auto|ja|en` 表示言語（auto＝クライアントの言語に合わせる）

## 設定
`addons/yunaui/yunaui_jp_settings.lua`（設定画面からも変更できます）:
```
return { ui_lang = 'auto', font_scale = 1.00, minimap_text_scale = 1.30 };
```
- `font_scale`: 文字サイズだけの倍率（日本語表示のとき）
- `minimap_text_scale`: ミニマップ窓の文字の倍率（0.5〜2.0、1.0 で公式と同じ）

## クレジット・ライセンス
- 原作: **YunaUI** by Yunas — https://github.com/YunasXI/yunaui
- 日本語化（訳・辞書・yunaui_jp.lua）: Tsukasa
- ライセンス: GNU GPL v3.0（`LICENSE`）に、YunaUI の追加条項（GPL-3.0 第7条(b)：作者表示の保持）が付きます（`NOTICE`）。改変・再配布するときは、NOTICE と著作権表示・クレジットを残し、README に `Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui` と書いてください。
- 改変の記録: `CHANGES_JP.md`

## 免責事項
- 本パッチは非公式です。YunaUI の作者（Yunas）、株式会社スクウェア・エニックス、CatsEyeXI の運営とは関係ありません。
- FINAL FANTASY XI © SQUARE ENIX CO., LTD. All Rights Reserved. ゲーム内の名称はゲームのデータから表示しており、その権利は株式会社スクウェア・エニックスにあります。
- フォント（メイリオ等）は同梱していません。OS に入っているものを参照します。
- アドオンの利用ルールはサーバーごとに違います。各自で確認してください（CatsEyeXI では、承認リストにないアドオンは使う前に審査が必要です）。
- 無保証です。利用によって起きたいかなる損害にも責任を負いません。

## 開発者向け
- 公式から変更したのは `yunaui.lua` だけです（`-- [JP]` 印の行を追加し、バージョン表記を変更）。日本語化の処理は `yunaui_jp.lua`、辞書は `yunaui_lang.lua` にあります。
- 公式 1.1.4 との差分は `patch/orig114_to_jp.patch` です（`git apply patch/orig114_to_jp.patch`）。追加行の一覧は `CHANGES_JP.md` を参照してください。
- 同梱しているのは上記のファイルと LICENSE / NOTICE / README / CHANGES_JP だけです。公式のほかのファイル・画像・フォント（メイリオ等）は含みません。

## 更新履歴
- 1.1.4j: 公式 YunaUI 1.1.4 に対応。新しい設定（BARS の「HPバー」オン/オフ）を翻訳。
- 1.1.3j: 最初の公開版（公式 YunaUI 1.1.3 用）。
