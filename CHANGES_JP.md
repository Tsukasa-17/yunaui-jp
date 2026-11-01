# 改変の記録（GPL-3.0 第5条(a) にもとづく表示）

- 2026-11-01 Tsukasa: 公式 YunaUI 1.1.4 に対応した「1.1.4j」。
  - `yunaui.lua` への変更内容は 1.1.3j と同じ（改変の記録1行、`addon.version` を `1.1.4j` に変更、`-- [JP]` 印の追加行19行）。パッチは `orig114_to_jp.patch`。
  - `yunaui_lang.lua`: 1.1.4 の新しい文字列（HPバーのオン/オフと説明）などを追加。

- 2026-11-01 Tsukasa: YunaUI 1.1.3（Yunas 作）を日本語化した版「1.1.3j」。
  - `yunaui.lua`: 先頭に改変の記録を1行追加し、`addon.version` を `1.1.3j` に変更。`-- [JP]` 印の追加行19行（下記 README.md 参照）。元の著作権表示・作者表示はすべてそのまま残しています。
  - 新規ファイル `yunaui_jp.lua`（日本語化の処理）と `yunaui_lang.lua`（日本語辞書）。
  - 公式のほかのファイル（equip.lua、exits.lua、maps3d/、画像、フォント、音など）は変更・同梱していません。
- NOTICE は YunaUI 公式のものをそのまま収録しています。
