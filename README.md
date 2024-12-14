# AviUtl_AutoBlur_K_Script

自動で方向ブラー、放射ブラー、回転ブラーをかけるスクリプト

[Download](https://github.com/korarei/AviUtl_AutoBlur_K_Script/releases)


## はじめに

自動的に回転ブラーをかけるためには、モジュールが必要です。以下の回転ブラースクリプトをダウンロードしてください。

- 回転ブラースクリプト (ティム氏)

    [Download](https://tim3.web.fc2.com/sidx.htm)

    動作確認バージョン: V2 (更新日: 2023/10/28)

- RotBlur_M (Mr-Ojii氏)

    [Download](https://github.com/Mr-Ojii/AviUtl-RotBlur_M-Script/releases)

    動作確認バージョン: r13

ダウンロードしたフォルダ内にある、 `.dll` ファイルまたは `.lua` ファイルを使用します。何も設定していない状態でこれらのモジュールが読み込まれる場所は以下の通りです。もし、この場所以外に配置する場合、設定ダイアログの"Mod Path"でパスを指定してください。

- exedit.aufと同階層   
- scriptフォルダ直下 
- AutoBlur_K.anmと同階層


## 導入・削除

### 導入

1. 同梱の `.anm` ファイルを `script` フォルダまたはその子フォルダに入れる。

### 削除

1. 同梱の `.anm` ファイルを導入したフォルダから出す。


## 使用方法

### トラックバー

- sAngle (Shutter Angle)

  ブラーの長さを指定する。

- sPhase (Shutter Phase)

  ブラーの位置を指定する。

### その他の設定項目

- Display Original

  ブラー前のオブジェクトを表示する。

- Consider Script

  スクリプトによる変化を考慮する。

- 各ブラーの有効無効

  略称の意味は以下の通りです。

  - Dir Blur: 方向ブラー
  - Rad Blur: 放射ブラー
  - Rot Blur: 回転ブラー

- Relative Path

  回転ブラーモジュールのパスを相対パスにするかどうかを指定します。基準はAutoBlur_Kのある場所です。

- Mod Path

  回転ブラーモジュールのパスを指定します。

  例
   
  - ..\\T_RotBlur\\?.dll
   
    autoblur_kのあるフォルダより1階層上のフォルダ内にあるT_RotBlurフォルダの中にあるdllファイルという意味。
   
  - ..\\rotblur_m\\?.lua
   
    autoblur_kのあるフォルダより1階層上のフォルダ内にあるrotblur_mフォルダの中にあるluaファイルという意味。

- Param
  回転ブラーモジュールに渡すパラメータです。意味は以下の通りです。

  `{type, param1, param2, ...}`

  - type: モジュールタイプ
   
    指定する数字によってモジュールを切り替えます。1がティム氏の回転ブラー、2がrotblur_mです。

    - ティム氏の回転ブラーの場合

      - param1: 角度解像度ダウン
      
      - param2: 高精度表示
      
      - param3: 高精度出力

    - RotBlur_Mの場合

      - param1: quality
      
      - param2: reload

- Keep Size

  サイズ固定するかどうか指定します。

- Amount

  ブラーの長さの微調整用。

  ここで設定したブラー長さはシャッターアングルでの長さ調整とは異なり、シャッターフェーズなどによる位置調整の影響を受けません。

- v0

  初速度を指定します。ここをうまく設定すると0フレーム目にもブラーがかかります。2番目以降は自動計算が使えない場合のみ使用します。

  `{auto_calc, vx, vy, vzoom, vrz}`

  - auto_calc: 自動計算の有効無効
       
    trueで有効、falseで無効です。
        
    この自動計算機能はconsider scriptが無効の場合に使えます。

    0, 1, 2フレーム目のデータをもとに加速度を計算し、そこから-1フレームから0フレーム間の変位を計算します。
    
  - vx: x方向の初速度 [px/s]
  - vy: y方向の初速度 [px/s]
  - vzoom: zoom方向の初速度 [%/s] (z方向は s1 = s0 *  `焦点距離`  / ( `焦点距離`  + z) のように遠近法を用いた見かけのサイズの変化量になります。)
  - vrz: rz方向の初速度 [deg/s]

## LICENSE
LICENSEファイルに記載

## Change Log
- **v1.1.2**
  - シャドー (カメラ制御)下において同一フレームにてグローバル空間に保存するテーブルが書き換わる問題への対策
  - カメラ制御下ではカメラの焦点距離でブラー計算を行うように変更
  - 初速度計算でsPhaseの影響を受けていなかった問題を解決

- **v1.1.1**
  - グローバル空間に保存するテーブルにレイヤー情報を追加

- **v1.1.0**
  - RotBlur_Mに対応
  - v0の指定機能を追加
  - z方向の計算間違いの修正
  - マジックナンバーの削除
  - コードの整理

- **v1.0.0**
  - release
