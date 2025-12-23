```mermaid
%%{init: {'theme':'base','themeVariables':{
  'primaryColor':'#E3F2FD','primaryTextColor':'#0D47A1','primaryBorderColor':'#0D47A1',
  'secondaryColor':'#E8F5E9','secondaryTextColor':'#1B5E20','secondaryBorderColor':'#1B5E20',
  'tertiaryColor':'#FFF3E0','tertiaryTextColor':'#E65100','tertiaryBorderColor':'#E65100',
  'lineColor':'#546E7A','textColor':'#263238'
}}}%%
flowchart TB
  %% ===== Analysis Objectives =====
  A0([Start]):::startend
  A1["分析テーマ①<br/>有償サポートプラン導入に向けた<br/>高ARPU層の感度分析"]:::primary
  A2["分析テーマ②<br/>コールセンターの品質価値（ROI）の再定義<br/>（コスト→利益貢献）"]:::primary
  A3["対象：高ARPU顧客（ARPU ≥ 1万円）"]:::secondary
  A4["想定：次期有償サポート（月額 ≥ 1万円）S-IN検討"]:::secondary

  %% ===== Core Variables / Metrics =====
  B1["応対品質（Quality）"]:::tertiary
  B2["継続率 / 解約抑止（Retention / Churn）"]:::tertiary
  B3["顧客ロイヤルティ（Loyalty）"]:::tertiary
  B4["LTV（顧客生涯価値）"]:::tertiary
  B5["コールセンターROI<br/>（品質→Loyalty→LTV→収益）"]:::secondary

  %% ===== Hypotheses (Goodman) =====
  H0{"仮説検証<br/>（グッドマンの法則適用）"}:::decision

  H1["仮説①<br/>優れた問題解決は<br/>トラブル未経験以上にロイヤルティを高める"]:::primary
  H1a["条件：迅速かつ期待以上の解決"]:::secondary
  H1b["期待効果：解約率低下"]:::secondary

  H2["仮説②<br/>解約顧客の多くは<br/>直近で接触していない層"]:::primary
  H2a["条件：直近3ヶ月<br/>接触履歴なし / 接触断念"]:::secondary
  H2b["期待効果：解約母集団の主要層"]:::secondary

  H3["仮説③<br/>高満足のトラブル解決は<br/>家族契約・副商材意向も向上"]:::primary
  H3a["効果①：本人の継続利用意向↑"]:::secondary
  H3b["効果②：家族契約意向↑"]:::secondary
  H3c["効果③：副商材契約意向↑"]:::secondary

  %% ===== Outputs / Implications =====
  O1["定量化：応対品質 × 継続率の相関<br/>（高ARPU層）"]:::secondary
  O2["可視化：品質→ロイヤルティ→LTVの影響"]:::secondary
  O3["示唆：コールセンターは<br/>投資価値のある機能"]:::primary
  O4["結論（仮説成立時）<br/>顧客は“問題解決”だけでなく<br/>“気持ちの理解”を求める"]:::tertiary
  A9([End]):::startend

  %% ===== Flow =====
  A0 --> A1 --> A3
  A0 --> A2 --> A4

  A3 --> B1
  B1 --> B2
  B1 --> B3 --> B4 --> B5

  A1 --> O1
  A2 --> O2

  O1 --> H0
  O2 --> H0

  H0 --> H1 --> H1a --> H1b --> B3
  H0 --> H2 --> H2a --> H2b --> B2
  H0 --> H3 --> H3a
  H3 --> H3b
  H3 --> H3c

  B2 --> O3
  B5 --> O3
  O3 --> O4 --> A9

  %% ===== Styles =====
  classDef startend fill:#FFFFFF,stroke:#546E7A,color:#263238,stroke-width:1px;
  classDef primary fill:#E3F2FD,stroke:#0D47A1,color:#0D47A1,stroke-width:1.2px;
  classDef secondary fill:#E8F5E9,stroke:#1B5E20,color:#1B5E20,stroke-width:1.1px;
  classDef tertiary fill:#FFF3E0,stroke:#E65100,color:#E65100,stroke-width:1.1px;
  classDef decision fill:#FFFFFF,stroke:#0D47A1,color:#0D47A1,stroke-width:1.2px,stroke-dasharray: 4 2;
