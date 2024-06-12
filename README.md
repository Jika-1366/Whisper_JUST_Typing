# Input_with_Whisper
Enable voice input with Whisper anywhere on your PC (with a few seconds of lag)


Input_with_Whisperは、Whisper APIを使用して音声を録音し、その音声をテキストに変換し、Pythonを使用して変換されたテキストを自動的に入力するプロジェクトです。windows向けです。デモ動画をご覧ください。

[![Video Demonstration](https://img.youtube.com/vi/DXQxencVgeU/0.jpg)](https://www.youtube.com/watch?v=DXQxencVgeU) <br>

## 使用上の注意
* 使用による不利益の責任は負いかねますので、自己責任でご使用ください。
* 2024/05/27において、料金は$0.006 / minute  (録音1分あたり約0.006ドル)で、非常に安価です。秒刻みで値段が決まります。<br>
最新情報：https://openai.com/api/pricing/

## 操作方法
### 基本的な操作方法
1. キーボードショートカット（例: Shift + Ctrl + V）でプログラムを起動します。
2. 入力したい場所をクリックし、入力待ちにします。
3. Deleteキーで録音を開始します。
4. 再度Deleteキーを押して録音を停止します。停止後、文字起こしされたテキストが自動で入力されます。
5. 再度録音したい場合は、Deleteキーを再度押して録音を開始・停止します。
6. 基本的には、プログラムは起動したまま、作業を続けていただくとよいかと思います。
7. プログラムを終了したい場合は、escキーを押していただくと、完全にプログラムを終了できます。

### 発展的な操作方法
* 録音中に、Deleteキーを2回押すことで録音を停止したあとすぐに次の録音を開始し、文字起こしと録音を並行できます。
* 単語の登録を行えますが、2024/6/12現在、244トークンまでしか、文字起こしに反映されません。単語の登録料が多すぎると、最初に登録されいている単語から無視されていきます。https://platform.openai.com/docs/guides/speech-to-text/improving-reliability

## 使用例
* READMEファイルの作成をLLMに頼むとき
* タイピングに疲れた時
* タイピングが苦手な方へ
* 気楽なメールを入力する際に



## 前提条件

* ~~Python 3以降~~
* ~~OPENAI API KEYを持っていること（無料で取得できます）~~
* ~~必要なpythonライブラリがあること（数は少ないです）~~

なくなりました。

## 準備
### 簡単な準備
「<>code」ボタン を押したら、zipインストールをクリックしてください。
ダウンロードしたzipファイルを解凍し、Input_with_Whipser.exeファイルを実行してください。


### 面倒な準備
#### 準備1（インストール）
``` batch
git clone https://github.com/Jika-1366/Input_with_Whisper.git
cd Input_with_Whisper
```

#### 依存関係
``` batch 
pip install pyaudio 
```

など


#### 準備2(環境変数の登録とライブラリインストール)
システム環境変数またはユーザー環境変数にOpenAI APIキーを設定します:
export OPENAI_API_KEY='your_openai_api_key'

ここまでできたら、一度普通にpythonコード（main.py）を実行して、テストしてみてください。


#### 準備3(ショートカットキー登録)
#### ショートカットキーによる使用(windows)
プログラムをキーボードショートカットで起動するのが便利です。以下の手順で設定できます:
1. .batファイルを以下のように書きます。今回は以下2つの絶対パスを使用します。
``` batch
cd "main.pyのあるディレクトリパス"
start /min cmd /c "path_to_python.exe path_to_main.py"
```

2. Pythonプログラムを起動するショートカットを作成します。
3. 作成したショートカットのプロパティを開き、「ショートカットキー」欄に Shift + Ctrl + V と入力します（VはVoiceのVです）。

## プログラムの動作の流れ
1. 環境変数からOPENAI_API_KEYを取得します。
2. 音声の録音：音声を録音し、.wavファイルとして保存します。
3. 文字起こし: .wavファイルを.mp4に変換し、Whisper APIに送信して文字起こしを行います。
4. 自動入力:録音の終了を検知すると、録音処理と並行して、 文字起こしされたテキストを入力します。


## 各ファイルの説明
Main.py: 音声録音、文字起こし、入力を管理する中央スクリプト。 
Head.py: Main.pyで使用されるヘルパー関数が含まれています。


## ご協力
コードの機能充実にご協力いただけますと大変幸いです。参考までに以下のような「to do」がございます。

## 予定(to do)
* OpenAIのwhisperには、固有名詞や特殊な単語を登録して聞き取り精度を向上させる機能がございますので、その機能を実装する予定です。
* 録音してることが分かりやすい小さなウィンドウの表示。
* また、これを骨組みに、バックグラウンドにLLMと対話できるサービスの開発も行う予定です。(GPT-4oが本格的に実装されればもう必要性はなくなりますが、そこまでのつなぎです)


## ライセンス
このプロジェクトはMITライセンスの下でライセンスされています。

