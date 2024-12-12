# Endpoint: BestDepositOptions

/v1/best-deposit-options/{userAddress}

## Additional Parameters
1. allowed_assets
* Type: array[string]
* Description: List of asset symbols or identifiers that are permitted for deposit.
* Example: ["ETH", "USDC", "DAI"]
2. disallowed_assets
* Type: array[string]
* Description: List of asset symbols or identifiers that are not permitted for deposit.
* Example: ["WBTC", "USDT"]
3. minimum_balance_threshold
* Type: number
* Description: Minimum balance (in USD) that an asset must meet or exceed to be considered for deposit options.
* Example: 50
4. allowed_networks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are permitted for deposit options.
* Example: ["mainnet", "polygon"] or ["eip155:1", "eip155:137"]
5. disallowed_networks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are not permitted for deposit options.
* Example: ["bsc", "arbitrum"] or ["eip155:56", "eip155:42161"]
6. allowed_protocols
* Type: array[string]
* Description: List of protocol names that are permitted for deposit options.
* Example: ["Yearn", "Curve", "Aave"]
7. disallowed_protocols
* Type: array[string]
* Description: List of protocol names that are not permitted for deposit options.
* Example: ["Compound", "SushiSwap"]


# Example Payload
```
{
  "allowed_assets": ["ETH", "USDC", "DAI"],
  "disallowed_assets": ["WBTC", "USDT"],
  "minimum_balance_threshold": 50,
  "allowed_networks": ["mainnet", "polygon"],
  "disallowed_networks": ["bsc", "arbitrum"],
  "allowed_protocols": ["Yearn", "Curve", "Aave"],
  "disallowed_protocols": ["Compound", "SushiSwap"]
}
```
# Example response
```
{
  "requestedAddress": "0xUserRequestedAddress1234567890abcdef",
  "allowed_assets": ["ETH", "USDC", "DAI"],
  "disallowed_assets": ["WBTC", "USDT"],
  "minimum_balance_threshold": 50,
  "allowed_networks": ["mainnet", "polygon"],
  "disallowed_networks": ["bsc", "arbitrum"],
  "allowed_protocols": ["Yearn", "Curve", "Aave"],
  "disallowed_protocols": ["Compound", "SushiSwap"],
  "userBalances": [
    {
      "asset": {
        "name": "Ethereum",
        "symbol": "ETH",
        "assetAddress": "0x0000000000000000000000000000000000000000",
        "networkName": "mainnet",
        "network_caip": "eip155:1",
        "decimals": 18,
        "balance": 1.5,
        "balanceInUsd": 2400
      },
      "investmentOptions": [
        {
          "vault": {
            "name": "ETH High Yield Vault",
            "protocol": {
              "name": "Yearn",
              "product": "Vault",
              "version": "v2",
              "protocol_url": "https://yearn.finance",
              "protocol_logo": "https://example.com/yearn-logo.png"
            },
            "vaultAddress": "0x1234567890abcdef1234567890abcdef12345678",
            "vault_url": "https://yearn.finance/vault/0x1234567890abcdef1234567890abcdef12345678",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0x1234567890abcdef1234567890abcdef12345678",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
            "tvlInUsd": 50000000,
            "apy": 5.5,
            "projectedEarnings": 132
          }
        }
      ]
    }
  ]
}

```
