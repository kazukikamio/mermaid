```mermaid
sequenceDiagram
    participant U as ユーザー
    participant P as MyPalette
    participant S as MyGPTシステム
    participant G as GPT

    U->>P: MyPaletteを開く
    U->>P: 「MyGPT取得」押下
    P->>S: MyGPT一覧取得
    S-->>P: 最新MyGPT一覧
    P-->>U: 登録完了表示

    U->>P: MyGPTを選択
    U->>P: お気に入り追加
    U->>P: 「開く」押下
    P->>G: GPT起動
    G-->>U: 利用開始

    %% Styling
    participant U fill:#E3F2FD,stroke:#1E88E5,color:#0D47A1
    participant P fill:#FFF9C4,stroke:#F9A825,color:#F57F17
    participant S fill:#C8E6C9,stroke:#43A047,color:#1B5E20
    participant G fill:#FFCC80,stroke:#FB8C00,color:#E65100

