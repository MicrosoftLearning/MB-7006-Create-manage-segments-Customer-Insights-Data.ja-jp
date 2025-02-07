---
lab:
  title: 'ラボ 1: データセットを取り込む'
---

# ラボ 1: データセットを取り込む
このラボでは、以下の方法について説明します。
- PowerQuery を使用して複数のデータセットを取り込む
- データセットを変換して列の型を変更する
- インポートの状態を監視する

セグメントを作成するには、まずセグメントで使用するデータをインポートする必要があります。 このラボでは、データを統合してセグメントを構築するための前提条件として、いくつかのデータセットをインポートします。

## 演習 1: データ ソースを取り込む
このガイド付きプロジェクトでは、さまざまなデータ ソースをインポートする必要があります。 このデータ ソースは、統合顧客プロファイルの作成に使用されます。

### タスク 1: 顧客データを電子商取引プラットフォームから取り込む
1. **Customer Insights - Data** で、左側のナビゲーション メニューの **[データ]** を展開し、**[データ ソース]** を選択します。

1. **データ ソースの追加**を選択します。 データを取り込むための使用可能な方法を表示します。 このラボでは、**[Microsoft Power Query]** を選択し、ソースの名前を「**eCommerce**」と設定し、**[次へ]** を選択します。

1. **Customer Insights** が取り込むことのできる **Power Query データ ソース**のビューが表示されます。 使用可能なコネクタのタイプを確認します。 **テキスト/CSV** コネクタを選択します。

1. **[ファイルのパスまたは URL]** に「`https://aka.ms/CI-ILT/Contacts`」と入力し、**[次へ]** を選択します。 データのアップロードに少し時間がかかる場合があります。

1. ソースのデータが表形式で表示されています。 **[データの変換]** を選択して、取り込むデータのデータ型と形式を構成します。

1. データの最初の行に列見出しが表示されていることに注目してください。 これを修正するには、**[ホーム]** タブで **[変換]、[1 行目をヘッダーとして使用]** の順に選択するか、**[変換]** タブを選択して **[1 行目をヘッダーとして使用]** を選択します。

1. **テキスト/CSV ソース**からデータを取り込んだので、すべての列は、既定の "テキスト" という**データ型**になります。 データを正常に取り込み、モデル化するために、テキスト以外の列のデータ型を設定できます。

1. データ型を変更するには、列見出し内の **ABC** アイコンを選択します。 次の列のデータ型を更新します。
    - **DateOfBirth**: 日付
    - **CreatedOn:** 日付
    - **Income:** 通貨

1. **[クエリの設定]** ウィンドウの「**名前**」フィールドが、**[連絡先]** に設定されていることを確認します。 [**次へ**] を選択します。

1. **[手動で更新]** を選択し、**[保存]** を選択します。

お疲れさまでした。 これで、データ セットを使用して最初のデータ ソースが正しく作成されました。 次のタスクでは、次のデータ セットのインポートを続けます。

### タスク 2: ロイヤルティ スキームから顧客データを取り込む
1. **Customer Insights** で、左側のメニューの **[データ]** を展開し、**[データ ソース]** を選択します。

1. **[+ データ ソースの追加]** を選択し、インポート方法として **[Microsoft Power Query]** を選択します。 ソースの名前を「**ロイヤルティ**」と設定し、**[次へ]** を選択します。

1. **テキスト/CSV** コネクタを選択します。

1. **[ファイル パスまたは URL]** に「`https://aka.ms/CI-ILT/LoyaltySchemeCustomers`」と入力し、**[次へ]** を選択し、**[データの変換]** を選択します。

1. 前と同様に、**[変換]**、**[1 行目をヘッダーとして使用]** の順に選択します。

1. 次の列のデータ型を更新します。
    - **DateOfBirth**: 日付
    - **RewardPoints:**: 整数
    - **CreatedOn:** 日付

1. **[クエリの設定]** ウィンドウでこのクエリの名前を「**顧客**」に変更し、**[次へ]** を選択します。

1. **[手動で更新]** を選択し、**[保存]** を選択します。

### タスク 3: 販売時点管理の購入から顧客データを取り込む
1. **Customer Insights** で、左側のナビゲーション メニューの **[データ]** を展開し、**[データ ソース]** を選択します。

1. **[+ データ ソースの追加]** を選択し、**[Microsoft Power Query]** を選択して、ソースの名前を「**POS**」と設定し、**[次へ]** を選択します。

1. **テキスト/CSV** コネクタを選択します。

1. **[ファイル パスまたは URL]** に「`https://aka.ms/CI-ILT/POSPurchases`」と入力します。 [**[次へ]** を選択し、**[データの変換]** を選択します。

1. 前と同様に、**[変換]**、**[1 行目をヘッダーとして使用]** の順に選択します。

1. 次の列のデータ型を更新します。
    - **PurchasedOn:**: 日付
    - **TotalPrice**: 通貨
    - **RewardPointsAdded:** 整数

1. **[クエリの設定]** ウィンドウの「**名前**」フィールドで、クエリの名前を「**購入**」に変更します。

1. [**次へ**] を選択します。

1. **[手動で更新]** を選択し、**[保存]** を選択します。

### タスク 4: オンライン購入データを取り込む
1. このタスクでは、**Contoso Coffee** の Web サイトで行われた購入を表す**オンライン購入**データを取り込みます。

1. **Customer Insights** で、左側のメニューの **[データ]** を展開し、**[データ ソース]** を選択します。 (**eCommerce** データ ソースの状態が **[成功]** になっていることを確認します。)

1. 最初のタスクで作成した **eCommerce** データ セットを選択し、**[編集]** を選択します。 データがまだ更新されている場合は、完了するまで待ってから編集する必要があります。

1. [**次へ**] を選択します。 

1. タスク 1 で取り込んだ **eCommerce Contacts** データの **Power Query** ビューが表示されます。 **[ホーム]** タブで、**[データを取得]** を選択します。

1. **Customer Insights** が取り込むことのできるデータ ソース コネクタのビューが表示されます。 **[テキスト/CSV]** を選択します。

1. **[ファイル パスまたは URL]** に「`https://aka.ms/CI-ILT/OnlinePurchases`」と入力し、**[次へ]** を選択します。 **［作成］** を選択します

1. 前と同様に、**[変換]**、**[1 行目をヘッダーとして使用]** の順に選択します。

1. 次の列のデータ型を更新します。
    - **PurchasedOn:**: 日付
    - **TotalPrice**: 通貨

1. このクエリに **Purchases** という名前を付け、**[保存]** を選択します。

**重要:** すべてのデータ ソースの状態が **[成功]** になってから、次の演習に進んでください。
