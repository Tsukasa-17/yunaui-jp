# 改変の記録（GPL-3.0 第5条(a) にもとづく表示）

- 2026-11-01 Tsukasa: 公式 YunaUI 1.1.4 に対応した「1.1.4j」。
  - `yunaui.lua` への変更内容は 1.1.3j と同じ（改変の記録1行、`addon.version` を `1.1.4j` に変更、`-- [JP]` 印の追加行19行）。パッチは `patch/orig114_to_jp.patch`。
  - `yunaui_lang.lua`: 1.1.4 の新しい文字列（HPバーのオン/オフと説明）などを追加。

- 2026-11-01 Tsukasa: YunaUI 1.1.3（Yunas 作）を日本語化した版「1.1.3j」。
  - `yunaui.lua`: 先頭に改変の記録を1行追加し、`addon.version` を `1.1.3j` に変更。`-- [JP]` 印の追加行19行。元の著作権表示・作者表示はすべてそのまま残しています。
  - 新規ファイル `yunaui_jp.lua`（日本語化の処理）と `yunaui_lang.lua`（日本語辞書）。
  - 公式のほかのファイル（equip.lua、exits.lua、maps3d/、画像、フォント、音など）は変更・同梱していません。
- NOTICE は YunaUI 公式のものをそのまま収録しています。

## 1.1.4j の追加行一覧（`yunaui.lua`）
適用後の行番号:
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
