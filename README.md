# OPC UA Bridge Pro

> A 4-in-1 OPC UA server that bridges Modbus, MQTT, CSV, and demo data sources into a single OPC UA endpoint. Replace $5,000 commercial gateways with a $79 Python tool.
<img width="1280" height="720" alt="opcua_cover" src="https://github.com/user-attachments/assets/35fda1a9-59f0-44be-b4d2-99f08490314f" />

**This is a commercial tool, sold on Gumroad.** Source code is included in your purchase.

---

## What it does

- **4 data sources in one bridge** — Modbus (TCP+RTU), MQTT, CSV files, demo simulator
- **Standards-compliant OPC UA server** — connect any SCADA / HMI client (Ignition, Kepware, FactoryTalk View, etc.)
- **Live tag mapping GUI** — drag-drop fields from any source into your OPC UA address space
- **Type-aware** — handles INT16, UINT16, INT32, UINT32, FLOAT32, FLOAT64, BOOL, STRING
- **All 4 byte orders** for Modbus — ABCD, CDAB (Schneider), BADC, DCBA
- **Subscription-based MQTT** — auto-flatten JSON payloads into OPC UA tags
- **CSV replay mode** — perfect for demo + training environments
- **Built-in demo simulator** — generate realistic IIoT data for testing
- **Tkinter dark GUI** — same look-and-feel as the rest of the toolkit
- **Single-file Python** — 1500+ lines, no install hell

## Why this exists

Commercial OPC UA gateways from Kepware, Matrikon, or InGearQA cost $1,000-$5,000+ per license per year. They're bloated, vendor-locked, and overkill for the 90% of integrations that just need "Modbus → OPC UA" or "MQTT → OPC UA."

OPC UA Bridge Pro is built for that 90%. One-time purchase, runs anywhere Python runs, source code included so you can customize it for your project.

## Use cases

| Scenario | Why this tool fits |
|---|---|
| Brownfield Modbus → modern SCADA | Bridge legacy PLCs into Ignition / FactoryTalk |
| MQTT broker → SCADA | Expose IIoT sensor data through OPC UA |
| Test rig data acquisition | CSV replay for repeatable test scenarios |
| Vendor demos / trade shows | Demo simulator generates realistic tags |
| Edge gateway prototyping | Run on Raspberry Pi as data aggregator |
| Training environments | Cheap-to-deploy OPC UA endpoint for students |

## Architecture

```
┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐
│  Modbus  │   │   MQTT   │   │   CSV    │   │   Demo   │
│  Sources │   │  Broker  │   │  Files   │   │ Simulator│
└─────┬────┘   └─────┬────┘   └─────┬────┘   └─────┬────┘
      │              │              │              │
      └──────────────┴──────┬───────┴──────────────┘
                            │
                  ┌─────────▼─────────┐
                  │  OPC UA Bridge    │
                  │  (Tag mapping)    │
                  └─────────┬─────────┘
                            │
                  ┌─────────▼─────────┐
                  │   OPC UA Server   │
                  │  (port 4840)      │
                  └─────────┬─────────┘
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
   ┌────▼────┐        ┌────▼────┐         ┌────▼────┐
   │ Ignition│        │ Kepware │         │ HMI/UI  │
   └─────────┘        └─────────┘         └─────────┘
```

## Tested with

| OPC UA Client | Connection result |
|---|---|
| Inductive Automation Ignition | ✅ Tags appear, types correct |
| KEPServerEX | ✅ |
| Matrikon OPC UA Client | ✅ |
| UaExpert (Unified Automation) | ✅ |
| Prosys OPC UA Client | ✅ |
| Node-RED `node-red-contrib-opcua` | ✅ |
| Python `asyncua` client | ✅ |

## Get it

→ **[OPC UA Bridge Pro on Gumroad — $79](https://philyeh.gumroad.com/l/opcua-bridge-pro)**

Or grab the **[Industrial Integration Bundle](https://philyeh.gumroad.com/l/industrial-integration-bundle)** ($119) — OPC UA Bridge + Modbus Logger + MQTT Logger together, saves $48.

## What's in the purchase

- `opcua_bridge.py` — Single-file Python application (1500+ lines)
- `requirements.txt` — Pinned dependencies (asyncua, pymodbus, paho-mqtt)
- `README.md` — Setup guide + tag mapping examples
- Commercial use license per Gumroad EULA

## License

Commercial use license per Gumroad EULA. You may use this software at the company that purchased it for any commercial purpose. Redistribution, resale, or open-sourcing the code is not permitted.

## Support

- Reply to your Gumroad purchase email
- Bug reports / feature requests via GitHub Issues

---

I write about industrial Python and protocol internals at **[dev.to/philyeh](https://dev.to/philyeh)**, and post Chinese versions on [iThelp](https://ithelp.ithome.com.tw/users/20171204).

— Phil Yeh · Senior Automation Engineer · Industrial Python · Developer Tools
