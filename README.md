# Endpoint: bestDepositOptions

/v1/best-deposit-options/{userAddress}

## Additional Parameters
1. minimumBalanceThreshold
* Type: number
* Description: Minimum balance (in USD) that an asset must meet or exceed to be considered for deposit options.
* Example: 50
2. maxVaultsPerAsset
* Type: number
* Description: Max number of top vaults to be displayed per asset on a network
* Example: 3, max=5
3. allowedAssets
* Type: array[string]
* Description: List of asset symbols that are permitted for deposit.
* Example: ["ETH", "USDC", "DAI"], default = all
* If allowed is used, disallowed is ignored. 
4. disallowedAssets
* Type: array[string]
* Description: List of asset symbols that are not permitted for deposit.
* Example: ["WBTC", "USDT"], default = None
5. allowedNetworks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are permitted for deposit options.
* Example: ["mainnet", "polygon"] or ["eip155:1", "eip155:137"], default = all
* If allowed is used, disallowed is ignored. 
6. disallowedNetworks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are not permitted for deposit options.
* Example: ["bsc", "arbitrum"] or ["eip155:56", "eip155:42161"], default = None
7. allowedProtocols
* Type: array[string]
* Description: List of protocol names that are permitted for deposit options.
* Example: ["Yearn", "Curve", "Aave"], default = all
* If allowed is used, disallowed is ignored. 
8. disallowedProtocols
* Type: array[string]
* Description: List of protocol names that are not permitted for deposit options.
* Example: ["Compound", "SushiSwap"], default = None

# Example Payload
```
{
  "minimumBalanceThreshold": 50,
  "maxVaultsPerAsset": 3,
  "disallowedAssets": ["WBTC", "USDT"],
  "allowedNetworks": ["mainnet", "polygon"],
  "disallowedProtocols": ["Compound", "SushiSwap"]
}
```

# Example response
```

{
  "requestedAddress": "0xUserRequestedAddress1234567890abcdef",
  "userBalances": [
    {
      "asset": {
        "name": "Ethereum",
        "symbol": "ETH",
        "assetAddress": "0x0000000000000000000000000000000000000000",
        "networkName": "mainnet",
        "networkCaip": "eip155:1",
        "decimals": 18,
        "balance": 1.5,
        "balanceInUsd": 2400
      },
      "depositOptions": [
        {
          "vault": {
            "name": "ETH High Yield Vault",
            "protocol": {
              "name": "Yearn",
              "product": "Vault",
              "version": "v2",
              "protocolUrl": "https://yearn.finance",
              "protocolLogo": "https://example.com/yearn-logo.png"
            },
            "vaultAddress": "0x1234567890abcdef1234567890abcdef12345678",
            "vaultUrl": "https://yearn.finance/vault/0x1234567890abcdef1234567890abcdef12345678",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0x1234567890abcdef1234567890abcdef12345678",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 50000000,
            "apy": 0.055,
            "projectedAnnualEarnings": 132
          }
        },
        {
          "vault": {
            "name": "ETH Liquidity Vault",
            "protocol": {
              "name": "Curve",
              "product": "Liquidity Pool",
              "version": "v1",
              "protocolUrl": "https://curve.fi",
              "protocolLogo": "https://example.com/curve-logo.png"
            },
            "vaultAddress": "0xabcdef1234567890abcdef1234567890abcdef12",
            "vaultUrl": "https://curve.fi/vault/0xabcdef1234567890abcdef1234567890abcdef12",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0xabcdef1234567890abcdef1234567890abcdef12",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 25000000,
            "apy": 0.032,
            "projectedAnnualEarnings": 76.8
          }
        },
        {
          "vault": {
            "name": "ETH Staking Vault",
            "protocol": {
              "name": "Lido",
              "product": "Staking",
              "version": "v1",
              "protocolUrl": "https://lido.fi",
              "protocolLogo": "https://example.com/lido-logo.png"
            },
            "vaultAddress": "0x9876543210fedcba9876543210fedcba98765432",
            "vaultUrl": "https://lido.fi/vault/0x9876543210fedcba9876543210fedcba98765432",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0x9876543210fedcba9876543210fedcba98765432",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 100000000,
            "apy": 0.048,
            "projectedAnnualEarnings": 115.2
          }
        }
      ]
    },
    {
      "asset": {
        "name": "USD Coin",
        "symbol": "USDC",
        "assetAddress": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "networkName": "mainnet",
        "networkCaip": "eip155:1",
        "decimals": 6,
        "balance": 1000,
        "balanceInUsd": 1000
      },
      "depositOptions": [
        {
          "vault": {
            "name": "USDC Stable Yield Vault",
            "protocol": {
              "name": "Yearn",
              "product": "Vault",
              "version": "v2",
              "protocolUrl": "https://yearn.finance",
              "protocolLogo": "https://example.com/yearn-logo.png"
            },
            "vaultAddress": "0x234567890abcdef1234567890abcdef12345678",
            "vaultUrl": "https://yearn.finance/vault/0x234567890abcdef1234567890abcdef12345678",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0x234567890abcdef1234567890abcdef12345678",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 80000000,
            "apy": 0.035,
            "projectedAnnualEarnings": 35
          }
        },
        {
          "vault": {
            "name": "USDC Liquidity Pool",
            "protocol": {
              "name": "Curve",
              "product": "Liquidity Pool",
              "version": "v1",
              "protocolUrl": "https://curve.fi",
              "protocolLogo": "https://example.com/curve-logo.png"
            },
            "vaultAddress": "0xbcdef1234567890abcdef1234567890abcdef12",
            "vaultUrl": "https://curve.fi/vault/0xbcdef1234567890abcdef1234567890abcdef12",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0xbcdef1234567890abcdef1234567890abcdef12",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 150000000,
            "apy": 0.028,
            "projectedAnnualEarnings": 28
          }
        },
        {
          "vault": {
            "name": "USDC Lending Pool",
            "protocol": {
              "name": "Aave",
              "product": "Lending",
              "version": "v3",
              "protocolUrl": "https://aave.com",
              "protocolLogo": "https://example.com/aave-logo.png"
            },
            "vaultAddress": "0xfedcba9876543210fedcba9876543210fedcba98",
            "vaultUrl": "https://aave.com/vault/0xfedcba9876543210fedcba9876543210fedcba98",
            "frontendUrl": "https://app.vaults.fyi/opportunity/mainnet/0xfedcba9876543210fedcba9876543210fedcba98",
            "networkName": "mainnet",
            "networkCaip": "eip155:1",
            "tvlInUsd": 120000000,
            "apy": 0.025,
            "projectedAnnualEarnings": 25
          }
        }
      ]
    }
  ]
}

```
