# Palmslave ZMK config (nice!nano V2 互換機向け・未検証)

元定義: qmk_firmware/keyboards/takashicompany/palmslave/keyboard.json
(Palmslave: CC-BY-SA-4.0 / takashicompany)

## 使い方
1. このフォルダ一式を自分のGitHubリポジトリにpush（Actionsが有効であること）
2. Actionsのビルド結果から firmware.zip をダウンロード
3. palmslave_left-nice_nano_v2-zmk.uf2  → 左手
   palmslave_right-nice_nano_v2-zmk.uf2 → 右手
   （リセットをダブルタップ → USBドライブとして出てくるのでUF2をコピー）
4. 接続がおかしいときは settings_reset を両手に書いてから、左右のUF2を書き直す

## ビルドが通らないとき
- ZMK Studioまわり(&studio_unlock, snippet, cmake-args)で失敗する場合は、
  build.yaml の左手の snippet / cmake-args と keymap の &studio_unlock を削除
- physical_layouts関連で失敗する場合は palmslave.dtsi の physical_layout0 と
  chosen の zmk,physical-layout を削除（キーマップ自体は動きます）
