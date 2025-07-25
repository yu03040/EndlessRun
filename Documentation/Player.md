# EndlessRun - プレイヤークラス説明

## RunCharacter クラスの概要
- **ソースファイルとヘッダファイル名**: `RunCharacter.cpp` / `RunCharacter.h`
- **主要な機能**:
  - **プロパティのデフォルト値の設定**: キャラクターの初期設定、例えばカプセルサイズやカメラの設定などを行います。
  - **カウントダウンタイマーの表示**: ゲーム開始時にカウントダウンタイマーを表示します。
  - **Tick処理**: 毎フレームごとにキャラクターの前進やコーナリングを処理します。
  - **EnhancedInputによる入力アクション**: プレイヤーの入力に応じてキャラクターが動作するように、ポーズ、ジャンプ、移動、方向転換の入力アクションを設定します。
  - **死亡処理**: キャラクターが死亡した際に、爆発エフェクトとサウンドを再生し、結果画面を表示する処理を行います。

## このクラスのソースコードの内容
### `RunCharacter.cpp` の内容概要
以下は `RunCharacter.cpp` の主要な内容です。

- **コンストラクタ `ARunCharacter::ARunCharacter()`**: このコンストラクタで、キャラクターの初期設定を行います。コリジョンカプセルのサイズ設定やカメラ、キャラクターの移動設定、各種エフェクトやサウンド、入力アクションの設定が含まれます。

- **`BeginPlay()`**: プレイヤーがゲームを開始した際に呼び出され、カウントダウンタイマーを表示するウィジェットをセットアップします。

- **`Tick(float DeltaTime)`**: 毎フレームで呼び出され、キャラクターが前方に移動し続ける処理や、プレイヤーが角を曲がる処理が実行されます。

- **`SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)`**: プレイヤーの入力（ポーズ、ジャンプ、移動、方向転換）に応じてキャラクターを操作できるように設定します。

- **`PauseInput()`**: ポーズ入力があった際にポーズメニューを表示する処理を行います。

- **`StartJump()` と `StopJump()`**: ジャンプの開始と終了を処理します。

- **`MovementInput(const FInputActionValue& Value)`**: プレイヤーの移動入力に応じてキャラクターを左右に動かす処理を行います。

- **`TurnLeftMovement()` と `TurnRightMovement()`**: プレイヤーが左右に方向転換する際の処理を行います。

- **`DisplayCountDown(TObjectPtr<APlayerController>& PlayerController)`**: ゲーム開始時のカウントダウンタイマーを表示するウィジェットをセットアップします。

- **`TurnCorner()`**: キャラクターが角を曲がる際に、希望の方向に向かってカメラを回転させる処理を行います。

- **`Death()`**: キャラクターが死亡した際の処理を行います。爆発エフェクトとサウンドを再生し、プレイヤーキャラクターを非表示にして、1秒後にリザルト画面を表示します。
