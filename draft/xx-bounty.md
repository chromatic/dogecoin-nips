NOT A NIP (YET)
===============

Nostr bounties

`draft` `optional` `author:chromatic`

## Terms

- `bounty` an offer to pay a reward for fulfilling a condition
- `pledge` a specific amount of currency promised to the person fulfilling the
  condition
- `status` a description of the state of the bounty, especially distinguishing
  between proposed, claimed, and rewarded
- 

### Event `...`: Create or update a bounty

**Event Content**:
```json
{
    "id": <32-bytes lowercase hex-encoded sha256 of the serialized event data>,
    "pubkey": <32-bytes lowercase hex-encoded public key of the event creator>,
    "created_at": <Unix timestamp in seconds>,
    "kind": <integer>,
    "tags": [
        [ "d": <String, UUID generated by the event creator. Random UUID encouraged.> ]j
        [ "title": <String, a title for the bounty> ],
        [ "published_at": <Integer, timestamp in Unix seconds of when the bounty was first published> ],
        [ "image", "<url>", "<dimensions>" ],
        [ "image", "<url>", "<dimensions>" ],
        [
            "amount" <String, the literal name of the tag>
            "number" <String, the amount in numeric format, included in the tag as as string>,
            "currency" <String, the currency unit in ISO 4217 format or similar format ("btc", "usd", "cad", "doge")>
        ]
    ],
    "content": <String, a description of what is being requested, including the conditions for awarding the bounty upon completion>,
    "sig": <64-bytes hex of the signature of the sha256 hash of the serialized event data, which is the same as the "id" field>
}

### Event `...`: Update a Bounty Status

Needs The status of the bounty, timestamp, id, and possibly reason? (`proposed`, `active`, `claimed`, `rewarded`, `withdrawn`)

### Event `...`: Pledge to bounty

Add a pledge to an existing bounty.

### Event `...`: Apply for Bounty
