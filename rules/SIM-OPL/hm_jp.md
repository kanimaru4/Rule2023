[日本語](./hm_ja.md) | [English](./hm_en.md)

# Handyman（HM）

参考動画：[Handyman_jp_2023](https://www.youtube.com/watch?v=Z0xf8hgyVzg)

> **Note**
> 参考動画は完璧ではない．開催年度のルールによってタスク内容が異なる可能性があるので，あくまで参考程度にしてください．
> 気になる点や議論したい点などがありましたら，GitHubの[Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues)にてご記入ください．


## メインゴール（Main Goal）

このタスクでは，人間の日常生活をサポートするロボットの基本的な能力を評価する．
タスクの内容は，与えられた指示に従って物体を探索，把持，運搬するものである．


## フォーカス（Focus）

このタスクは，命令文の内容理解，障害物を考慮した自律移動，物体認識，物体操作，人物検出，タスクプランニングなどに焦点を当てている．
加えて，存在しない物体を探す指示のように命令文が誤っている場合には，その誤りを検知し指摘することが求められる．

## セットアップ（Settings）
- **システム構成**：本競技ではシミュレーション環境を実行するWindows PCと，各チームが開発するロボットコントローラを実行するUbuntu PCでrosbridge serverを介した通信を行う．これにより，ロボットのセンサデータの取得や，アバターとロボットのインタラクションを行う．
- **Handyman-ソフトウェア**：シミュレーション環境を実行するWindows PCでは，UnityとSIGVerseをベースにHandymanソフトウェアを実行する．このソフトウェアは，JointState，TF，センサー情報，その他のROSメッセージを一定間隔でロボットコントローラに送信する．セットアップ手順はこちら（なんかのリンク）
- **ロボットコントローラ**：各チームはUbuntu環境において，Handymanタスクを行うためのロボット制御プログラムの開発を行う．TwistやJointTrajectory，その他のROSメッセージを送信することでロボットを制御する．Ubuntu環境のセットアップ手順はこちら（なんかのリンク）
- **ロケーション**：家庭環境を模したSIGVerse上のシミュレーション環境が用いられる．本競技に用いられる環境は複数あり，競技〇週間前までに本Githubにて公開される．

## シナリオ（Scenario）

### スタートフェーズ（Starting Phase）

1. **セッション数**：セッション数は**6セッション**となる．
1. **競技時間**：競技時間は1セッションあたり**10分間**となる．
1. **スタート**：OCの指示によってWindows PCとUbuntu PCを順に実行する．

### 競技フェーズ（Follow-Me Phase）

1. **運搬開始**：ロボットが紙バッグを把持し追従可能な状態になったら，ロボットはアバターーにその主旨を伝える．

1. **ゴール**：6セッションが終了したら，タスク終了になる．


## スコアシート（Score Sheet）

<table>
  <tr>
    <th> <b>Action</b> </th>
    <th> <b>Score</b> </th>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>メインタスク</b> </td>
  </tr>
  <tr>
    <td> 指示された部屋に移動する <br> 
      <ul>
        <li> 指示通りの部屋に移動 </li>
        <li> 誤った部屋に移動 </li>
      指示された物体を把持する <br> 
        <li> 指示通りの物体を把持 </li>
        <li> 誤った物体を把持 </li>
      物体の持ち運び動作を完遂する <br> 
        <li> 指示通りの位置に運搬する </li>
        <li> 誤った位置に運搬する </li>
      </ul> 
    </td>
    <td align="center"> <br> 20 <br> -10 <br> <br> <br> 50 <br> -10 <br> <br> <br> 30 <br> -10 </td>
  </tr>
  
  <tr>
    <td colspan="2" align="center"> <b> ボーナスタスク </b> </td>
  </tr>
  <tr>
    <td> アリーナへの再入場
      <ul>
        <li> 自律的にアリーナ内に入る </li>
        <li> 自律的に`スタート地点`へ戻る </li>
      
    </td>
    <td align="center"> <!-- 50 <br> --> 25 <br> 25 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>ペナルティ</b> </td>
  </tr>
  <tr>
    <td> 不参加（無断） </td>
    <td align="center"> -500 </td>
  </tr>
  <tr>
    <td> <b>合計（ボーナスタスクを含む）</b> </td>
    <td align="center"> <b>500</b> </td>
  </tr>
</table>


> **Note**
> Educationリーグと同じ競技を採用し，ルール内容も同じなのですが，差別化のため異なる採点方式を用いている．

> **Note**
> 開閉式バリア（ガイドポールなど）は，三角形のものを3本ほど用いる．`Setup Day`から使用可能（予定）．


## 運営(EC)による指示（Instructions from the Executive Committee(EC)）

- 準備
  - Ubuntu PCでロボットコントローラやSIGVerse rosbridgeなどを起動する．
  - Windows PCでHnadyman-ソフトウェアを起動する．
  - 


## レフェリー(OC)の動き（Role of the Referee(TC)）

- 競技開始30分前に集まり，競技者とともに接続確認を行う．
- スコアシートに基づき，競技を採点する．
- 他のTCと採点内容を確認し合う．
- スコアシートを提出する．

> **Note**
> TCは各チームから数名選出され，他チームの競技において以下を行ってもらう．詳細については，一般規定の[採点方法](./gr_ja.md#採点方法scoring-system)をご確認ください．
