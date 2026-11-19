# nro-user-tools

国立天文台 野辺山宇宙電波観測所の 利用者向けのツールの**運用リポジトリ**です。観測所でこの装置群をどう使い、どう保守しているかを集めます。文脈基盤のハブ [nro-context](https://github.com/nobeyama-radio-observatory/nro-context) から参照されます。

扱うもの：観測指示書の作成ソフト、解析ソフト（NEWSTAR、NOSTAR、cont、CASA の形式への書き出し）

## 位置づけ

文脈基盤では、装置の情報を次の四つの層に分けて置きます（ハブの判断記録 [0006](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/decisions/0006-資産の情報を装置群ごとの運用リポジトリに置く.md)）。参照は上の層から下の層へだけ行います。

```
ハブ（nro-context）→ 運用（このリポジトリ）→ 製品 → 開発
```

- **このリポジトリが正本のもの：** 台帳（構成、依存関係、提供の状態、保守の状況、更新の見込み、担い手の数）、運用と保守の文書、聞き取りの記録。
- **製品と開発のリポジトリ：** 観測系のインターフェース仕様の [nro45-interfaces](https://github.com/nobeyama-radio-observatory/nro45-interfaces)（ハブの判断記録 0013）と、観測指示書の書き換えの開発の [tz230-firstlight](https://github.com/ars096/tz230-firstlight)。台帳の `repos` から参照します。

## 中身

| 場所 | 中身 |
|---|---|
| [assets.yaml](assets.yaml) | 台帳。項目の定義はハブの [assets/README.md](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/assets/README.md) |
| [interviews/](interviews/README.md) | 聞き取りの記録。公開資料にない値（保守の手間、担い手の数、更新の見込みなど）の出典 |

台帳の id の置き場所は、ハブの[資産の索引](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/assets/README.md)で引けます。`nro45m`（アンテナ）は [nro-45m-antenna](https://github.com/nobeyama-radio-observatory/nro-45m-antenna) にあります。

## 進め方

進め方の決まりの正本は、ハブの [CONTRIBUTING.md](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/CONTRIBUTING.md) です。とくに次を守ってください。

- 機微情報を入れない。制御の手順、接続先、ネットワーク構成、アクセスの方式は、既存の非公開の場所に置いたままにする。利用者向けのツールはこれらが入りやすいので、とくに気をつける。
- 主ブランチに直接書き込まず、プルリクエストを出す。AI が作ったものにはラベル `AI作成` を付ける。
- 事実には出典を添える。出典を示せない事実は仮説として扱う（ハブの判断記録 [0004](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/decisions/0004-事実の根拠は出典で示す.md)）。

担当：計算機グループ（[聞き取り 2026-11-18](https://github.com/nobeyama-radio-observatory/nro-data/blob/main/interviews/2026-11-18.md) 問1）

## 利用許諾

- コード：BSD 3-Clause License（[LICENSE](LICENSE)）
- 文書：クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0、[LICENSE-docs](LICENSE-docs)）
