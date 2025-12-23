```mermaid
flowchart LR
    A[MyPaletteを開く] --> B[MyGPT取得ボタン押下]
    B --> C[MyGPT自動更新]
    C --> D[登録完了]

    D --> E[よく使うMyGPT選択]
    E --> F[お気に入り追加]
    F --> G[開くボタン押下]
    G --> H[GPT起動]

    %% Styling
    style A fill:#E3F2FD,stroke:#1E88E5,stroke-width:2px,color:#0D47A1
    style B fill:#BBDEFB,stroke:#1E88E5,stroke-width:2px,color:#0D47A1
    style C fill:#C8E6C9,stroke:#43A047,stroke-width:2px,color:#1B5E20
    style D fill:#A5D6A7,stroke:#43A047,stroke-width:2px,color:#1B5E20
    style E fill:#FFF9C4,stroke:#F9A825,stroke-width:2px,color:#F57F17
    style F fill:#FFE082,stroke:#F9A825,stroke-width:2px,color:#F57F17
    style G fill:#FFCC80,stroke:#FB8C00,stroke-width:2px,color:#E65100
    style H fill:#FFAB91,stroke:#E64A19,stroke-width:2px,color:#BF360C
