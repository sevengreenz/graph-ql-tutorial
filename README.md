
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
# teOfTheDay $B%/%(%j$r<B9T(B
$ curl -X POST -H "Content-Type: application/json" -d '{"query": "{ quoteOfTheDay }"}' http://localhost:4000/graphql
{"data":{"quoteOfTheDay":"Salvation lies within"}}
# $B$b$7$/$O(B {"data":{"quoteOfTheDay":"Take it easy"}} $B$,JV$C$F$/$k!#(B

# rollDice $B%/%(%j$r<B9T(B
$ curl -X POST -H "Content-Type: application/json" \
    -d '{"query": "{rollDice(numDice: 3, numSides: 6)}"}' \
    http://localhost:4000/graphql
{"data":{"rollDice":[1,2,3]}}
# $B$5$$$3$m$NL\$J$N$G7k2L$O%i%s%@%`!#(B

# $BJQ?t$b;H$($k!#"-$H",$OF15A!#(B
# $ $B$,A0$K$D$$$F$"$k$b$N$OJQ?t!#(Bquery $B%-!<$HF13,AX$K(B variables $B%-!<$rMQ0U$7$FCM$rDj5A$9$k!#(B
$ curl -X POST \
    -H "Content-Type: application/json" \
    -d '{"query": "query RollDice($dice: Int!, $sides: Int) { rollDice(numDice: $dice, numSides: $sides) }", "variables": {"dice":3, "sides":6} }'  \
    http://localhost:4000/graphql
{"data":{"rollDice":[3,5,6]}} }"}' }"}'
```

### Gui $B%/%i%$%"%s%H(B

http://localhost:4000/graphql
