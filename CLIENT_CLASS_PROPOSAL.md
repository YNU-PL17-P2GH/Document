# Client Class Proposal
## MainFrame extends JFrame
- JFrame継承のメインウィンドウを受け持つ
- Callbackを実装し,画面切り替え,セーブデータに関する取り扱いを受け持つ

## Title extends Canvas(?)
- タイトル画面
- 適当にMainFrameにsetContentPane()させて遷移

## World Select extends Canvas(?)
- ワールドセレクト(複数ダンジョンを実装するならよい)
- 適当にMainFrameにsetContentPane()させて遷移

## DungeonBase extends Canvas(?)
- メインとなるダンジョンを実装するためのベースクラス
- ダンジョンへの進入は,基本的にこれを継承したクラスをロードすることによって行う
※クラスロード方式にする訳は,ダンジョンごとに特定のアクションを起こしてヒントを出せるようにするため
- 次のダンジョンへ進むnextDungeon()
- 前の部屋へ戻るpreviousDungeon()
- 仕掛けを作動させるopenDoor(), setVariable()など
- プログラムを実行するrunScript()
- マップの部分だけ受け持つようにして,メニュー等はMainFrameとかに受け持たせる

## Connection
- 通信クラス.
- サーバとのデータ同期を受け持つ.
- とりあえずlogin(),send(),receive()
