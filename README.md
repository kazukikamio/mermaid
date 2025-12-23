'''mermaid
flowchart TD
  %% =========================
  %% ノード定義
  %% =========================
  A([開始])
  B[申請者：申請作成]
  C{必須項目\nチェック}
  D[差戻し\n修正依頼]
  E[自動チェック\n予算・重複]
  F{チェックOK？}
  G[一次承認]
  H{承認OK？}
  I[二次承認]
  J{金額大？}
  K[発注処理]
  L[納品]
  M[検収]
  N{検収OK？}
  O[支払処理]
  Z([終了])

  %% =========================
  %% フロー
  %% =========================
  A --> B --> C
  C -- NG --> D --> B
  C -- OK --> E --> F
  F -- NG --> D
  F -- OK --> G --> H
  H -- NG --> D
  H -- OK --> J
  J -- Yes --> I --> K
  J -- No --> K
  K --> L --> M --> N
  N -- NG --> L
  N -- OK --> O --> Z

  %% =========================
  %% 色・スタイル定義
  %% =========================
  classDef startEnd fill:#2ecc71,color:#fff,stroke:#1e8449,stroke-width:2px;
  classDef user fill:#3498db,color:#fff,stroke:#21618c;
  classDef system fill:#95a5a6,color:#000,stroke:#7f8c8d;
  classDef approval fill:#f1c40f,color:#000,stroke:#b7950b;
  classDef exception fill:#e74c3c,color:#fff,stroke:#922b21;
  classDef finance fill:#9b59b6,color:#fff,stroke:#6c3483;

  %% =========================
  %% クラス適用
  %% =========================
  class A,Z startEnd
  class B user
  class E,K,L,M,O system
  class G,I approval
  class D exception
  class C,F,H,J,N finance
