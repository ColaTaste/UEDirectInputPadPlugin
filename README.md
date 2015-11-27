# UEDirectInputPadPlugin
UE4.10(Windows)で、DirectInputのゲームパッド(以下DIPad)を使用できるようするプラグインです。  
まだ開発中ではありますが、最低限動くようにはなりましたので公開します。

# 特徴
- 複数のゲームパッドに対応
- UE4のゲームパッドイベントと統合

## 複数のゲームパッド対応
複数のゲームパッドがPCに認識されてる場合、見つかった順番にPlayerIDを割り当てます。  
最大でPlayerID(8つ)分認識します。

XInputパッドがすでに存在していた場合は、XInputパッドを優先します。  
つまり、XInputパッドの次からPlayerIDが割り振られます。

## UE4のゲームパッドイベントと統合
UE4が元からもっている「ゲームパッドAボタン」「ゲームパッド左サムスティックX」などのイベントとして入力を受け取れます。
それらを使う限り、入力元のゲームパッドがDIPadなのかXInputパッドなのかを気にする必要はありません。

ただし、DIPadはパッドごとにボタン配置が違いますので、XInputパッドの配置と合わせる必要があります。そのための仕組みも用意してあります。

もちろん、DIPad専用のイベントもあります。こちらの場合、最大で6つ軸、1つのPOV、32個のボタンイベントを扱うことができます。

# 使用方法
UE4のプラグインとして入れて有効にするだけで使うことができます。
プラグインのフォルダ名は、「DirectInputPadPlugin」としてください。  
VS2015は入れて、ソースからビルドしてください。バイナリ(DLL)はつけていません。

DIPadとしてのイベントは、BPエディタでDIGamePadで検索！

BP公開APIをさっと見たい人は、「DirectInputPadJoystick.h」を見て下さい。

詳しい使い方は、[こちらの記事](http://katze.hatenablog.jp/entry/2015/11/27/191351)を参照してください。

# 使用上の注意
- キーリピート非対応

# ToDo
- キーコンフィグサポート機能

# Misc
VS2015で開発していますが、VS2013でもコンパイルできるとは思いますのでUE4.9以前でも使用できるとは思います。  
内部でtuple/functionalを使っていますので、VS2012以前ではその部分を書き換えれば、たぶん

# 参考
https://github.com/Ikarus76/UEJoystickPlugin/

# 連絡先
Twitter : [katze_7514](http://twitter.com/katze_7514)  
blog    : [GameProgrammer's Night](http://katze.hatenablog.jp/)
