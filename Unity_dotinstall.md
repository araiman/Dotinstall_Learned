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
	- rigidbody（物理特性）

- 弾性をつける
	- Asset
	- Material
	- Physics Material
	- Bouncinessの値を、0より大きくする

#09 Directional Lightを追加しよう

- Directional Lightとは
	- Game上を、光らせるためのモノ。

- 再生モードに入った時の注意点。
	- 再生モード中に、Game Objectに出した、変更は、再生モードを終えると変更が、破棄される。


#10 GameObjectを階層化してみよう

- 階層化の効用
	- 親と子を同時に動かせる

- 階層化の方法	
	- ドラッグ＆ドロップで、合体させる。

- GameObjectのフォルダを作る
	- GameObject
		- Create Empty

#11 Prefabを使ってみよう

- prefabとは
	- 再利用な可能な、部品。

- オブジェクトを、Prefabにするやり方
	- Assetにドラッグする

- Prefabの効用
	- 一気に、複数のオブジェクトに変更を加えることが出来る


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

- 関数の外で宣言された変数
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

- それぞれのボタンに割り当てられている名前を確認する方法
	- メニューバー
	- Edit
	- Project Settings
	- Input


#16 衝突判定をしてみよう
- 衝突の時に、実行する関数名
	- OnCollisionEnter()

- 当たった、オブジェトの判定
	- <code>OnCollisonEnter(obj : collision){  
		if(obj.gameObject.name == "RightWall"){  
			Debug.Log("Right Hit!");  
		} 
	  } 
	  </code>


#17 動的にGameObjectを生成しよう
- Prefabから動的に生成する方法
	- EmptyのGameObjectを用意
	- 動的に生成したいモノのPrefabを作る
	- コードを記述する
		- <code>
			var ball : Transform;  
			function Update () {  
				if(Input.GetButtonUp("Jump")) {  
					Instantiate(ball, transform.position, transform.rotation); 
				}  
			}  
		  </code>


#18 OnGUIを使ってみよう
- 別のシーンの呼び出し
	- Scriptを作成

		- <code>
			var style : GUIStyle;  
			function OnGUI () {  
				GUI.Label(Rect(10, 10, 200, 50), "GameOver", style);  
			}  
  		</code>


#19 別のSceneを呼び出してみよう
- Scriptで、呼び出し。
	- <code>  
		function Update () {  
			if(Input.GetButtonUp("Jump")) {  
				Instantiate(ball, transform.position,   transform.rotation);  
				n++;  
				if(n > 10){  
					Application.LoadLevel("GameOver");  
				}  
			}  
		}  

	  </code>

- BuildSettingsで、Sceneを順番通りに追加


#20 ゲームを書きだしてみよう
- BuildSettings
- BUild


#23 Enemyの設定をしていこう
- Cubeが回転しながら落ちてくる、というScriptを書く