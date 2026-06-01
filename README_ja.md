# fuzzy-equalizer
Reference MATLAB implementation of a fuzzy inference based audio equalizer.

[English README](README_en.md)

# ファジィ制御オーディオイコライザー
## MATLABリファレンス実装

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](
https://matlab.mathworks.com/open/github/v1?repo=HiroshiIwamura/fuzzy-equalizer&file=FEQU_v2.mlapp)

※  MATLAB Online の利用には無料の MathWorks アカウントが必要です。
MATLAB Onlineでは推論処理およびグラフ表示を試すことができます。
リアルタイム音声出力にはデスクトップ版 MATLAB と Audio Toolbox が必要です。

---

## 概要

本リポジトリは、ファジィ推論を用いたオーディオ信号処理技術のMATLAB実装です。

本技術は1989年に考案・特許出願されたものであり、本実装は発明者本人によるリファレンス実装です。

技術解説については以下の記事をご参照ください。

- https://note.com/leftbank/n/n2b16648c9b39

### デモ動画

- https://www.youtube.com/watch?v=ImQW7U3SLto
- https://www.youtube.com/watch?v=WyPJTxr6pvw

---

## 特徴

- ファジィ推論を用いたオーディオ信号処理
- 学習データ不要
- リアルタイム動作可能
- 低計算量
- リアルタイム推論グラフ表示
- Graph機能のON/OFF切替可能
- 推論機構と知識ベースを独立して扱える
- MATLAB Online上で推論処理およびグラフ確認が可能

近年の機械学習ベース手法とは異なり、本手法は学習を必要としないルールベースの推論方式です。

そのため計算量が小さく、リアルタイム処理や組み込み機器への実装にも適しています。

---

## 技術的背景

本手法は、ファジィ推論をオーディオ信号処理へ応用したものです。

一般的なDSPアルゴリズムでは、アルゴリズム構造そのものを変更しなければ特性を大きく変更できない場合が少なくありません。

一方、ファジィ推論では、

- 推論機構
- メンバーシップ関数
- IF-THENルール

を比較的独立して扱うことができます。

そのため、推論エンジンを変更することなく、知識ベースやルールセットを継続的に改善できる点が本手法の特徴です。

---

## 現在の位置付け

本リポジトリに含まれるMATLAB実装はリアルタイム動作可能な実装です。

また、発明者自身により、本技術をベースとしたJUCE/C++によるオーディオプラグイン実装も開発されています。

ただし、その実装は本リポジトリには含まれていません。

本実装は十分に動作するものですが、オーディオ信号処理の観点からは、ファジィルールやメンバーシップ関数についてさらなる検討や改良の余地があると考えています。

ファジィ推論の利点は、推論エンジンそのものを変更することなく、ルールや知識ベースを発展させられる点にあります。

そのため、本リポジトリは完成品というよりも、技術検証・研究・発展のためのリファレンス実装として公開しています。

---

## MATLAB Onlineについて

本リポジトリは MATLAB Online 上で実行できます。

MATLAB Online の利用には MathWorks アカウントが必要です。

- MathWorksアカウント（無料）で利用可能
- ソフトウェアのインストール不要
- 推論処理およびグラフ表示を試すことが可能

ただし、MATLAB Online では audioDeviceWriter が利用できないため、リアルタイム音声出力は行えません。

利用可能な機能：

- 推論処理の実行
- 推論結果の確認
- グラフ描画
- パラメータ変更による挙動確認

利用できない機能：

- リアルタイム音声再生
- オーディオデバイスへの出力

音声処理を実際に試す場合は、デスクトップ版 MATLAB と Audio Toolbox が必要です。

---

## 動作について

本実装では、音声再生と推論結果のリアルタイム描画を同時に行うことができます。

Graph機能は ON/OFF 可能です。

- Graph ON
  - 推論状態をリアルタイム表示
  - CPU負荷が増加
  - 実行環境によっては音切れが発生する場合がある

- Graph OFF
  - 描画処理を停止
  - CPU負荷を低減
  - より安定したリアルタイム動作が可能

作者の環境では、MATLABの新しいバージョンほど描画による音切れが発生しにくい傾向が確認されています。

例：
- MATLAB R2024a：Graph ON時に音切れが発生する場合がある
- MATLAB R2026a：同条件でも音切れは大幅に減少

結果はPC性能や実行環境に依存します。

---

## スクリーンショット
<img width="1602" height="989" alt="capture_002_26012024_110936" src="https://github.com/user-attachments/assets/a98d14e1-f9c2-4859-9c32-fda53640fe0d" />
<img width="840" height="900" alt="fuzzy" src="https://github.com/user-attachments/assets/547a9884-1038-47ea-bddc-6958800bb886" />


※ JUCE/C++による実装例（本リポジトリには含まれていません）
<img width="802" height="528" alt="FEQU_VST" src="https://github.com/user-attachments/assets/13ac1c8a-b1a5-47dc-9fd9-5c2c474a59a9" />

---

## 動作環境

- MATLAB R2023a以降
- Audio Toolbox（リアルタイム音声処理を行う場合）

---

## 使用方法

1. 本リポジトリをダウンロードまたはクローン
2. MATLABで開く
3. FEQU_v2(.mlapp) を実行
4. 任意の音源を読み込む（2chステレオ）
5. パラメータを調整しながら処理結果を確認

---

## サポートについて

本リポジトリは技術資料およびリファレンス実装として公開しています。

不具合修正、機能追加、Pull Requestのレビュー等を保証するものではありません。

---

## お問い合わせ

技術的な議論、共同研究、ライセンスおよび商用利用に関するお問い合わせは下記までご連絡ください。

AudiiSion Sound Lab.
https://www.audiision.com/

---

## ライセンス

MIT License

Copyright (c) 2026 Hiroshi Iwamura

詳細は LICENSE ファイルをご参照ください。
