# Students — ZIGBEE2MQTT

**Project:** ZIGBEE2MQTT  
**Category:** CONSUMER_APPLIANCES  
**Upstream:** https://github.com/Koenkk/zigbee2mqtt  
**Pinned commit:** `344b6e03b43644c97154a72ca9eae17193c553a2`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c87cb3406779831d66c4f10d9ab649277e5aaa8f2f9faeb831dee72bc5849d08`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `344b6e03b43644c97154a72ca9eae17193c553a2`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `c87cb3406779831d66c4f10d9ab649277e5aaa8f2f9faeb831dee72bc5849d08`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
