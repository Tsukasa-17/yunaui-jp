# YunaUI 日本語化 1.1.4j（非公式）

Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui

YunaUI 1.1.4（Ashita v4 / VanaCore 用 HUD アドオン）の画面を日本語で表示するための、非公式の日本語化パッチです。
日本語訳と辞書: Tsukasa

## バージョン
- 1.1.4j（公式 YunaUI 1.1.4 用）。パッチを当てると、設定パネルの下部のバージョン表示が `v1.1.4j` になります。

## 同梱ファイル
| ファイル | 内容 |
|---|---|
| `yunaui_jp.lua` | 日本語化の処理（フォント・名前・設定画面・コマンド） |
| `yunaui_lang.lua` | 日本語辞書 |
| `orig114_to_jp.patch` | 公式 1.1.4 の `yunaui.lua` に当てる差分（追加行のみ＋バージョン表記） |
| `README.md` / `CHANGES_JP.md` | 説明 / 改変の記録 |
| `LICENSE` / `NOTICE` | GPL-3.0 全文 / YunaUI 公式の NOTICE（原文のまま） |

YunaUI 本体（`yunaui.lua` ほか）・画像・地図・フォント・音は同梱していません。公式から入手してください。

## 入れ方
1. 公式の YunaUI **1.1.4** を `Ashita/addons/yunaui/` に入れる（https://github.com/YunasXI/yunaui ）。
2. `yunaui_jp.lua` と `yunaui_lang.lua` を同じフォルダにコピーする。
3. `yunaui.lua` にパッチを当てる。次のどれか1つで構いません。
   - Git がある場合（`addons/yunaui/` で実行）: `git apply orig114_to_jp.patch`
   - patch コマンドの場合: `patch -p1 < orig114_to_jp.patch`
   - 手で直す場合: 下の一覧の行を同じ場所に追加する（行番号はパッチ適用後のもの）。
4. ゲーム内で `/addon reload yunaui`（または `/addon load yunaui`）。

手で追加する行（適用後の行番号）:
```
3: -- Modified by Tsukasa, 2026-11-01: Japanese localization ([JP] hook lines; see yunaui_jp.lua / CHANGES_JP.md).
6: addon.version = '1.1.4j';   -- [JP]
38: local JP = require('yunaui_jp'); JP.boot();   -- [JP]
157: t = JP.msg(t);   -- [JP]
234: JP.wrap_dl(DL);   -- [JP]
270: t = JP.t(t);   -- [JP]
371: size = JP.psize(size, cfg);   -- [JP]
379: size = JP.fsize(size, cfg);   -- [JP]
511: str = JP.t(str); if JP.mb(str) then return JP.spaced(dl, x, y, str, col, gap, DL.T); end   -- [JP]
521: str = JP.t(str); if JP.mb(str) then return JP.spaced_w(str, gap); end   -- [JP]
11698: name = JP.item_name(r, name);   -- [JP]
12723: JP.timers(TIMERS);   -- [JP]
13187: JP.loot(C);   -- [JP]
13656: if JP.mb(str) then return px + JP.spaced(dl, px, py, str, col, sp, function(d, a, b, c, t) text(d, a, b, t, c); end) + sp; end   -- [JP]
13755: nm = JP.fit(nm, room, 1 * sc);   -- [JP]
15309: JP.panel_wfs(C, pf, cfg);   -- [JP]
15364: JP.size_ui(row_slider, cfg);   -- [JP]
15398: JP.settings_ui(section, accent_button, hint);   -- [JP]
15910: JP.fonts(YUI_FONTS);   -- [JP]
17102: nm = JP.exit_name(YMAP.exit_names, ex[7], nm);   -- [JP]
20234: if JP.command(sub, args, msg) then return; end   -- [JP]
```
※ 6行目は既存の `addon.version = '1.1.4';` を置き換えます。それ以外はすべて追加行です。

## できること
- 設定画面・各ウィンドウの表示を日本語化（辞書に無い文字列は英語のまま）。
- アイテム名・装備名・ミニマップの出口名・トレジャープールの名前をゲームの日本語名で表示。
- 日本語表示のときはメイリオで描画（Windows に入っているフォントを参照します）。
- ミニマップ内の文字だけ拡大（既定 1.3 倍）。
- 英語表示のときは公式と同じ動作です。

## コマンド
- `/yui lang auto|ja|en` 表示言語（auto＝クライアントの言語に合わせる）
- `/yui jpdebug` 日本語化のデバッグ表示 ON/OFF
- `/yui iconcheck` トレジャープールのアイコン診断（英語表示でも使えます）

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

## 更新履歴
- 1.1.4j: 公式 YunaUI 1.1.4 に対応。新しい設定（BARS の「HPバー」オン/オフ）を翻訳。
- 1.1.3j: 最初の公開版（公式 YunaUI 1.1.3 用）。
