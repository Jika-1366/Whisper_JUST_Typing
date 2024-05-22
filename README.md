# Whisper_JUST_Typing
Enable voice input with Whisper anywhere on your PC (with a few seconds of lag)


WhisperTypingは、Whisper APIを使用して音声を録音し、その音声をテキストに変換し、Pythonを使用して変換されたテキストを自動的に入力するプロジェクトです。windows向けです。

## 操作方法
### 基本的な操作方法
1. 入力待ち状態にする場所をクリックしてから、キーボードショートカット（例: Shift + Ctrl + V）でプログラムを起動します。
2. Deleteキーで録音を開始します。
3. 再度Deleteキーを押して録音を停止します。停止後、文字起こしされたテキストが自動で入力されます。
4. 再度録音したい場合は、Deleteキーを再度押して録音を開始・停止します。

### 発展的な操作方法
録音中に、Deleteキーを2回押すことで録音を停止したあとすぐに次の録音を開始し、文字起こしと録音を並行できます。


## 使用例
READMEファイルの作成をLLMに頼むとき
タイピングに疲れた時
タイピングが苦手な方へ
気楽なメールを入力する際に



## 前提条件
* Python 3以降
* OPENAI API KEYを持っていること（無料で取得できます）
* 必要なpythonライブラリがあること（数は少ないです）

## 準備
### 準備1（インストール）
``` batch
git clone https://github.com/Jika-1366/WhisperTyping.git
cd WhisperTyping
```

### 依存関係
``` batch 
pip install pyaudio 
```

など


### 準備2(環境変数の登録とライブラリインストール)
システム環境変数またはユーザー環境変数にOpenAI APIキーを設定します:
export OPENAI_API_KEY='your_openai_api_key'

ここまでできたら、一度普通にpythonコード（main.py）を実行して、テストしてみてください。


### 準備3(ショートカットキー登録)
### ショートカットキーによる使用(windows)
プログラムをキーボードショートカットで起動するのが便利です。以下の手順で設定できます:
1. .batファイルを以下のように書きます。
``` batch
start /min cmd /c "C:/Users/user/anaconda3/envs/openinterpreter/python.exe c:/Users/user/original_programs/mine/projects/whisper_input2/main.py"
```
2. Pythonプログラムを起動するショートカットを作成します。
3. 作成したショートカットのプロパティを開き、「ショートカットキー」欄に Shift + Ctrl + V と入力します（VはVoiceのVです）。

## 機能
音声録音: 音声を録音し、.wavファイルとして保存します。
文字起こし: .wavファイルを.mp4に変換し、Whisper APIに送信して文字起こしを行います。
自動入力: Pythonを使用して、文字起こしされたテキストをキーボードライブラリで入力します。



## 各ファイルの説明
Main.py: 音声録音、文字起こし、入力を管理する中央スクリプト。
Head.py: Main.pyで使用されるヘルパー関数が含まれています。


## ご協力
コードの機能充実にご協力いただけますと大変幸いです。参考までに以下のような「to do」がございます。

## 予定(to do)
・OpenAIのwhisperには、固有名詞や特殊な単語を登録して聞き取り精度を向上させる機能がございますので、その機能を実装する予定です。
・また、これを骨組みに、バックグラウンドにLLMと対話できるサービスの開発も行う予定です。(GPT-4oが本格的に実装されればもう必要性はなくなりますが、そこまでのつなぎです)


## ライセンス
このプロジェクトはMITライセンスの下でライセンスされています。

