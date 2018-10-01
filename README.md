# API for MoonDEX

MoonDEX exchange's order books are on BitShares blockchain. The assets name begins with MOONDEX., like MOONDEX.BTC for BTC. Most of the BitShares explorers can be used to check the trade history.

The APIs below are mantained by the MoonDEX dev team:

# Get the trading data
## The base url is https://data.moondex.io

## [GET /ticker]
#### Description:
Get all of the trading pair's ticker information for the past 24 hours.

#### Response:
```javascript
[
    {
        "highestBid": "0.00000900",
        "latest": "0.00001059",
        "lowestAsk": "0.00001000",
        "pair": "MDEX_BTC",
        "percentChange": "17.66",
        "volume": "0.07833426"
    },
    {
        "highestBid": "0.00000193",
        "latest": "0.00000219",
        "lowestAsk": "0.00000255",
        "pair": "RVN_BTC",
        "percentChange": "21.66",
        "volume": "0.00291406"
    }
]
```

## [GET /ticker/COIN_BASE]

#### Description:
Get a specific trading pair's ticker information for the past 24 hours.

#### Query:
* `COIN`		**string** The coin to trade.
* `BASE`		**string** The base coin for the volumes.
* Example: MDEX_BTC

#### Response:
```javascript
{
    "highestBid": "0.00000000",
    "latest": "0.00000000",
    "lowestAsk": "0.00010000",
    "percentChange": "0.00",
    "volume": "0.00000000"
}
```

# Get the exchange data
## The base url is https://api.moondex.io

## [GET /coins]

#### Description:
Get all of the coins supported by MoonDEX and their detailed information.

#### Response:
```javascript
[
    {
        "coinType": "moondex.mdex",
        "walletName": "BitShares 2.0",
        "name": "MoonDEXCoin",
        "symbol": "MOONDEX.MDEX",
        "walletSymbol": "MOONDEX.MDEX",
        "walletType": "bitshares2",
        "transactionFee": "0.01",
        "precision": "100000000",
        "backingCoinType": "mdex",
        "supportsOutputMemos": false,
        "restricted": false,
        "depositAllowed": true,
        "requiredConfirmations": 6
    },
    {
        "coinType": "moondex.btc",
        "walletName": "BitShares 2.0",
        "name": "Bitcoin",
        "symbol": "MOONDEX.BTC",
        "walletSymbol": "MOONDEX.BTC",
        "walletType": "bitshares2",
        "transactionFee": "0.0003",
        "precision": "100000000",
        "backingCoinType": "btc",
        "supportsOutputMemos": false,
        "restricted": false,
        "depositAllowed": true,
        "requiredConfirmations": 3
    }
]
```