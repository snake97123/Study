# Combineに関して学んだことをまとめる。

### Combineとは
CombineとはWWDC２０１９でAppleでSwiftの新しいフレームワークとして紹介されました。</br>
RxSwiftやReactiveSwiftの代替のフレームワークとしても使用される。</br>
非同期イベントの処理をカスタマイズすることが可能である。</br>

基本的な考え方にPublisherとSubscriberがある。</br>
・**Publisher**</br>
Declares that a type can transmit a sequence of values over time.</br>
時間経過とともに変化する値を転送する型を宣言することができる。</br>
・**Subscribers**</br>
A protocol that declares a type that can receive input from a publisher.</br>
pablisherから入力を受け取ることができる型を宣言することができるプロトコルのこと。

