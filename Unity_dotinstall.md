#01 Unityとはなにか？

- 3Dに強いゲームエンジン

#02 Projectを作ってみよう

- Projectの用語 
	- Scene
		- GameObject（部品、カメラ・敵・プレイヤーなど）
		- Component（ゲームの表面や、位置をどうするかを決める構成要素）

	- Assets（Sceneに共通の部品）


- Unityの基本的な進め方
	- 大量にSceneを作る
	- Sceneの構成要素を決める

#04 視点（自分から見た時の視点）の操作をしてみよう

- GameObjectの追加
	- Hierarchy
	- Create

- 見るものの切り替え
	- オブジェクト名をクリック

- 対象を中心に持ってくる
	- オブジェクト名をダブルクリック

- 視点カーソルの切り替え
	- Q
	- W
	- E
	- R

- 傾きの操作
	- Alt+ドラッグ

#05 GameObjectの操作をしてみよう

- 軸の説明
- オブジェクトの移動
	- Wキーのカーソルにする

- オブジェクトの回転
	- Eキー

- オブジェクトを大きくしたり、小さくしたり
	- Rキー

- オブジェクトをどっから見てるか分からなくなったら
	- Shiftキー+真ん中の四角をクリック

#06 Transformを使ってみよう

- Transformとは
	- 位置関係

- Sceneの制作過程で、位置関係がよくわからなくなったら
	- Position,Rotationを0にする

- カメラの視点合わせがうまくいかない時。自分の視点にしたいとき
	- サブメニュー
		- Align With View


#07 Materialを使ってみよう
- GameObjectの色を変える
	- Asset
		- Material
			- Inspectorの、色を変える
				- AssetのMaterialをGameObjectにドラッグ＆ドロップ

- 画像のはりつけ
	- Asset
		- Import New Assets
			- Importしたものを、Materialにドラッグ＆ドロップ


#08 Rigidbodyを使ってみよう
- 物理特性の付与（重さとか）
	- add component
		- physics

- 弾性をつける
	- Asset
		- Material
			- Physics Material

#09 Directional Lightを追加しよう

- Directional Lightとは
	- Game上を、光らせるためのモノ。

- 再生モードに入った時の注意点。
	- 再生モード中に、Game Objectに出した、変更は、再生モードを終えると変更が、破棄される。


#10 GameObjectを階層化してみよう

- 複数のオブジェクトを同時に動かす
	- ドラッグ＆ドロップで、合体させる。

- カーレースの、車にカメラを付けて、同時に動かしたい時とか。
- GameObjectのフォルダを作る
	- GameObject
		- Create Empty

#11 Prefabを使ってみよう

- prefabとは
	- 再利用な可能な、部品にする。こと

- やり方
	- Assetにドラッグする


#12 Scriptを追加してみよう
- Script
	- Component（部品）の１つとして、扱う

- Scriptの作成
	- Project
		- JavaScript

- 自分のエディタを使う
	- preference
		- External tool


#13 はじめてのScript

- function start
	- スクリプト実行、１回目に動かすメソッド

- function update
	- 1フレームごと

- メッセージの表示
	- Debug.Log("hello world");

- 変数の宣言
	- var 変数名 : 型 = 初期値
    	-var x : int = 5

- 関数の外の変数
	- Inspectorから変更することができる。

#14 GameObjectを移動させてみよう

- 例えば
	- transform.position.z += 0.1
	- taransform.position += Vector3(X軸,Y軸,Z軸) 
	- transform.Translate(X軸,Y軸,Z軸)

- 公式リファレンス
	- スクリプトレファレンスで参照する


#15 ユーザー入力を受け付けよう

- Input○○  
<code> 
if(Input.GetButtonUp("Jump")){  
	Debug.log("Jumped");  
}
</code>