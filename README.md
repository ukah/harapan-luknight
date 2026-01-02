# パンチアニメ（クリックで再生）サンプル

準備:

- `punch.gif` を用意してください（アニメーションGIF）。
- `punch_static.png` は不要です。ページ読み込み時に `punch.gif` の1フレーム目を自動的に静止画として生成します。
- 上記をこのフォルダ（`examples/punch/`）に置きます。

使い方:

1. ローカルで確認するには、このフォルダで簡易HTTPサーバを起動します。

```bash
python3 -m http.server 8000
```

2. ブラウザで `http://localhost:8000/` を開き、`index.html` を表示します。

動作:

- ページ読み込み時に `punch.gif` を読み込み、最初のフレームをキャンバスへ描画して `data:` URL に変換します。
- 最初は自動生成した静止画（または `punch_static.png` のフォールバック）を表示します。
- 画像をクリックすると `punch.gif` に切り替わり、`gifDuration` (index.html内で設定) ミリ秒後に静止画に戻ります。

注意:

- GIFが別オリジンの場合、ブラウザのセキュリティによりキャンバスへの書き出しが失敗することがあります。その場合は `punch_static.png` を用意してください。
- GIFの実際の再生時間に合わせて `gifDuration` を調整してください。
# パンチアニメ（クリックで再生）サンプル

準備:

- `punch.gif` を用意してください（アニメーションGIF）。
- `punch_static.png` を用意してください（GIFの1コマ目などの静止画）。

使い方:

1. ローカルで確認するには、このフォルダで簡易HTTPサーバを起動します。

```bash
python3 -m http.server 8000
```

2. ブラウザで `http://localhost:8000/` を開き、`index.html` を表示します。

動作:

- 最初は `punch_static.png` を表示します。
- 画像をクリックすると `punch.gif` に切り替わり、`gifDuration` (index.html内で設定) ミリ秒後に静止画に戻ります。

注意:

- GIFが無限ループの場合でも `index.html` の `setTimeout` により静止画に戻ります。
- GIFの実際の再生時間に合わせて `gifDuration` を調整してください。
