# YunaUI 日本語化 1.1.3j（非公式）

Based on YunaUI by Yunas - https://github.com/YunasXI/yunaui

YunaUI 1.1.3（Ashita v4 / VanaCore 用 HUD アドオン）の画面を日本語で表示するための、非公式の日本語化パッチです。
日本語訳と辞書: Tsukasa

## バージョン
- 1.1.3j（公式 YunaUI 1.1.3 用）。パッチを当てると、設定パネルの下部のバージョン表示が `v1.1.3j` になります。

## 同梱ファイル
| ファイル | 内容 |
|---|---|
| `yunaui_jp.lua` | 日本語化の処理（フォント・名前・設定画面・コマンド） |
| `yunaui_lang.lua` | 日本語辞書 |
| `orig113_to_jp.patch` | 公式 1.1.3 の `yunaui.lua` に当てる差分（追加行のみ＋バージョン表記） |
| `README.md` / `CHANGES_JP.md` | 説明 / 改変の記録 |
| `LICENSE` / `NOTICE` | GPL-3.0 全文 / YunaUI 公式の NOTICE（原文のまま） |

YunaUI 本体（`yunaui.lua` ほか）・画像・地図・フォント・音は同梱していません。公式から入手してください。

## 入れ方
1. 公式の YunaUI **1.1.3** を `Ashita/addons/yunaui/` に入れる（https://github.com/YunasXI/yunaui ）。
2. `yunaui_jp.lua` と `yunaui_lang.lua` を同じフォルダにコピーする。
3. `yunaui.lua` にパッチを当てる。次のどれか1つで構いません。
   - Git がある場合（`addons/yunaui/` で実行）: `git apply orig113_to_jp.patch`
   - patch コマンドの場合: `patch -p1 < orig113_to_jp.patch`
   - 手で直す場合: 下の一覧の行を同じ場所に追加する（行番号はパッチ適用後のもの）。
4. ゲーム内で `/addon reload yunaui`（または `/addon load yunaui`）。

手で追加する行（適用後の行番号）:
```
3: -- Modified by Tsukasa, 2026-11-01: Japanese localization ([JP] hook lines; see yunaui_jp.lua / CHANGES_JP.md).
6: addon.version = '1.1.3j';   -- [JP]
38: local JP = require('yunaui_jp'); JP.boot();   -- [JP]
157: t = JP.msg(t);   -- [JP]
234: JP.wrap_dl(DL);   -- [JP]
270: t = JP.t(t);   -- [JP]
371: size = JP.psize(size, cfg);   -- [JP]
379: size = JP.fsize(size, cfg);   -- [JP]
511: str = JP.t(str); if JP.mb(str) then return JP.spaced(dl, x, y, str, col, gap, DL.T); end   -- [JP]
521: str = JP.t(str); if JP.mb(str) then return JP.spaced_w(str, gap); end   -- [JP]
11698: name = JP.item_name(r, name);   -- [JP]
12719: JP.timers(TIMERS);   -- [JP]
13183: JP.loot(C);   -- [JP]
13652: if JP.mb(str) then return px + JP.spaced(dl, px, py, str, col, sp, function(d, a, b, c, t) text(d, a, b, t, c); end) + sp; end   -- [JP]
13751: nm = JP.fit(nm, room, 1 * sc);   -- [JP]
15305: JP.panel_wfs(C, pf, cfg);   -- [JP]
15360: JP.size_ui(row_slider, cfg);   -- [JP]
15394: JP.settings_ui(section, accent_button, hint);   -- [JP]
15906: JP.fonts(YUI_FONTS);   -- [JP]
17098: nm = JP.exit_name(YMAP.exit_names, ex[7], nm);   -- [JP]
20230: if JP.command(sub, args, msg) then return; end   -- [JP]
```
※ 6行目は既存の `addon.version = '1.1.3';` を置き換えます。それ以外はすべて追加行です。

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

## 更新履歴（開発メモ）
- j3: 日本語表示時は `YUI_JP=true` を強制（公式の日本語クライアント判定が外れる環境で、アイテム名・エリア名・チャットが「?」になる問題の修正）。
- j4: 装備ツールチップ・ミニマップ出口名の「???」を修正（日本語クライアントでは公式が使う `Name[1]` / `GetString` が ??? を返すため、yunaui_jp.lua で AshitaCore を薄く代理し `Name[0]`・言語0の文字列に差し替え。本体の名前取得コードは無変更）。一般設定の「テキストサイズのみ」スライダーを復活（本体に2行フック追加）。言語選択ボタンを等幅3分割にして「日本語」が切れて見えない問題を修正。
- j5: 装備名・ミニマップ出口名を 102j と同じ方式で修正。原因は「公式は Name[1] / GetString の生文字列（Shift_JIS）を UTF-8 変換せず描いていた」ことと「出口名は ??? を一度キャッシュすると二度と取り直さない」こと。j4 の AshitaCore 代理は廃止。
  - `equipped()` 内: `name = JP.item_name(r, name);` … Name[0] 優先 → YUI_U8
  - ミニマップ出口: `nm = JP.exit_name(YMAP.exit_names, ex[7], nm);` … zones.names → ZoneName → GetZoneName → vana.ashita.string(言語0) → 前後空白除去 → YUI_U8。??? はキャッシュせず次フレームで再試行

- j6: 装備ツールチップとミニマップ出口名が、日本語の字形を持たない既定フォントで描かれていた（ImGui は字形が無い文字を「?」で描く）。102j はそこで fonts.chat を PushFont していた。yunaui_jp.lua で YUI_TIP と DL.T を包み、日本語を含む文字列を描くとき、今のフォントに日本語が無ければ合成済みフォント（fonts.chat）に切り替える。本体の変更なし。
  - デバッグ: `/yui jpdebug` で ON/OFF（既定 OFF）。ON のあいだ、出口名・装備名・使用フォントを id ごとに1回だけ `[YUI-JPDBG]` としてチャットに出す。

- j7: 日本語表示のときは英数字も含めて全部メイリオで描く（102j と同じ）。Segoe UI・チャット用フォントは meiryo.ttc、Bahnschrift（見出し）は meiryob.ttc に置き換える。日本語の合成もメイリオ優先（無ければ游ゴシック→MSゴシック）。yunaui_jp.lua の AddFontFromFileTTF フック内で置き換えるので本体の変更なし。英語表示は公式のまま。

- j8: 「テキストサイズのみ」（旧: フォントサイズのみ）を設定メニューの文字にも適用。公式の設定メニューは sized() を通らず push_font(フォント, 18×パネル倍率) で直接描いていたため倍率が掛かっていなかった。本体に2行追加: push_font 先頭 `size = JP.psize(size, cfg);`、設定ウィンドウの C.wfs 設定直後 `JP.panel_wfs(C, pf, cfg);`（古い ImGui 用）。sized() 経由は二重に掛けない。日本語表示のときだけ有効。

- j9: チャットの日本語（本文・「戦闘」タブ・戦闘ログ表示）だけ小さくなる問題を修正。原因は j6 の日本語フォント切り替えで、窓の倍率込みの文字サイズを PushFont に渡していたため倍率が二重に掛かっていた（新 ImGui は 0=現在サイズを渡す、古い ImGui は倍率を補正）。また日本語の合成サイズを元フォントと同じにし、YunaUI のフォント（sized 含む）なら切り替え自体をしないようにした。本体の変更なし。

- j9-113: 公式 1.1.3 に移植。新規の設定項目・説明 20件を翻訳。
- j10-113: ミニマップ窓の文字だけ 1.3 倍（minimap_text_scale）。
- j11-113: トレジャープールの名前を日本語化（フック3行追加）。
- 1.1.3j: 公開用にまとめた版（バージョン表示 v1.1.3j、ライセンス表記を追加）。
