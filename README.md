
## Setup

```
$ npm install
```

## Run

```
$ node server.js
```

## Test

### Curl

```
# teOfTheDay クエリを実行
$ curl -X POST -H "Content-Type: application/json" -d '{"query": "{ quoteOfTheDay }"}' http://localhost:4000/graphql
{"data":{"quoteOfTheDay":"Salvation lies within"}}
# もしくは {"data":{"quoteOfTheDay":"Take it easy"}} が返ってくる。

# rollDice クエリを実行
$ curl -X POST -H "Content-Type: application/json" \
    -d '{"query": "{rollDice(numDice: 3, numSides: 6)}"}' \
    http://localhost:4000/graphql
{"data":{"rollDice":[1,2,3]}}
# さいころの目なので結果はランダム。

# 変数も使える。↓と↑は同義。
# $ が前についてあるものは変数。query キーと同階層に variables キーを用意して値を定義する。
$ curl -X POST \
    -H "Content-Type: application/json" \
    -d '{"query": "query RollDice($dice: Int!, $sides: Int) { rollDice(numDice: $dice, numSides: $sides) }", "variables": {"dice":3, "sides":6} }'  \
    http://localhost:4000/graphql
{"data":{"rollDice":[3,5,6]}} }"}' }"}'
```

### Gui クライアント

http://localhost:4000/graphql
