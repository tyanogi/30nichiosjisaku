#  30日OS自作入門
覚えること多すぎて覚えれないのでメモっておく．

## アセンブラ命令
naskという，NASMを筆者が拡張したものを使用している．
|命令|説明|例|
|:--:|:--:|:--:|
|DB|Data Byteの略．ファイルの内容を1バイトだけ直接書く|DB 0x08|
|RESB|Reserve Byteの略．指定したバイト数をあけて0x00で埋める．|RESV 16|
|DW|Data Wordの略．DB命令の仲間．Wordは16ビットのこと．|DW 224|
|DD|Data Double-wordの略．DB命令の仲間．Double-wordは32ビットのこと|2880|
|ORG|originの略．機械語の実行時にメモリのどこに読み込まれるかをnaskに教える．|ORG 0x7c00|
|JMP|Jumpの略．指定したメモリ番地に飛ぶ．|JMP 0x8000|
|MOV a,b|Moveの略．aにbを代入. a,bにはメモリ番地を指定することが可能．メモリ番地の指定はBX，BP，SI，DIだけ．|MOV AX,0 ;(AX=0) <br> MOV AL,[SI]|
|CMP a,b|Compareの略．aとbを比較する．|CMP AL,0|
|JE|Jump if Equalの略．比較結果が等しければ指定したメモリ番地に飛ぶ．|JE fin|
|INT|Interruptの略，ソフトウェアの割り込み命令|INT 0x13|
|HLT|Haltの略．CPUを待機状態にする||HLT|

## x86レジスタ
### 種類
- 汎用レジスタ
- セグメントレジスタ
- インジケータ
### 汎用レジスタ
|32ビット|16ビット|8ビット|名称|用途|
|:--:|:--:|:--:|:--:|:--:|
|EAX|AX|AH，AL|アキュムレーターレジスタ|累積演算|
|ECX|CX|BH，BL|カウンターレジスタ||
|EDX|DX|DH，DL|データレジスタ||
|EBX|BX|BH，BL|ベースレジスタ||
|ESP|SP|分けられない|スタックポインタ||
|EBP|BP|分けられない|ベースポインタ|
|ESI|SI|分けられない|ソースインデックス|
|EDI|DI|分けられない|デスティネーションインデックス|

### セグメントレジスタ
|レジスタ名|名称|用途|
|:--:|:--:|:--:|
|ES|エクストラセグメントレジスタ||
|CS|コードセグメントレジスタ||
|SS|スタックセグメントレジスタ||
|DS|データセグメントレジスタ||
|FS|||
|GS|||


## Memo
### p.40
筆者が記したBIOSの使い方ページがリンク切れしている．  
##### 似たようなページ ↓  
<https://wiki.osdev.org/BIOS#Common_functions>  
<http://oswiki.osask.jp/?(AT)BIOS>
### p.42
筆者が記したメモリマップのページがリンク切れしている．
##### 似たようなページ → <https://wiki.osdev.org/Memory_Map_(x86)>

