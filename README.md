# Aftermint Rarity Data

This repository contains pre-calculated rarity data for NFT collections on the Aftermint marketplace.

## Collections

- **Dank Pepes** (4.8 MB) - 6,969 tokens
- **Final Phase NFT V3** (5.6 MB) - 10,000 tokens
- **PixelPepes** (762 KB) - 7,777 tokens
- **CosmicPond** (707 KB) - 1,008 tokens
- **BasedBeasts** (1.0 MB) - 2,222 tokens
- **OGNodes** (36 KB) - 111 tokens

## Usage

These files are served via jsDelivr CDN for free, global distribution:

```
https://cdn.jsdelivr.net/gh/bemorebased/aftermint-rarity-data@main/dankpepesComplete.json
```

## Caching

The Aftermint marketplace uses IndexedDB client-side caching:
- First visit: Downloads from jsDelivr CDN
- Repeat visits: Instant load from browser cache (30-day TTL)
- Zero bandwidth cost on Vercel

## Data Format

Each collection follows this structure:

```json
{
  "metadata": {
    "collection": "Collection Name",
    "contract": "0x...",
    "totalSupply": 1000,
    "version": "1.0.0"
  },
  "rarityMap": {
    "1": {
      "tokenId": 1,
      "name": "Token #1",
      "traits": { "trait_type": "value" },
      "rarityScore": 123.45,
      "rank": 1,
      "tier": "Legendary"
    }
  },
  "traitStats": {
    "trait_type": {
      "value": { "count": 10, "rarity": 0.01 }
    }
  }
}
```

## Updates

To update rarity data:
1. Update JSON files in this repo
2. Increment `RARITY_DATA_VERSION` in the marketplace code
3. Users will automatically fetch updated data on next visit

## License

MIT - Public domain for community use
