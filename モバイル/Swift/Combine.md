# Combineに関して学んだことをまとめる。

### Combineとは
CombineとはWWDC２０１９でAppleでSwiftの新しいフレームワークとして紹介されました。オブジェクトからオブジェクトにイベントを伝える仕組みを提供します。</br>
RxSwiftやReactiveSwiftの代替のフレームワークとしても使用される。</br>
非同期イベントの処理をカスタマイズすることが可能である。</br>

基本的な考え方にPublisherとSubscriberがある。</br>
・**Publisher**</br>
Declares that a type can transmit a sequence of values over time.</br>
時間経過とともに変化する値を転送する型を宣言することができる。</br>
・**Subscribers**</br>
A protocol that declares a type that can receive input from a publisher.</br>
publisherから入力を受け取ることができる型を宣言することができるプロトコルのこと。</br>

イベントを渡す手段としてPassthroughSubjectクラスを使用する。</br>
```Swift
let subject = PassthroughSubject<Output, Failure>
```

送信された値に対して処理をする時にはsinkメソッドを使用する。sinkメソッドはsubscribeの一種である。</br>
```Swift
func sink(receiveValue: @escaping ((Self.Output) -> Void)) -> AnyCancellable
```
また、sinkには戻り値が存在しそれをsubscriptionという。実際にCombineを使用する時には、これらを意識する必要がある。

値を渡す時にはsendメソッドを使用する。</br>
```Swift
subject.send(value)
```
イベントの完了を渡すこともできる。以下のコードでイベントの完了を受信した際に実行する処理である。
```swift 
func sink(receiveCompletion: @escaping ((Subscribers.Completion<Self.Failure>) -> Void)) -> AnyCancellable 
```

この時には値を送信する代わりにイベントの完了を意味する.finishedを送信する。
```Swift
subject.send(completion: .finished)
```





