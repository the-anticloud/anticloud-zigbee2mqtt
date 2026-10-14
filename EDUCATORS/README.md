# Educators — ZIGBEE2MQTT

**Project:** ZIGBEE2MQTT  
**Category:** CONSUMER_APPLIANCES  
**Upstream:** https://github.com/Koenkk/zigbee2mqtt  
**Pinned commit:** `344b6e03b43644c97154a72ca9eae17193c553a2`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c87cb3406779831d66c4f10d9ab649277e5aaa8f2f9faeb831dee72bc5849d08`  
**Date:** October 2026

## Teaching with ZIGBEE2MQTT

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `c87cb3406779831d66c4f10d9ab649277e5aaa8f2f9faeb831dee72bc5849d08` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
