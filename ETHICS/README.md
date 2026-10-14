# Ethics — ZIGBEE2MQTT

**Project:** ZIGBEE2MQTT  
**Category:** CONSUMER_APPLIANCES  
**Upstream:** https://github.com/Koenkk/zigbee2mqtt  
**Pinned commit:** `344b6e03b43644c97154a72ca9eae17193c553a2`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c87cb3406779831d66c4f10d9ab649277e5aaa8f2f9faeb831dee72bc5849d08`  
**Date:** October 2026

## Position

ZIGBEE2MQTT is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
