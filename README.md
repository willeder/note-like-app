開発スケジュール提案書（ギャンブル特化型投稿サービス）
スケジュール概要（マイルストーン方式 / 余裕を持った構成）
フェーズ	期間	主な内容
Phase 0：要件定義・構成設計	0.5ヶ月	ペルソナ / 投稿・購入フロー / 通知・クレジット方針設計
Phase 0.5：UI/UXデザイン	1ヶ月	全主要画面のデザイン（Figma） / モバイル対応 / コンポーネント設計
Phase 1：MVP開発	3ヶ月	以下の全機能を含む：
投稿・購入（有料/無料）
Stripe決済＋クレジットカード登録
閲覧制御（購入者のみ全文）
締切設定・締切通知
クレジット（残高確認ページ／返還履歴ページ／使用履歴ページ）
売上管理・引き出し申請
SNS連携（X/Twitter API）
レスポンシブUI / SEO / 管理画面
購入済み記事一覧やマイページ中心のUX導線に最適化
Phase 1（MVP）機能一覧
カテゴリ	機能
投稿	記事作成（有料/無料・締切設定）／公開設定
閲覧制御	ロック表示／購入ユーザーのみに全文表示
決済	Stripe即時決済＋クレジットカード登録＋手数料控除
通知	締切前通知（メール）／通知タイミング設定
クレジット	クレジット残高表示ページ／返還履歴ページ／使用履歴ページ
売上管理	投稿別売上表示／収益ダッシュボード
引き出し	銀行口座 / PayPalなどへ申請制で対応
SNS連携	X（旧Twitter）自動投稿API連携
SEO / UX	モバイル最適化／OGP／シンプルUI設計／購入済み記事一覧・マイページ中心導線
管理機能	投稿一覧／ユーザー一覧／簡易BAN管理
想定工数（MVP対応）
担当	工数（人日）	備考
PM	約22人日	要件整理・進行管理・調整含む
SE	約75人日	フロント・バック・通知・SNS・クレジット・カード登録まで対応
デザイナー	約25〜30人日	UI設計・スマホUI・管理画面など含む
※ デザイン期間を1ヶ月に設定しており、1人がフル稼働する想定。2人以上で並行する場合は短縮可能。

提案の強みと方針
MVPにおいて「投稿→購入→締切通知→外れたらクレジット返還→売上管理→引き出し」までのフローをすべてカバー。
ギャンブル情報の性質に合わせて「締切通知」と「信頼性（返還）」を初期から実装。
note/bookersとの差別化として、リアルタイム性 × 信頼性 × 実績の可視化 を軸に構築。
ユーザーに優しい導線設計として、「マイページ中心構造」「購入済み記事一覧」「通知・履歴ページ」「カード登録管理ページ」などを初期から組み込み。
今後の展望（Phase 2以降）
的中率・回収率・投稿者ランキング
Push通知 / LINE通知連携
プレミアム会員プラン・サブスク機能
フォロー・タイムライン型のUI拡張
ページ遷移図（Mermaid構文）
flowchart TD

%% ユーザー側
U_Login[ログイン]
U_MyPage[マイページ]
U_ArticleList[記事一覧]
U_ArticleDetail[記事詳細]
U_ArticlePost[記事投稿]
U_Purchase[記事購入]
U_Purchased[購入済み記事一覧]
U_Notification[通知設定・履歴]
U_Profile[プロフィール編集]
U_CreditBalance[クレジット残高]
U_CreditRefund[返還履歴]
U_CreditUsage[使用履歴]
U_Sales[売上管理]
U_Withdraw[引き出し申請]
U_CardRegister[カード登録・管理]

U_Login --> U_MyPage
U_MyPage --> U_ArticleList
U_MyPage --> U_Purchased
U_MyPage --> U_Notification
U_MyPage --> U_Profile
U_MyPage --> U_CreditBalance
U_CreditBalance --> U_CreditRefund
U_CreditBalance --> U_CreditUsage
U_MyPage --> U_Sales
U_Sales --> U_Withdraw
U_MyPage --> U_CardRegister

U_ArticleList --> U_ArticleDetail
U_ArticleDetail --> U_Purchase
U_MyPage --> U_ArticlePost

%% 管理者側
A_Login[管理者ログイン]
A_Dashboard[管理者ダッシュボード]
A_Articles[投稿一覧]
A_Users[ユーザー一覧]
A_BAN[ユーザーBAN管理]
A_WithdrawAdmin[出金申請管理]

A_Login --> A_Dashboard
A_Dashboard --> A_Articles
A_Dashboard --> A_Users
A_Users --> A_BAN
A_Dashboard --> A_WithdrawAdmin
Some content has been disabled in this document
