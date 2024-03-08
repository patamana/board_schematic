# パタマナボード 回路図・kicadデータ
パタマナボードの回路図やkicadデータです。

## パタマナボードの概要
XIAO用キーボード基板<br>
XIAOは無線接続ができて便利だが、端子数が少ない<br>
→シフトレジスタでスイッチを読み込むことで解決<br>
74HC165 を4つ実装済みで

**XIAOの3ピンで32キーの読み取りに対応**

I2CによるOLED制御<br>
TRRSジャックによる左右通信<br>
充電用のPHコネクタやスライドスイッチが実装可能

### シフトレジスタの概要
XIAOのD1,D2,D3ピンが74HC165のLD,CK,QHに配線されています。<br>
LDをLowにすることでシフトレジスタにロードされ、<br>
QHからSW0のHIGE/LOWが出力されます。<br>
CKが立ち上がるたびに出力信号がSW1,SW2...とシフトされていきます。


詳しい利用方法は[patamana.com](https://patamana.com)を参照してください。

Arduino IDE を用いる場合は、[patamana/keybard_firmware](https://github.com/patamana/keyboard_firmware)のコードを参考にしてください。


