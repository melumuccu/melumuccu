# 主な成果物 (公開可能なもの)

## [mcp-notion](https://github.com/melumuccu/mcp-notion)

README参照

## [get-google-map-place-info](https://github.com/melumuccu/get-google-map-place-info)

README参照

## qrypto-ale シリーズ

- 仮想通貨の取引履歴を取引所のAPIで取得し、平均取得価額などを計算し表示するアプリケーション
    - 複数の取引所で一覧化したいため自作した
- 初見・知見が少ない技術の実験台として複数作成している
    - CLIとして単体で動作
        - ****[qrypto-ale-cli-nodejs-typescript](https://github.com/melumuccu/qrypto-ale-cli-nodejs-typescript)****
    - API
        - ****[qrypto-ale-api-sam-typescript](https://github.com/melumuccu/qrypto-ale-api-sam-typescript)****
        - ****[qrypto-ale-api-nodejs-express](https://github.com/melumuccu/qrypto-ale-api-nodejs-express)****
    - MobileApp(動作確認はiOSでのみ, 前述のAPIをcallする)
        - ****[qrypto-ale-mobileapp-typescript-angular](https://github.com/melumuccu/qrypto-ale-mobileapp-typescript-angular)****

## [python-openpyxl](https://github.com/melumuccu/python-openpyxl)

- 仮想通貨の取引履歴を出力したExcelファイルをPythonで加工するアプリケーション
- ほぼ同一時刻に取引された複数の取引記録を統合する処理をPythonとOpenPyXLで実装
    - 極めて短時間に少額の取引が実施されるのが視認性の低下に繋がっていたため
