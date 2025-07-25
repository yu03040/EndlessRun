# EndlessRun - ゲームモードクラス説明

## ゲームモードクラスの概要

### クラス名とファイル名
- クラス名: `RunGameMode`
- ソースファイル: `RunGameMode.cpp`
- ヘッダファイル: `RunGameMode.h`

### 機能概要
`RunGameMode` クラスは、EndlessRunゲームのゲームモードを担当します。このクラスでは、以下の処理を主に行っています。

- **デフォルトプロパティの設定**: ゲームの初期状態を設定します。
- **セーブデータのロードとセーブ**: プレイヤーの進行状況を保存し、ゲーム開始時にそのデータを読み込みます。
- **UIの表示**: ゲーム中のコイン数や走行距離を表示するUI (`DisplayRunScore`) を管理します。
- **床タイルの事前生成**: ゲーム開始時にプレイヤーがすぐに走れるよう、床タイルを一定数生成します。
- **リザルトの表示**: プレイヤーがゲームオーバーになった際に、結果を表示する (`ShowResult`) 処理を行います。

## このクラスのソースコードの内容

### 初期化処理 (`ARunGameMode::ARunGameMode`)
- 毎フレーム `Tick()` メソッドを呼び出すよう設定。
- 次の床タイルの接続ポイントや、コイン数、走行距離の初期値を設定。

### ゲーム開始処理 (`ARunGameMode::BeginPlay`)
- セーブデータをロードし、ゲーム中のUIを表示。
- 初期状態として、床タイルを10枚生成し、プレイヤーが落ちないように設定。

### ゲーム進行処理 (`ARunGameMode::Tick`)
- プレイヤーが走っている間に、距離を計算し、ランクデータに記録。

### 床タイル生成 (`ARunGameMode::AddFloorTile` と `ARunGameMode::AddFloorTileCurve`)
- 床タイルをランダムに生成し、プレイヤーが走れるようにします。7枚ごとに曲がったタイルを追加します。

### ゲームオーバー処理 (`ARunGameMode::ShowResult`)
- ゲームオーバー時に、結果を表示するためのウィジェットを生成し、ランクデータを更新します。

### セーブデータの管理 (`ARunGameMode::CreateSaveFile`, `ARunGameMode::SaveGame`, `ARunGameMode::LoadGame`)
- セーブデータの作成、保存、読み込みを行います。

