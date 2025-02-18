﻿//------------------------------------------------------------------------------
// Magica Cloth
// Copyright (c) Magica Soft, 2020
// https://magicasoft.jp
//------------------------------------------------------------------------------

■概要
Magica Cloth（マギカ・クロス）はUnity Job System + Burstコンパイラにより動作する高速なクロスシミュレーション（揺れものアセット）です。

■要求Unityバージョン
Unity2018.4.0(LTS)以上


■機能

* Unity Job System + Burstコンパイラによる高速なクロスシミュレーション
* WebGLを除くすべてのプラットフォームで動作可能
* ボーン(Transform)で駆動するBoneClothとメッシュで駆動するMeshClothを装備
* MeshClothはスキニングメッシュでの動作も可能
* 簡単で直感的なインターフェースによりすぐにセットアップ可能
* スローなどの時間操作が可能
* フルソースコード付き


■使い方
オンラインマニュアルとなっていますので、詳しくは次のURLを参照してください。
https://magicasoft.jp/magica-cloth-install/

まず[インストールガイド]に従いパッケージをインストールしてください。
次に[システム概要]を読み、各種[セットアップガイド]に進むと理解が深まります。


■更新履歴
[v1.8.0]
報告: データフォーマットが変更となりました。過去のデータでは新しい機能を利用できないため、再度[Create]ボタンを押してデータを作り直す必要があります。
追加: BoneClothにメッシュ結合方式を追加しました。これによりボーン接続から自動でメッシュを作成できます。ボーンによるスカートなどの動作が改善します。
追加: MagicaPhysicsManagerのenableを操作することで、クロスシミュレーション全体をON/OFFすることが可能になりました。
改善: 一部のプリセットパラメータを調整しました。
改善: 衝突判定を改善しました。
改善: Penetrationの動作を改善しました。
修正: Penetrationのマイナススケール（フリップ）時の問題を修正しました。

[v1.7.6]
追加: キャラクタのマイナススケール（フリップ）に対応しました。ただし反転軸はxyzの１軸のみとなります。
追加: マイナススケールのサンプルシーンを追加しました。
改善: [Once per Frame]更新オプションの廃止を取りやめました。
改善: パーティクル半径の最小値を0.01から0.001に変更しました。
修正: MeshSpringの法線／接線再計算が正しく行われていなかった問題を修正しました。ライティングに影響します。
修正: エディタでの実行停止時にエラーが発生する問題を修正しました。

[v1.7.5]
追加: [World Influence]に最大速度の設定を追加しました。高速移動時にシミュレーションが安定します。
追加: リセット時にパーティクルが跳ねる問題を改善するパラメータ[Stabilization Time After Reset]を追加しました。
改善: 衝突判定によるパーティクルの振動を低減させました。
改善: 衝突判定の精度が少し向上しました。
修正: グローバルコライダーが高速に移動／回転すると、離れたパーティクルが弾かれる問題を修正しました。
修正: 高速移動時にボーンが不用意に伸びる問題を修正しました。
修正: 固定パーティクルの補間処理に一部誤りがあったため修正しました。
修正: スプリング設定の一部のパラメータを変更しても、バーが黄色くならない問題を修正しました。
修正: メッシュにtangentデータがない場合に、RenderDeformerでエラーが発生する問題を修正しました。
修正: CubismSDK(Live2D)との併用時に動作しない問題を修正しました。(ただしUnity2019.3以上)

[v1.7.4]
追加: [Radius][Drag][Gravity][Mass]パラメータのAPIを追加しました。
改善: メッシュの頂点数が65535を超える場合はエラーを表示するようにしました。これは既存の制限です。
修正: スケーリング処理によりUnity2019.1-2019.2.13でエラーが発生する問題を修正しました。

[v1.7.3]
追加: クロスコンポーネントにランタイムでコライダーを追加できるようになりました。
追加: AvatarPartsをAvatarに接続する時に、Avatarのコライダーを引き継ぐオプションを追加しました。
追加: Colliderコンポーネントにオフセット位置を設定できるようになりました。
追加: MagicaAvatarにOnAttachParts, OnDetachPartsイベントを追加しました。
改善: BlendWeightをアニメーション制御できるようになりました。
改善: Springコンポーネントの[Adjust Rotation]は常に有効となり、モードにより振る舞いを設定する方式に変更しました。
改善: MeshSpring, Colliderのギズモが不用意な場合にも表示されていた問題を修正しました。
改善: PlayerLoopの制御を外部関数として公開しました。
修正: 複数のクロスコンポーネントを入れ替えると、まれにメッシュの頂点が崩壊する問題を修正しました。
修正: Unity2019.4でプリセットを読み込むとGUIのエラーが発生する問題を修正しました。
修正: 頂点ウエイトが入ったメッシュをMeshRendererに入れてMeshClothを設定するとエラーが発生する問題を修正しました。

[v1.7.2]
追加: ランタイムでのスケール変更に対応しました。
改善: パラメータ変更によりデータの再構築が必要な場合は、インスペクターのパラメータバーの色が黄色に変化するようにしました。
修正: クロスコンポーネントの初期化の順番によりエラーが発生する問題を修正しました。
修正: AvatarPartsアタッチ時にInfluence Targetが切り替わらない問題を修正しました。
修正: Projectのプレハブを削除する時に、状況によりエラーが発生する問題を修正しました。

[v1.7.1]
追加: APIに[World Influence][Collider Collision][Penetration]パラメータへのアクセス関数を追加しました。
改善: まだデータが作られていない場合はインフォメーションにエラーではなく、データが無い状態を表示するようにしました。
修正: Collectionsパッケージ0.9.0以上を入れるとエラーが発生する問題を修正しました。
修正: [ReadOnly]属性がカスタム定義されていた場合にエラーが発生する問題を修正しました。

[v1.7.0]
報告: データフォーマットが変更となり過去のデータでは起動しなくなりました。再度[Create]ボタンを押してデータを作り直す必要があります。
追加: Surface Penetrationの機能を追加しました。
追加: Collider Penetrationの機能を追加しました。
追加: Entity Component Systemとの併用が可能となりました。Unity2018.4/Unity2019.2 では MAGICACLOTH_ECSデファインをプロジェクトに設定する必要があります。
追加: クロスモニターから頂点／パーティクルの軸(XYZ)を表示できるようになりました。
改善: 衝突判定を見直し、以前より突き抜けが改善しました。
改善: Unsafe Codeのプロジェクト設定が不要となりました。
改善: クロスモニターのデプス表示は現在の数値を表示するようになりました。
改善: 予めメッシュに可動ボーンのウエイトが入っている場合に、シミュレーションが不安定になる問題を修正しました。
修正: MeshClothの[Create]ボタンのスペルミスを修正しました。
修正: VirtualDeformerのデータ作成時に無限ループに陥る問題を修正しました。

[v1.6.1]
改善: 摩擦処理のアルゴリズムを改善しました。パーティクルが振動する問題が低減しました。
修正: エディタにインスペクタウインドウが２つ以上存在する場合に頂点ペイントが正常に行えない問題を修正しました。
修正: エディタでの実行終了時にエラーが発生する問題を修正しました。

[v1.6.0]
改善: ClampPosition / ClampRotationの動作を改善。移動制限よりも衝突判定を優先するようにしました。
改善: 衝突判定処理の改善。
改善: ローテーションラインの生成アルゴリズムを改善しました。
改善: コライダーギズモは基本的に選択していない場合は非表示にしました。
改善: 実行中のクロスインスペクタにシミュレーションのリセットボタンを追加しました。
改善: 摩擦処理のアルゴリズムを改善しました。
改善: RestoreDistanceのNear接続時に、最大接続数を指定できるようにしました。
改善: VirtualDeformerのウエイト算出方式を、参照するスキニングメッシュ頂点の平均ウエイト値に変更。
これによりアニメーション時に本来意図しない頂点が変形する問題が大幅に減少します。
改善: VirtualDeformerの固定頂点は、状況により完全に計算から除外するように設定しました。
これによりアニメーション時に本来意図しない頂点が変形する問題が大幅に減少します。
改善: AdjustLineをRotation Interpolationに名称変更しました。
改善: Rotation InterpolationにFixedNonRotationフラグを追加しました。
このフラグをONにすると固定パーティクルは一切回転しなくなります。
修正: グローバルコライダーが正しく機能していなかった問題を修正

[v1.5.1]
追加: [Distance Disable]パラメータへのアクセスAPIを追加しました。
追加: [External Force]パラメータへのアクセスAPIを追加しました。
改善: 各コンポーネント間の接続制御を強化しました。
修正: 実行中に[Distance Disable]をOn/Offするとエラーが発生する問題を修正しました。
修正: 遅延実行時にLateUpdateでクロスコンポーネントを作成するとエラーが発生する問題を修正しました。
修正: 遅延実行はLateUpdateの最後ではなく、PostLateUpdateで実行するように変更しました。
修正: 非アクティブのレンダーデフォーマが計算処理されていた問題を修正しました。
修正: 非アクティブのレンダーデフォーマがメモリリークを起こしていた問題を修正しました。
修正: クロスモニタの[RenderMeshVertexUsed][VirtualMeshVertexUsed]の数値を正しいものに修正しました。

[v1.5.0]
追加: 遅延実行の機能を追加しました。
改善: パフォーマンスを改善しました。
改善: プロファイラにメッシュへの書き込み時間を表示させました。
改善: レンダーデフォーマの法線／接線再計算を法線のみ、もしくは法線＋接線を選択できるようにしました。
改善: 頂点ペイント中にシーンビューをAlt+マウスドラッグで画面回転できるように設定しました。
修正: ボーンへの書き込み時にスケール計算が間違っていた問題を修正しました。
修正: １つのボーンを複数で参照する場合に、親ボーンへの参照が消失する場合がある問題を修正しました。
修正: テレポートが正しく機能しない場合がある問題を修正しました。
修正: クロスモニターを非表示にしていると、ウインドコンポーネント選択時にエラーが発生する問題を修正しました。
修正: プレハブモードでの編集時にデータが正しく書き込まれない問題を修正しました。
修正: MeshSpringの軸をインスペクタで編集した時に、シーンビューを再描画するように修正しました。
報告: 更新モードの[Once Per Frame]は将来的に廃止予定となりました。

[v1.4.2]
改善: コライダー作成時は親のスケールを自動判断してコライダーのスケールを調整するように変更しました。
修正: Unity2018を使用し、SkinnedMeshRendererとMeshRendererが混在する場合に、メッシュが壊れる問題を修正しました。
修正: カプセルコライダーのギズモが正しく表示されていなかった問題を修正
修正: クロスコンポーネントがアタッチされたフレームに、クロスシミュレーションが実行されていなかった問題を修正

[v1.4.0]
追加: 着せ替え機能を追加しました(Avatar, AvatarParts)
追加: クロスコンポーネントのテレポートは初期設定ではOFFに変更しました。
改善: クロスの移動にともなう振動を低減させました
改善: クロスコンポーネントオブジェクトを作成する時に、親の名前を引き継ぐように設定しました。
修正: アセットバンドルから読み込んだ場合にMeshOptimizeMissmatchエラーが発生する問題を修正しました。
修正: 頂点ペイント時にシーンビューが再描画されない問題を修正しました
修正: クロスコンポーネントの追加／削除を繰り返すと、トランスフォームの書き込みがおかしくなる問題を修正しました。
修正: コライダーはトランスフォームスケールを正しく反映するように修正しました。
修正: メインカメラが存在しない場合にエラーが発生する問題を修正しました。
修正: レンダラーをマルチ選択してRenderDeformerをアタッチすると、データが作成されない問題を修正しました。

[v1.3.0]
追加: 風の機能を追加しました(Wind)
追加: 風のサンプルシーンを追加しました(WindSample)
改善: クロスチームの前処理をC#からJobSystemに書き直しました。

[v1.2.0]
追加: 元の姿勢とのブレンド機能を追加しました(Blend Weight)
追加: 距離によるシミュレーション無効化機能を追加しました(Distance Disable)
追加: 距離無効化機能のサンプルシーンを追加しました(DistanceDisableSample)
改善: クロスモニターにスクロールバーを追加しました
改善: メッシュにUV値が無くともデータを作成できるようになりました
改善: エラー処理を強化しました
修正: スローの再生不具合を修正しました。Time.timeScaleは正しく機能します
修正: プレハブをCtrl+Dで複製した場合にエラーが発生する問題を修正しました
修正: 頂点ペイントを行わずにデータを作成しようとするとエラーが発生する問題を修正しました

[v1.1.0]
追加: Unity2018.4(LTS)に対応しました
改善: エラー内容をエラーコードとともに詳しく表示するようにしました
改善: 頂点ペイントは頂点インデックスではなく頂点ハッシュで記録するようにしました
修正: MagicaPhysicsManagerが２つ以上見つかった場合、後から発見されたものを削除するようにしました

[v1.0.3]
修正: Unity2019.3.0にて編集中にデータへの参照が消失する問題を修正

[v1.0.2]
修正: Macエディタ環境で実行時にエラーが発生する問題を修正

[v1.0.1]
修正: Unity2019.3にてプレハブ書き込み時にエラーが発生する問題を修正

[v1.0.0]
報告: 初期リリース



