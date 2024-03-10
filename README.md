# パタマナボード 回路図・kicadデータ
パタマナボードの回路図やkicadデータです。

## パタマナボードの概要
XIAO用キーボード基板です。<br>
XIAOは無線接続ができて便利ですが、端子数が少なく、マトリクス構造にしてもOLEDを制御するピンなどが足りなくなってしまいます。<br>
シフトレジスタの74HC165を4つ実装することで、**XIAOの3ピンで32キーの読み取りに対応**しました。<br>
I2CによるOLED制御、TRRSジャックによる左右通信、充電用のPHコネクタやスライドスイッチが実装可能です。

## シフトレジスタの概要
XIAOのD1,D2,D3ピンが74HC165のLD,CK,QHに配線されています。<br>
LDをLOWにすることでシフトレジスタにロードされ、<br>
QHからSW0のHIGE/LOWが出力されます。<br>
CKが立ち上がるたびに出力信号がSW1,SW2...とシフトされていきます。

## ピン配置
XIAOのSDA,SCLピンがOLED用の端子のSDA,SCLに配線されています。

TRRSにはXIAOのTX,RXピンとUSBからの5Vが配線されており、左右でTXとRXが逆になっているので、TRRSジャックの実装位置を変えることで、UARTでの左右通信が可能です。

XIAOの裏面の+端子をパタマナボード裏面のBAT+端子に繋げ、スライドスイッチとPHコネクタを実装し、PHコネクタにリチウムイオンポリマーバッテリーを繋げることで充電が可能です。

バッテリーの電圧を200kΩ抵抗2つの直列で分圧した電圧がXIAOのD0ピンに印加されているので、電圧値を読み取ることでバッテリー残量がわかります。

D8,D9,D10ピンは未使用なので、自由に利用できます<br><br>

詳しい利用方法は[patamana.com](https://patamana.com)を参照してください。

Arduino IDE を用いる場合は、[patamana/keybard_firmware/simple_split_keyboard](https://github.com/patamana/keyboard_firmware/tree/main/simple_split_keyboard)のコードを参考にしてください。


