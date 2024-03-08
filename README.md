# パタマナボード 回路図・kicadデータ
パタマナボードの回路図やkicadデータです。

## パタマナボードの概要
XIAO用キーボード基板です。<br>
XIAOは無線接続ができて便利ですが、端子数が少なく、マトリクス構造にしてもOLEDを制御するpinなどが足りなくなってしまいます。<br>
シフトレジスタの74HC165を4つ実装することで、**XIAOの3ピンで32キーの読み取りに対応**しました。
I2CによるOLED制御、TRRSジャックによる左右通信、充電用のPHコネクタやスライドスイッチが実装可能です。

## シフトレジスタの概要
XIAOのD1,D2,D3ピンが74HC165のLD,CK,QHに配線されています。<br>
LDをLowにすることでシフトレジスタにロードされ、<br>
QHからSW0のHIGE/LOWが出力されます。<br>
CKが立ち上がるたびに出力信号がSW1,SW2...とシフトされていきます。


詳しい利用方法は[patamana.com](https://patamana.com)を参照してください。

Arduino IDE を用いる場合は、[patamana/keybard_firmware](https://github.com/patamana/keyboard_firmware)のコードを参考にしてください。


