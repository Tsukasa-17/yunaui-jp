# YunaUI 日本語化（作業用リポジトリ）

Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui

> **YunaUI 1.1.5 から、日本語化が公式に取り込まれています。**
> 使う場合は、公式の [YunaUI](https://github.com/YunasXI/yunaui/releases) の最新版を入れてください。このリポジトリの導入は不要です。

YunaUI の日本語化と、日本語クライアントで起きる表示の不具合の修正（装備の説明やミニマップの出口名が「???」になるなど）を作り、公式に取り込んでもらうための作業場所です。

## 現在の作業版
- 公式 1.1.45 がベースです。
- 変更点: `CHANGES_JP.md`
- 公式との差分: `patch/orig1145_to_jp.patch`
- 戦闘ログの色分けのテストと解析データ取得のため、`/yui jpcf` で診断ログ（jpdebug.log）を出力できます（もう一度打つとオフ）。

## 開発者向け
- 公式ファイル（`yunaui.lua`・`dps.lua`・`equip.lua`）への変更は `-- [JP]` 印の行だけです。日本語化の処理は `yunaui_jp.lua`、辞書は `yunaui_lang.lua` にあります。
- 同梱しているのは上記のファイルと LICENSE / NOTICE / README / CHANGES_JP だけです。公式のほかのファイル・画像・フォントは含みません。

## クレジット・ライセンス
- 原作: **YunaUI** by Yunas — https://github.com/YunasXI/yunaui
- 日本語化（訳・辞書・yunaui_jp.lua）: Tsukasa
- ライセンス: GNU GPL v3.0（`LICENSE`）に、YunaUI の追加条項（GPL-3.0 第7条(b)：作者表示の保持）が付きます（`NOTICE`）。改変・再配布するときは、NOTICE と著作権表示・クレジットを残し、README に `Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui` と書いてください。

## 免責事項
- 非公式の作業用リポジトリです。株式会社スクウェア・エニックス、CatsEyeXI の運営とは関係ありません。
- FINAL FANTASY XI © SQUARE ENIX CO., LTD. All Rights Reserved. ゲーム内の名称はゲームのデータから表示しており、その権利は株式会社スクウェア・エニックスにあります。
- 無保証です。利用によって起きたいかなる損害にも責任を負いません。

## 更新履歴
- 2026-11-09: 公式 YunaUI 1.1.45 ベースに更新。
  - チャットのフォント設定（日本語フォント・英字フォント・日英別の文字サイズ）を廃止し、言語タブにフォント選択（プルダウン）を追加。YunaUI の fonts フォルダのフォント（.ttf / .otf / .ttc）と Windows のメイリオから選べます（変更後は /addon reload yunaui で反映）。
  - 「チャットの縁取りと影」をチャットタブへ移動。縁取りの太さを追加し、縁取り・影の設定を公式のスライダー・スイッチ・プルダウンと「元に戻す」（Ctrl+Z）に対応。
  - 1.1.42〜1.1.45 の新しい文字列を翻訳（ヴォイドレッド、戦闘不能中のロット・パス不可、レアの所持品をロットしない通知など）。
- 1.1.4j: 公式 YunaUI 1.1.4 に対応。新しい設定（BARS の「HPバー」オン/オフ）を翻訳。
- 1.1.3j: 最初の公開版（公式 YunaUI 1.1.3 用）。
