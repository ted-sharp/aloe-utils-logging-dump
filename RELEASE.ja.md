# リリースノート

## [1.1.0] - 2025-05-26
### 変更点
- ダンプ出力フォーマットを改善しました。
  - 各行に以下の情報が含まれるようになりました：
    - **オフセット**: バイト配列内の位置（16進数）
    - **16進数値**: 16バイトごとにグループ化された生のバイト値
    - **ASCII表現**: 印字可能な文字はそのまま表示、印字不可能な文字は`.`で表示

#### 新しいフォーマット:

```
00000000 | 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F | 0123456789ABCDEF
-------- | -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- | ----------------
00000000 | 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F | ................
00000010 | 10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F | ................
```

#### 旧フォーマット:

```
00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F
```

## [1.0.0] - 2025-05-17
### 追加
- 初回リリース
- バイナリデータを16進数形式で出力する`DumpDebug(this ILogger logger, byte[] bytes)`メソッドを追加 