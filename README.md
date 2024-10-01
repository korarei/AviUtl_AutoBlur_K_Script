# AviUtl_AutoBlur_K_Script

自動で方向ブラー、放射ブラー、回転ブラーをかけるスクリプト

[Download](https://github.com/korarei/AviUtl_AutoBlur_K_Script/releases)


## はじめに

自動的に回転ブラーをかけるためには、モジュールが必要です。以下の回転ブラースクリプトをダウンロードしてください。

- 回転ブラースクリプト (ティム氏)

    [Download](https://tim3.web.fc2.com/sidx.htm)

- RotBlur_M (Mr-Ojii氏)

    [Download](https://github.com/Mr-Ojii/AviUtl-RotBlur_M-Script/releases)

ダウンロードしたフォルダ内にある、.dllファイルまたは.luaファイルを使用します。何も設定していない状態でこれらのモジュールが読み込まれる場所は以下の通りです。もし、この場所以外に配置する場合、設定ダイアログの"Mod Path"でパスを指定してください。

    - exedit.aufと同階層
    - scriptフォルダ直下
    - AutoBlur_K.anmと同階層

## 導入・削除
### 導入
1. 同梱の.anmファイルをscriptフォルダまたはその子フォルダに入れる。

### 削除
1. 同梱の.anmファイルを導入したフォルダから出す。

## トラックバー
2つ存在する
- sAngle (Shutter Angle)

    ブラーの長さを指定する。

- sPhase (Shutter Phase)

    ブラーの位置を指定する。

## その他の設定項目
1. Display Original

    ブラー前のオブジェクトを表示する。

2. Consider Script

    スクリプトによる変化を考慮する。

3. 各ブラーの有効無効

    略称の意味は以下の通りです。

    - Dir Blur : 方向ブラー
    - Rad Blur : 放射ブラー
    - Rot Blur : 回転ブラー

4. Relative Path

    回転ブラーモジュールのパスを相対パスにするかどうかを指定します。基準はAutoBlur_Kのある場所です。

5. Mod Path

    回転ブラーモジュールのパスを指定します。

    例
        - ..\\T_RotBlur\\?.dll
   
           autoblur_kのあるフォルダより1階層上のフォルダ内にあるT_RotBlurフォルダの中にあるdllファイルという意味。
   
        - ..\\rotblur_m\\?.lua
   
           autoblur_kのあるフォルダより1階層上のフォルダ内にあるrotblur_mフォルダの中にあるluaファイルという意味。

7. Param
    回転ブラーモジュールに渡すパラメータです。意味は以下の通りです。

    1. モジュールタイプ

        1がティム氏の回転ブラー、2がrotblur_mです。

    - ティム氏の回転ブラーの場合

        2. 角度解像度ダウン
        3. 高精度表示
        4. 高精度出力

    - RotBlur_Mの場合

        2. quality
        3. reload

8. Keep Size

    サイズ固定するかどうか指定します。

9. Amount

    ブラーの長さの微調整用

10. v0

    初速度を指定します。ここをうまく設定すると0フレーム目にもブラーがかかります。

    1. 自動計算の有効無効
       
        trueで有効、falseで無効です。
        
        この機能はconsider scriptが無効の場合に使えます。

        0, 1, 2フレーム目のデータをもとに加速度を計算し、そこから-1フレームから0フレーム間の変位を計算します。
    
    2. x方向の初速度 [px/s]
    3. y方向の初速度 [px/s]
    4. zoom方向の初速度 [%/s] (z方向は s1 = s0 * 1024 / (1024 + z) のように遠近法を用いた見かけのサイズの変化量になります。)
    5. rz方向の初速度 [deg/s]

## LICENSE
LICENSEファイルに記載

## Change Log 
- **v1.1.0**
  - RotBlur_Mに対応
  - v0の指定機能を追加
  - z方向の計算間違いの修正
  - マジックナンバーの削除
  - コードの整理

- **v1.0.0**
  - release
