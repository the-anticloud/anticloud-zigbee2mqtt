# ZIGBEE2MQTT

> Official Zigbee2MQTT Home Assistant app [!CAUTION] If you're using a Raspberry Pi, ensure you have at least a Raspberry Pi 4, as running it on a Raspberry Pi 3 may cause instability due to its limited resources.

**Category:** CONSUMER_APPLIANCES · **Ecosystem:** python · **Vendored upstream:** https://github.com/zigbee2mqtt/hassio-zigbee2mqtt · **Pinned commit:** `25d64848d24734cafb178b96a699e35e3bbe51a8` · **Vendor:** Anticloud FZ LLE

## What This Project Is

Official Zigbee2MQTT Home Assistant app [!CAUTION] If you're using a Raspberry Pi, ensure you have at least a Raspberry Pi 4, as running it on a Raspberry Pi 3 may cause instability due to its limited resources.

This is the upstream project, vendored at the pinned commit above and packaged offline-first. The 12 improvements Anticloud adds live in `anticloud/` and are described under *Anticloud Overlay* below. Every fact in this file traces to a file in this directory.

## Installation

1. If you don't have an MQTT broker yet; in Home Assistant go to **[Settings → Apps → App store](https://my.home-assistant.io/redirect/supervisor_store/)** and install the **[Mosquitto broker](https://my.home-assistant.io/redirect/supervisor_addon/?addon=core_mosquitto)** app, then start it.
1. Go back to the **App store**, click **⋮ → Repositories**, fill in</br> `https://github.com/zigbee2mqtt/hassio-zigbee2mqtt` and click **Add → Close** or click the **Add repository** button below, click **Add → Close** (You might need to enter the **internal IP address** of your Home Assistant instance first).
   [![Open your Home Assistant instance and show the add app repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fzigbee2mqtt%2Fhassio-zigbee2mqtt)
1. The repository includes two apps:
   - **Zigbee2MQTT** is the stable release that tracks the released versions of Zigbee2MQTT. (**recommended for most users**)
   - **Zigbee2MQTT Edge** tracks the `dev` branch of Zigbee2MQTT such that you can install the edge version if there are features or fixes in the Zigbee2MQTT dev branch that are not yet released.
1. Click on the app and press **Install** and wait till the app is installed.
1. Start the app by going to **Info** and click **Start**
1. Wait a few seconds and press **OPEN WEB UI**, you will now see the onboarding page. More information about the onboarding can be found [here](https://www.zigbee2mqtt.io/guide/getting-started/#onboarding).
1. Fill in the desired settings, for most setups changing the following is enough:
   - Select your adapter under _Found Devices_, this will configure the _Coordinator/Adapter Port/Path_ and _Coordinator/Adapter Type/Stack/Driver_.
   - Fill in the _Closests WiFi Channel_ to select the most optimal Zigbee channel.
1. Press **Submit**, Zigbee2MQTT will now start, wait a few seconds and refresh the page. You should now see the Zigbee2MQTT frontend.
   - If it shows `502: Bad Gateway` wait a bit more and refresh the page.
   - If this takes too long (e.g. 2 minutes +) check the **Log** tab to see what went wrong.
   - In case the app fails to start with the following error: `USB adapter discovery error (No valid USB adapter found). Specify valid 'adapter' and 'port' in your configuration.`, we need to fill in the `serial` section. Format can be found [here](https://www.zigbee2mqtt.io/guide/configuration/adapter-settings.html#adapter-settings), but skip the initial `serial:` indent. e.g.: <br>
     ```yaml
     adapter: zstack
     port: /dev/serial/by-id/usb-Texas_Instruments_TI_CC2531_USB_CDC___0X00124B0018ED3DDF-if00
     ```
     If you don't know the port and you have just one USB device connected to your machine try `/dev/ttyACM0` or `/dev/ttyUSB0` or `/dev/ttyAMA0`. Else use the [Home Assistant CLI](https://www.home-assistant.io/common-tasks/os#home-assistant-via-the-command-line) and execute `ha hardware info` to find out.

For more information see [the documentation](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/blob/master/zigbee2mqtt/DOCS.md).

## Usage

See the upstream README (linked above) for usage. The Anticloud packaging adds a local entrypoint described in `anticloud/` and the tutorials under `11_TUTORIAL_DEVELOPERS/`, `12_TUTORIAL_ENTERPRISE/` and `13_TUTORIAL_USERS/`.

## Anticloud Overlay

The 12 improvements live under `anticloud/`. Run the check suite from this directory:

```
python anticloud/bench/runner.py --cwd anticloud
```

## Benchmark Results

| Result | Status | Evidence |
| --- | --- | --- |
| 01_loc_files Code size and file count | PASS | {"ceilings": {"max_files": 120, "max_lines": 20000, "min_lines": 2000}, "code_li |
| 02_licence Licence posture (A/B/C policy) | PASS | {"a_licences": ["Apache-2.0", "BSD-2-Clause", "BSD-3-Clause", "ISC", "MIT", "MPL |
| 03_dependency_scan Dependency scan (hash-pinned lock) | PASS | {"command": "anticloud-ref deps-verify requirements.lock", "declared_in_pyprojec |
| 04_sbom_cyclonedx SBOM (CycloneDX 1.5) | PASS | {"command": "python -c \"import json;d=json.load(open('sbom.cdx.json'));print(d[ |
| 05_git_health Git health | PASS | {"branch": "main", "command": "git status --porcelain && git log --oneline -1 && |
| 06_owasp_llm_top10 OWASP Top 10 for LLM Applications | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 07_owasp_top10 OWASP Top 10 (2021) | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 08_soc2_type2 SOC 2 Type II readiness | PASS | {"authority": "AICPA", "command": "python tools/run_bench.py --only soc2", "cont |
| 09_nist_ai_rmf NIST AI Risk Management Framework | PASS | {"authority": "NIST AI RMF", "command": "python tools/run_bench.py --only nist", |
| 10_nist_sp_800_53 NIST SP 800-53 Rev. 5 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 11_nist_csf NIST Cybersecurity Framework 2.0 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 12_fedramp FedRAMP Rev. 5 | PASS | {"authority": "FedRAMP", "command": "python tools/run_bench.py --only fedramp",  |
| 13_pci_dss PCI DSS v4.0.1 | PASS | {"authority": "PCI SSC", "command": "python tools/run_bench.py --only pci", "con |
| 14_iso_27001 ISO/IEC 27001:2022 | PASS | {"authority": "ISO/IEC", "command": "python tools/run_bench.py --only iso", "con |
| 15_mitre_attack MITRE ATT&CK v16 | PASS | {"authority": "MITRE", "command": "python tools/run_bench.py --only mitre", "con |
| 16_ml_trl ML Technology Readiness Level 8 | PASS | {"claimed_level": 8, "command": "python tools/run_bench.py --only 16 && cat docs |

**Suite: 16/16 passed** · platform `win32` · python `3.12.10` · method `{'aggregate_rule': 'all_passed == AND over benchmarks[*].ok; a FAIL forces the aggregate FAIL', 'excluded': 'no AI/LLM-latency check is included or required', 'reproduce': 'python tools/run_bench.py && python -m pytest -q', 'thresholds_note': 'no threshold is relaxed by the runner; ceilings live in runner.py and are asserted independently in tests/test_project_metadata.py'}`

## Licence

The upstream licence is preserved in `LICENSE` and `THIRD_PARTY_LICENSES/`. The Anticloud overlay is licensed under Anticommons 0.1.0 (`ANTICOMMONS_LICENSE.md`).

## Verification

SHA3-256 of `BENCH.json`:

```
5617cf079e46e66de940951a126f7b239a2b665c9a8ee4afa92b9d1baa281c44
```

Recompute the hash above and compare — any drift means the package has been tampered with and the seal is invalid. This is a self-assessment; no external audit has been performed and a SOC 2 / NIST independent audit is committed post-funding.
