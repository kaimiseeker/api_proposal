# Endpoint: BestDepositOptions

/v1/best-deposit-options/{userAddress}

## Additional Parameters
1. allowed_assets
* Type: array[string]
* Description: List of asset symbols that are permitted for deposit.
* Example: ["ETH", "USDC", "DAI"], default = all
* If allowed is used, disallowed is ignored. 
2. disallowed_assets
* Type: array[string]
* Description: List of asset symbols that are not permitted for deposit.
* Example: ["WBTC", "USDT"], default = None
3. minimum_balance_threshold
* Type: number
* Description: Minimum balance (in USD) that an asset must meet or exceed to be considered for deposit options.
* Example: 50
4. allowed_networks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are permitted for deposit options.
* Example: ["mainnet", "polygon"] or ["eip155:1", "eip155:137"], default = all
* If allowed is used, disallowed is ignored. 
5. disallowed_networks
* Type: array[string]
* Description: List of network names or CAIP-2 identifiers that are not permitted for deposit options.
* Example: ["bsc", "arbitrum"] or ["eip155:56", "eip155:42161"], default = None
6. allowed_protocols
* Type: array[string]
* Description: List of protocol names that are permitted for deposit options.
* Example: ["Yearn", "Curve", "Aave"], default = all
* If allowed is used, disallowed is ignored. 
7. disallowed_protocols
* Type: array[string]
* Description: List of protocol names that are not permitted for deposit options.
* Example: ["Compound", "SushiSwap"], default = None

# Example Payload
```
{

  "disallowed_assets": ["WBTC", "USDT"],
  "minimum_balance_threshold": 50,
  "allowed_networks": ["mainnet", "polygon"],
  "disallowed_protocols": ["Compound", "SushiSwap"]
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
              "protocol_url": "https://curve.fi",
              "protocol_logo": "https://example.com/curve-logo.png"
            },
            "vaultAddress": "0xabcdef1234567890abcdef1234567890abcdef12",
            "vault_url": "https://curve.fi/vault/0xabcdef1234567890abcdef1234567890abcdef12",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0xabcdef1234567890abcdef1234567890abcdef12",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
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
              "protocol_url": "https://lido.fi",
              "protocol_logo": "https://example.com/lido-logo.png"
            },
            "vaultAddress": "0x9876543210fedcba9876543210fedcba98765432",
            "vault_url": "https://lido.fi/vault/0x9876543210fedcba9876543210fedcba98765432",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0x9876543210fedcba9876543210fedcba98765432",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
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
        "network_caip": "eip155:1",
        "decimals": 6,
        "balance": 1000,
        "balanceInUsd": 1000
      },
      "investmentOptions": [
        {
          "vault": {
            "name": "USDC Stable Yield Vault",
            "protocol": {
              "name": "Yearn",
              "product": "Vault",
              "version": "v2",
              "protocol_url": "https://yearn.finance",
              "protocol_logo": "https://example.com/yearn-logo.png"
            },
            "vaultAddress": "0x234567890abcdef1234567890abcdef12345678",
            "vault_url": "https://yearn.finance/vault/0x234567890abcdef1234567890abcdef12345678",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0x234567890abcdef1234567890abcdef12345678",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
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
              "protocol_url": "https://curve.fi",
              "protocol_logo": "https://example.com/curve-logo.png"
            },
            "vaultAddress": "0xbcdef1234567890abcdef1234567890abcdef12",
            "vault_url": "https://curve.fi/vault/0xbcdef1234567890abcdef1234567890abcdef12",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0xbcdef1234567890abcdef1234567890abcdef12",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
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
              "protocol_url": "https://aave.com",
              "protocol_logo": "https://example.com/aave-logo.png"
            },
            "vaultAddress": "0xfedcba9876543210fedcba9876543210fedcba98",
            "vault_url": "https://aave.com/vault/0xfedcba9876543210fedcba9876543210fedcba98",
            "frontend_url": "https://app.vaults.fyi/opportunity/mainnet/0xfedcba9876543210fedcba9876543210fedcba98",
            "networkName": "mainnet",
            "network_caip": "eip155:1",
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
