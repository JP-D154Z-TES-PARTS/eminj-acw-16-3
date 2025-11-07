# l_mat.c 仕様書対応マップ

作成日: 2025-11-07

## 概要

このドキュメントは、baseフォルダの仕様書とl_mat.cソースコードの対応関係を示すマッピング情報です。

## 仕様書情報

- **仕様書ファイル**: `ロジック変更シート_ver9.09_eminj.xlsx`
- **対象シート**: acw-15-c-t
- **モジュール名**: eminj-acw-15-c-t

### 変更理由

納入後マイナー(機能変更なし)
(7)仕様確認書対応(DENG-STD-25013,DENG-STD-25017,DENG-STD-25026)
　 ①誤記修正
　 ②記述整理


### ロジックの狙い

(7)仕様確認書対応(DENG-STD-25013,DENG-STD-25017,DENG-STD-25026)

　 ①誤記修正

　　・Word仕様書

　　　- Ａ.１.機能の「ポンプ、」「要求」を削除(DENG-STD-25013①)

　　　- Ｄ.２-２-２.(3)の「…PRINORQ(0))、かつ…」を「…PRINORQ(0))、または…」に修正

## ソースコード情報

- **ソースファイル**: `eminj_l_mat.c`
- **総行数**: 4962
- **パブリック関数数**: 4
- **スタティック関数数**: 12

## パブリック関数一覧と詳細

### 1. vdg_eminj_pwon

- **行番号**: 721
- **呼出タイミング**: 
- **機能**: 
- **関数本体の長さ**: 約500行

#### 機能概要

```c
#define u1s_EMINJ_EMINJST_NUM2  ((u1)((u1)(sizeof(sts_eminj_eminjst_tbl2)/sizeof(sts_eminj_eminjst_tbl2[0])) - (u1)1))   /* lsb=256/256,unit= :nvDxvf -1DUMMY */
#define u1s_EMINJ_EMINJAST_NUM  ((u1)((u1)(sizeof(sts_eminj_eminjast_tbl)/sizeof(sts_eminj_eminjast_tbl[0])) - (u1)1))   /* lsb=256/256,unit= :nvDxvf -1DUMMY */
#define u1s_EMINJ_EMINJAST_NUM2 ((u1)((u1)(sizeof(sts_eminj_eminjast_tbl2)/sizeof(sts_eminj_eminjast_tbl2[0])) - (u1)1)) /* lsb=256/256,unit= :nvDxvf -1DUMMY */

/*-------------------------------------------------------------------*/
/* ֐                                                              */
/*-------------------------------------------------------------------*/
/*********************************************************************/
/*  ֐        | vdg_eminj_pwon( )                                */
/*  e      | lݒ                                       */
/*  ^C~O| pwon                                             */
/*            | Ȃ                                             */
/*  ߂l        | Ȃ                                             */
/*  ӎ      |                                                  */
/*********************************************************************/
```

#### 主要な処理

```c
vdg_ebinjctr_ebinjctr_dataget( &stt_binjctrdat );   /* f[^擾 */
vds_eminj_einj_dataset( &stg_eminj_einj, &stt_injdat, (u1)ON );
vds_eminj_eminj_dataset( &stg_eminj_eminj, &stt_injdat2, (u1)ON );
vdg_eminj_8msm( void )
```

#### 仕様書との対応

- 仕様書セクション: [TODO: 詳細分析が必要]
- 実装している仕様項目: [TODO: 詳細分析が必要]

---

### 2. vdg_eminj_8msm

- **行番号**: 814
- **呼出タイミング**: 
- **機能**: 
- **関数本体の長さ**: 約12行

#### 機能概要

```c
    /* f4s_eminj_eminj_einjend_mońAf4g_eminj_einjendőp\ */

    /* l0ϐ́Aj^ϐւ̊i[sv */

#endif /* M_EMINJ */
}

/*********************************************************************/
/*  ֐        | vdg_eminj_8msm( )                                */
/*  e      | ˗v̒⏈                               */
/*  ^C~O| 8msm                                             */
/*            | Ȃ                                             */
/*  ߂l        | Ȃ                                             */
/*  ӎ      |                                                  */
/*********************************************************************/
```

#### 仕様書との対応

- 仕様書セクション: [TODO: 詳細分析が必要]
- 実装している仕様項目: [TODO: 詳細分析が必要]

---

### 3. vdg_eminj_einj_dataget

- **行番号**: 2604
- **呼出タイミング**: 
- **機能**: 
- **関数本体の長さ**: 約115行

#### 機能概要

```c
    /* ˂r`b̊mO˗vXV */
    /* {́A{ȋSĂ̂W^XN{ɍs */
    vdg_ainjif_renew_injrq();
}

/*********************************************************************/
/*  ֐        | vdg_eminj_einj_dataget( )                        */
/*  e      | ˏ擾                                 */
/*  ^C~O| v                                       */
/*            | ptt_retval:ˏ擾obt@̃AhX        */
/*  ߂l        | Ȃ                                             */
/*  ӎ      |                                                  */
/*********************************************************************/
```

#### 仕様書との対応

- 仕様書セクション: [TODO: 詳細分析が必要]
- 実装している仕様項目: [TODO: 詳細分析が必要]

---

### 4. vdg_eminj_eminj_dataget

- **行番号**: 2730
- **呼出タイミング**: 
- **機能**: 
- **関数本体の長さ**: 約108行

#### 機能概要

```c
#if JEEFI != u1g_EJCC_D4        /*yD-4ȊOz*/
    ptt_retval->s2_ek1fpt = stg_eminj_einj.s2_ek1fpt;
    ptt_retval->f4_ek1fpt = stg_eminj_einj.f4_ek1fpt;
#endif /* JEEFI */
    glint_ei();       /* m I */
}

/*********************************************************************/
/*  ֐        | vdg_eminj_eminj_dataget( )                       */
/*  e      | ˏ擾i\2j                      */
/*  ^C~O| v                                       */
/*            | ptt_retval:ˏ擾obt@̃AhX        */
/*  ߂l        | Ȃ                                             */
/*  ӎ      | V\̗p                                       */
/*********************************************************************/
```

#### 仕様書との対応

- 仕様書セクション: [TODO: 詳細分析が必要]
- 実装している仕様項目: [TODO: 詳細分析が必要]

---

## スタティック関数一覧

以下は、パブリック関数から呼び出される内部ヘルパー関数です。

1. **vds_eminj_eminj_hpri** (行 680, 戻り値型: void)
2. **vds_eminj_eminjlmt_hpri** (行 681, 戻り値型: void)
3. **vds_eminj_einj_dataset** (行 682, 戻り値型: void)
4. **vds_eminj_einj_datacopy** (行 683, 戻り値型: void)
5. **vds_eminj_eminj_dataset** (行 684, 戻り値型: void)
6. **vds_eminj_einj_datacopy2** (行 685, 戻り値型: void)
7. **vds_eminj_einj_dataconv** (行 686, 戻り値型: void)
8. **vds_eminj_einj_dataconv_rev** (行 687, 戻り値型: void)
9. **vds_eminj_erestahot_rap_dataget** (行 689, 戻り値型: void)
10. **vds_eminj_erdpn_rap_dataget** (行 692, 戻り値型: void)
11. **vds_eminj_dummy_emedi_dataget** (行 694, 戻り値型: void)
12. **vds_eminj_dummy_emedi_dataget2** (行 695, 戻り値型: void)

## 関数呼び出しフロー

### メイン処理フロー

```
1. vdg_eminj_pwon() - 初期化 (pwon時)
   └─ 初期値設定、データ構造の初期化

2. vdg_eminj_8msm() - 噴射要求の調停処理 (8msm時)
   ├─ 各種データ取得
   ├─ 優先度判定
   └─ 噴射パラメータ決定

3. vdg_eminj_einj_dataget() - 噴射情報取得
   └─ 外部からのデータ取得インターフェース

4. vdg_eminj_eminj_dataget() - 噴射情報取得(構造体2用)
   └─ 新構造の外部データ取得インターフェース
```

## 重要なデータ構造

### st_EMINJ_EINJ
- 旧構造の噴射情報を格納
- パブリック変数: `stg_eminj_einj`

### st_EMINJ_EMINJ
- 新構造の噴射情報を格納
- パブリック変数: `stg_eminj_eminj`

## 計算式とアルゴリズム

### 主要な計算

1. **噴射量補正係数 (KRICHX)**
   - LSB: (32*2)/128/256
   - 初期値: EMINJ_KRICHI
   - 変換式: `f4 = s2 * ((32.*2.)/128./256.)`

2. **ポート噴射量算出係数 (KPFI)**
   - LSB: (1*4)/128/256, 単位: 倍
   - PORTモード時: 1.0
   - 非PORTモード時: 0.0

3. **噴射終了時刻 (EINJEND)**
   - LSB: 1024/128/256
   - ebinjctr モジュールから取得

## 条件コンパイルとバリエーション

以下のマクロによって機能が切り替わります:

- `JEEFI`: 噴射方式 (PORT, DUAL, D4)
- `JEPRDEMAND`: 可変燃圧制御の有無
- `JESS`: アイドルストップ機能の有無
- `JEALLHV_E`: ハイブリッド仕様
- `JEEGMG_E`: EG-MG連携仕様

## 仕様書セクションとコードの対応表

| 仕様書セクション | 対応する関数 | コード行番号 | 備考 |
|------------------|--------------|--------------|------|
| A.1. 機能 | vdg_eminj_pwon | 721-804 | 初期化処理 |
| D.1. 噴射要求調停 | vdg_eminj_8msm | 814-2603 | メイン処理 |
| D.2-2-1. 優先度判定 | vds_eminj_eminj_hpri | (static) | 優先度比較 |
| D.2-2-2. 制限付き判定 | vds_eminj_eminjlmt_hpri | (static) | 制限考慮判定 |
| E. データ取得I/F | vdg_eminj_einj_dataget | 2604-2729 | 外部I/F |
| E. データ取得I/F(新) | vdg_eminj_eminj_dataget | 2730-2854 | 外部I/F(新構造) |

## 処理フロー詳細

### 噴射要求調停処理のフロー (vdg_eminj_8msm)

```
1. 初期化・前提条件チェック
   - NE同期タスク完了フラグ確認
   - 噴射無効フラグ確認

2. 各種補正係数の算出
   - バンク別噴射量補正係数 (KRICHXBCRT)
   - 総合噴射量補正係数 (KRICHX)
   - ポート噴射係数 (KPFI)

3. 要求データの取得
   - 各機能モジュールからの噴射要求データ取得
   - データバッファへの格納

4. 優先度による調停
   - 優先度テーブルに基づく比較
   - 最高優先度の要求選択
   - 制限条件の考慮

5. 噴射パラメータの決定
   - 噴射量、噴射時期の確定
   - データ構造への格納
   - 外部モジュールへの通知
```

## 注意事項

1. **優先度テーブル**: `sts_eminj_eminj_tbl` および `sts_eminj_eminjlmt_tbl` で定義
2. **データ取得関数**: 多数の外部モジュールから `vdg_*_emedi_dataget()` を呼び出し
3. **割り込み制御**: `glint_di()` / `glint_ei()` で排他制御
4. **構造体2対応**: 新旧2つのデータ構造を並行管理

## 次のステップ (sub4用)

このマッピング情報を基に、以下の作業を実施します:

1. 仕様書の差分抽出
2. 対応するコード箇所の特定
3. 差分のコードへの反映
4. テストケースの作成と検証

---

このドキュメントは自動生成されたものです。詳細な仕様理解のためには、
元の仕様書とソースコードを直接参照してください。
