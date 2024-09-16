# AviUtl_AutoBlur_K_Script
自動で方向ブラー、放射ブラー、回転ブラーをかけるスクリプト

## はじめに
ティム氏の回転ブラーを導入すると回転ブラーを自動的にかけれるようになる。

[Download](https://tim3.web.fc2.com/sidx.htm)

## 導入・削除
### 導入
1. 同梱の.anmファイルをscriptフォルダまたはその子フォルダに入れる。
### 削除
1. 同梱の.anmファイルを導入したフォルダから出す。

## パラメータ
2つ存在する
- sAngle (Shutter Angle)
ブラーの長さを指定する
- sPhase (Shutter Phase)
ブラーの位置を指定する

## その他の設定項目
1. Display Original
  - ブラー前のオブジェクトを表示する
2. Consider Script
  - スクリプトによる変化を考慮する
3. 各ブラーの有効無効
4. Relative Path
  - 回転ブラーモジュールのパスを相対パスにするかどうか
5. Dll Path
  - 回転ブラーモジュールのパス
6. Param
  - 回転ブラーモジュールに渡すパラメータ
  - 最初から順に、タイプ（現在使用していない）、角度解像度ダウン、高精度表示、高精度出力
7. Keep Size
  - サイズ固定するかどうか
8. Length
  - ブラーの長さの微調整用

## LICENSE
LICENSEファイルに記載

## Change Log 
- **v1.0.0**
  - release
