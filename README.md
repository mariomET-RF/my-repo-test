# RF Setup and Test Requirements — Folder Index

Updated 2026-11-20. The block diagram PDF, all Excel workbooks (sheet names and header rows), all Word documents (headings, scope and requirement IDs) and 25 of the 28 spec-sheet files were read in full (the long manuals by subagents; see the Source column). The other three are described from their embedded PDF title and the master workbook's Hardware Inventory tab. The 11 current engineering drawings in `Eng System Diagrams` were read by subagents. Their title blocks and notes are text and reliable, but ref des, part numbers and connector labels are small image text and were read at low resolution (see the confidence notes). The superseded Rev 9.5 drawings in `Archives` were not read. The three documents added to `ICD_DOCs` on Nov 20 were read in full: the ICD PDF (all 43 pages) and the text of both PowerPoint decks. The pictures inside the decks were not examined.

## Top-level folders

| Folder | Description |
|---|---|
| `archive` | Superseded drafts of the MUSV-RF-TR test requirements documents. v0.1 (TR-000…004 only) is a long formal format with approvals, applicable documents, test equipment, records and common requirements repeated in each doc. v0.2 adds TR-005…007 and switches to the short per-part-number IQC → sub-assembly → EOL layout kept in v0.3. |
| `ICD_DOCs` | Design reference documents from RF Communications engineering (David Cobos), added Nov 20: the MUSV RF-Comm ICD Rev 6.0, the RFSC EWIS handover package, and the VHF antenna relocation decision brief. See the ICD section below. |
| `meetings` | Nov 16 check-in notes: minutes in .md/.txt plus two photos of handwritten pages. |
| `RF test setup block diagram` | Test setup block diagrams, the R&S quote 1195773 equipment list, the Olympus 12U rack equipment list, an early GNSS/GPS single-line diagram, and the 440-001 engineering drawings they're built from. |
| `RFSetup` | Master test-planning workbook *MUSV RF Test Setup & Requirements* (current v0.10, plus v0.9): equipment selection (TK1), cables & adapters, BOM (TK3), rack budget, IQC parameters and the test-requirements matrix (TK6), hardware inventory, drawing discrepancies and open questions. Older MUSV drafts (v0.6–v0.8) and the earlier GNSS-only *Marauder Test Requirements* workbooks (v0.1–v0.5) are in `Archive`. |
| `SpecSheets` | 28 vendor documents (datasheets, brochures, outline drawings and installation manuals), one per MUSV RF part number and named `<Saronic PN>_<vendor doc>`. Two pairs are byte-identical copies filed under two PNs. Three more files cover the test equipment: the R&S ZNL VNA and SGS100A signal generator spec sheets, and a ZNL14 photo. See the SpecSheets table below. |
| `TK6 Test Requirements Documents` | Current v0.3 Word drafts of the eight TK-6 RF test requirements documents, one per subsystem plus one for shared hardware (see the table below). Each has the same layout: scope, hardware, IQC per part number, sub-assembly test (bench → mast), EOL at FLA, open items. |
| `TK6 Test Requirements Documents_bk` | Byte-for-byte backup of the folder above, and its `archive` is byte-for-byte identical to the top-level `archive` (verified by file hash). |

## Subfolders

| Folder | Description |
|---|---|
| `RF test setup block diagram\Eng System Diagrams` | The source drawings: the 440-001 RFSC Rev 10.0 top-level assembly and the seven sub-assembly drawings (.01–.07), the functional diagram, the Arena structure and the RFSC frequency plan. Declared the source of truth in the v0.10 workbook. |
| `RF test setup block diagram\Eng System Diagrams\Archives` | Previous Rev 9.5 sub-assembly drawings dated 10/21/2026, which are large at 18–88 MB each. |
| `RF test setup block diagram\archive` | The v0.1 block diagram (PDF and .drawio), the v0.2 .drawio source, a GNSS assembly draft, and byte-identical copies of four Rev 10.0 sub-assembly drawings (.01, .03, .04, .06). |
| `RFSetup\Archive` | Superseded workbooks: MUSV Test Setup & Requirements v0.6–v0.8, and Marauder GNSS/INS Test Requirements v0.1–v0.5, which used the older L1a/L1b/L2/L3/L4 test levels. |

## Workbooks

| Workbook | Contents |
|---|---|
| `RFSetup\MUSV_RF_Test_Setup_and_Requirements_DRAFT_v0.10.xlsx` | The master workbook, 9 tabs: **Overview** (scope, IQC → sub-assembly → EOL phases, 7 sub-assemblies, sources); **TK1 Equipment** (E-tagged test equipment with status Quoted / Selected / Spec only / Gap); **TK1 RF Cables & Adapters**; **TK3 BOM** (~65 lines with quoted R&S prices); **Rack Budget** (12U road case layout, weight, power); **TK6 IQC Key Parameters** (~125 per-part-number pass criteria from datasheets, mapped to TR-000…007); **TK6 Test Requirements** (~120 PRE / IQC / SUB / EOL requirements with limits, methods, equipment); **Hardware Inventory** (~80 RF parts per vessel from 440-001 Rev 10.0); **Drawing Discrepancies** (functional diagram vs 440-001, resolved 2026-11-19); **Open Questions**. |
| `RFSetup\MUSV_RF_Test_Setup_and_Requirements_DRAFT_v0.9.xlsx` | Previous revision of the master workbook, still in the main folder. |
| `rf_marauder_test_req_1.0v.xlsx` (root) | The lead engineer's IQC list: ~78 Saronic part numbers, each with its key test parameters. Feeds the TK6 IQC Key Parameters tab. |
| `RF test setup block diagram\Equipment_List_Quote_1195773.xlsx` | Line items from the Rohde & Schwarz quote 1195773 (Oct 16, 2026): ZNL VNA and accessories, with part numbers, quantities and prices. |
| `RF test setup block diagram\RackEquipment.xlsx` | The same R&S quote list, plus a second tab adding power, dimensions and weight for each item. |
| `RF test setup block diagram\Olympus RF Test Rack.xlsx` | Equipment list for the 12U rack / road case (11U usable) for FLA AI&T, with power, dimensions and weight. |
| `RF test setup block diagram\GNSS_GPS_Single_Line_Diagram.xlsx` | Early spreadsheet-drawn GNSS/GPS block diagram (ANT1/ANT2 to the pole for AIT @ FLA); its test-requirements tab is empty. |

## Test requirements documents (v0.3)

Requirement counts are IQC / sub-assembly / EOL rows in each document's tables.

| Document | Covers | Requirements |
|---|---|---|
| `MUSV-RF-TR-000` Hardware & Common | Common rules for all docs; shared passives: splitters 233-00164/165, loads 233-00166/167/168, UHF and BNC adapters 233-00169/170, RF switch 233-00300, production coax (F520, LMR). | IQC 12 + cable IQC 4 / SUB-COM 3 / EOL-COM 5 |
| `MUSV-RF-TR-001` GNSS/GPS | Septentrio AsteRx RBi3 Pro (233-00140), Advanced Navigation Boreas D90 GNSS/INS (242-00664), Maxtena M10HCT-A-TNC antenna (242-00634). | 23 / 5 / 3 |
| `MUSV-RF-TR-002` LOS-MANET | Silvus StreamCaster SC4400X radio (233-00139), Southwest Antennas 1009-066 (233-00150). | 13 / 4 / 2 |
| `MUSV-RF-TR-003` SAT-TER | Thales VesseLINK Iridium Certus 700 (242-00266, 242-00267), Starlink terminal (233-00134; the TR doesn't name the model, but the ICD names it as the Flat High Performance terminal). | 12 / 4 / 3 |
| `MUSV-RF-TR-004` E-Stop | BWI Eagle Air-Eagle XLT receiver (233-00214), BWI Eagle 49-3101 omni antenna (233-00216), RockBLOCK RTU Iridium SBD SAT E-Stop (234-00035). | 13 / 4 / 3 |
| `MUSV-RF-TR-005` 5G/LTE | Cradlepoint W1855-5GC 5G adapter (233-00142), Maxtena NETZ 4-in-1 antenna (233-00149). | 9 / 3 / 2 |
| `MUSV-RF-TR-006` VHF/AIS | Raymarine AIS4000 (242-00689), Garmin Cortex Neuro (233-00299), SAILOR 7226 VHF (233-00298), Raymarine Ray90/91 (233-00154), VHF/AIS antenna (233-00155, TBD), Pasternack GNSS antenna for AIS (233-00264). The largest doc. | 33 / 4 / 2 |
| `MUSV-RF-TR-007` Radar | Furuno DRS6A-NXT X-band sensor (233-00232), FAR-22x8-BB radar (233-00279), FAR-2xx8 transceiver (446-00546), radar antenna (233-00286, TBD, no datasheet). The ICD and handover package name different models: X-band DRS25A-NXT and S-band FAR-2238S-NXT-BB. | 10 / 5 / 2 |

## Engineering drawings (`Eng System Diagrams`)

The Rev 10.0 drawings are single-sheet, by David Cobos, dated 11/16/2026, for project "Marauder - MR-003 V1". They share one notes block. It defines the cables: F520 is a MegaPhase assembly, and LMR-195/200/240/400 are made in-house from Times Microwave cable. It also defines references E1–E3, marks redundant parts with a dashed line, and sets the cable ID series: C100s are LOS/VHF/AIS, C200s GNSS, C300s SatComm. None has a TBD, a "[?]" or a revision table.

| Drawing | Shows |
|---|---|
| `440-001_V1_eng_rfsc_top_level_assembly_10.0v.pdf` | MR003-440-001 RFSC System Diagram: the whole RF system on one large sheet. Too dense to read beyond the title block and notes. |
| `440-001.01` RF LOS Subsystem | Six StreamCaster radios (RAD1–6; RAD2/4/6 redundant), six dual-port sector antennas (RF-ANT12–17, N-F) on 12 F520 cables (C106–C117), and 12 TNC-M 50 Ω loads (RF-LOAD2–13) on the unused radio ports. |
| `440-001.02` VHF/AIS | Antennas ANT9/ANT10 (UHF-F, PN ~233-00155) and ANT11 (GNSS, 233-00264, TNC-F J1, cable C200), splitters PWR_DIV1 (2-way) and PWR_DIV2 (4 ports, likely 3-way), N-to-UHF adapters, a coax switch, transceivers TXR1–4 and loads, in the ACU Wall [STRB]. |
| `440-001.03` RF LOS E-Stop | Air-Eagle receiver RF-RX1 (233-00214, TNC-F J1) → C120 LMR-240 → PWR_DIV3 (233-00164, 2-way) → C118/C119 → two 49-3101 antennas, ANT18 port and ANT19 stbd (N-F). Dedicated splitter, not shared with VHF. The most legible sheet. |
| `440-001.04` RF BLOS Comms | Mast antenna boxes for SAT E-Stop (RF-ESAT1/2), Starlink (RF-SAT_TER1/2) and Iridium (RF-ANT19/21); Iridium modems RF-MDM2/MDM3[R1] (242-00267) in the port/stbd ACUs with RP-SMA 50 Ω loads on J1 (RF-LOAD14/15, ~233-00168); cables C300/C301 F520. Labels mostly illegible. |
| `440-001.05` RF Radar | Two radars. FAR processor RF-RADAR2 (446-00546) J5 N-F → N cable → antenna RF-RADAR3 (233-00279) J1 N-M. DRS sensor RF-RADAR1 (233-00232) → waveguide → RF-RADAR4 (233-00286). No waveguide adapter or supply voltage shown. |
| `440-001.06` RF GNSS/INS | Four receivers: GNSS1 (233-00140, mast), GNSS2 [R2] (233-00140, forepeak), GNSS3 [R1] (242-00664 Boreas, tank, ports PRI/SEC), GNSS4 [R3] (233-00140, jet). Eight 242-00634 antennas, two per receiver, on F520 cables C209–C216, TNC-F throughout. No splitters or bias tees. |
| `440-001.07` RF Cell/LTE | Cradlepoint RF-MDM3 (233-00142), J1–J4 N-F → C121–C124 LMR-195 → Cell ports J1/J2 of Maxtena antennas RF-ANT22 port and ANT23 stbd (233-00149, N-M). The antennas' Wi-Fi ports J3/J4 are unconnected. No PoE source shown. |
| `MUSV RFSC Functional Diagram.pdf` | Older whole-system block diagram, no title block. Superseded: its ref des and cable IDs differ from Rev 10.0 (e.g. Cradlepoint = RF-RAD9, Maxtena = RF-ANT1/2, Boreas = RF-GNSS4, Starlink = 973-00064, GNSS cables C202–C208). |
| `RFSC Frequency Plan Rev1.0.pdf` | Bar chart of 12 bands, no title block, no TX powers. VHF/AIS 156–162 MHz; 5G 600–850 MHz, 2.5 GHz, 3.7 GHz; UHF 900 MHz; GNSS 1.2–1.6 GHz; low-rate SAT 1616–1626.5 MHz; LOS 2430–2440 MHz; S-band radar 3.0 GHz; X-band radar 9.4 GHz; Ku SAT RX 10.7–12.7 / TX 14–14.5 GHz. |
| `RFSC 440-001 Arena Sctructure.pdf` | Arena BOM tree. 991-02053 RFSC assembly → system diagram 622-00043 + seven sub-assemblies (991-01880, -01896, -01899, -01904, -01905, -01907, -01908 = .01–.07) + doc package 601-00036. The doc package holds RF-STD-001 RF Standard and work instructions RF-WI-001–004 (coax install, connector, weatherproofing, bond), RF-INSP-001 Inspection and RF-AML-001 Approved Tools. Those documents aren't in this folder. |

**Drawing findings** (low confidence where noted; check at full zoom)
- **Maxtena 233-00149 connectors:** .07 shows N-M on all four antenna ports, so the drawing agrees with the block diagram. The ICD (Table 2) also says N-male. The SMA-M pigtail in the datasheet is the odd one out; confirm the variant ordered.
- **GNSS antenna 233-00264 (ANT11):** .02 labels J1 as TNC-F. The datasheet says a 60 in pigtail with SMA-M. Still unresolved.
- **PWR_DIV2:** drawn with four ports, so probably 3-way, but the spec sheet on file under 233-00165 is the 2-way model (low confidence).
- **SAILOR 7226 ports:** .02 appears to label **J1 = DSC (TNC-F, loaded with RF-LOAD18)** and **J2 = ANT (TNC-F, to the coax switch)**. The block diagram v0.2 has J1 as the antenna and J2 loaded. That is a possible swap, unconfirmed because the label is small and the manual is too big to read.
- **StreamCaster model:** not shown on .01. The ICD gives the SC4400X TX power as up to 43 dBm (20 W), so the 5 W loads (233-00166) are under-rated unless TX is disabled on J2/J4.
- **Boreas receiver variant:** not shown on .06.
- **Ref des clash:** RF-MDM3 appears to be the Cradlepoint on .07 and the redundant Iridium modem on .04 (low confidence). The workbook says the Rev 10.0 set agrees on every ref des, so check this.
- **Cable type "F250"** appears on .02/.03 (C100, C101, C118, C119), but the notes define only F520. It may be a typo for F520.
- **Possible cable ID clash:** C118 appears on .01 (near ANT14) and on .03 (to ANT18). It may be a misread of C110.

## SpecSheets

Source: **Read** = document opened and read; **Title + WB** = long manual not read, described from its embedded PDF title, page count and the v0.10 workbook's Hardware Inventory tab.

| File (PN) | Doc type | Part | Key specs | Source |
|---|---|---|---|---|
| 233-00139 | Datasheet, 2 p | Silvus StreamCaster SC4400X MANET radio (LOS-MANET) | 4x4 MN-MIMO, bands 300 MHz–6 GHz by option; TX 1 W / 8 W / 20 W (SC4410X / SC4480X / SC44K0X); 4× TNC(f); 9–50 VDC, up to 105 W at 20 W TX; sensitivity −102 dBm @ 5 MHz | Read |
| 233-00140 | Datasheet, 2 p | Septentrio AsteRx RBi3 Pro GNSS/INS receiver | Multi-constellation, multi-frequency; dual-antenna heading; 2× TNC with 5 V / 150 mA LNA bias; 9–32 VDC, 2.5 W max; xPPS 5 ns; tracking C/N0 20 dB-Hz, acquisition 33 dB-Hz | Read |
| 233-00142 | Datasheet, 12 p (2025-04-30) | Ericsson Cradlepoint W1855-5GC outdoor 5G adapter | LTE/NR 600 MHz (B71/n71) to 4.9 GHz (n79), incl. 850 MHz, 2.5 GHz (n41), 3.7 GHz (n77); 4x4 MIMO; TX 23 dBm ±2 (26 dBm HPUE); 4× N(f), 600 MHz–6 GHz; PoE+ 802.3at Class 4 (30 W) only, no DC input; 2× 2.5 GbE; IP67 | Read (agent) |
| 233-00149 | Datasheet + drawing, 4 p | Maxtena NETZ 4-in-1 antenna (100-00142-01) | 2× cell/LTE (698–960, 1710–2170, 2500–2700 MHz, VSWR ≤2.0:1) + 2× Wi-Fi (2.4 / 4.9–5.9 GHz); 25 W; standard SMA-male pigtails, 3 m LL195; IP67/IP69K | Read |
| 233-00150 | Datasheet, 10 p (doc 217-0001-1090) | Southwest Antennas 1009-066 sector panel (LOS-MANET) | Dual-band 2x2 MIMO, 120° az / 13° el, slant ±45°, integrated diplexer; 2.2–2.5 GHz 10.2 dBi, 5.725–5.875 GHz 7.2–7.6 dBi; VSWR <2.0:1; 50 W per port; 2× N(f) | Read |
| 233-00154 | Install & operation manual, 183 p (Raymarine doc 81377) | Raymarine Ray90 (E70492) / Ray91 (E70493) VHF DSC radio | 12 VDC Class D DSC (10.2–16 V, <6 A at 25 W); TX 1 W / 25 W, 156.025–157.425 MHz; RX −119 dBm @ 12 dB SINAD; VHF SO-239 50 Ω; GPS TNC, passive antenna only (no bias); Ray91 adds receive-only AIS. No VSWR detection | Read (agent) |
| 233-00164 / 233-00165 | Datasheet, 2 p (identical files) | Westell CV04-500-629 2-way power splitter (via Talley) | 138–960 MHz; split 3.0 dB + IL ≤0.7 dB; isolation ≥18 dB; VSWR ≤1.3; 50 W; N(f); IP65. Also covers the 3-way CV04-501-629 and 4-way CV04-502-629 | Read |
| 233-00166 | Datasheet, 3 p | Pasternack PE6TR1134 RF load (MANET radio) | 5 W CW (500 W peak, 5 µs / 1 %), DC–12.4 GHz, VSWR ≤1.25:1, TNC male | Read |
| 233-00167 | Datasheet, 3 p | Pasternack PE6TR029 RF load (VoIP repeater) | 50 W CW (5 kW peak), DC–8.5 GHz, VSWR ≤1.2:1 to 4 GHz / ≤1.3:1 to 8.5 GHz, N male, heatsink | Read |
| 233-00168 | Datasheet, 4 p | Pasternack PE6241 RF load (Wi-Fi / Iridium modem J1) | 1 W CW, DC–6 GHz, VSWR ≤1.2:1, RP-SMA male | Read |
| 233-00169 | Outline drawing, 1 p | Amphenol RF 4400 (UG-146/U) adapter | UHF female → N male, DC–300 MHz, VSWR ≤1.3 | Read |
| 233-00170 | Outline drawing, 1 p | Amphenol RF 31-217 (UG-349A/U) adapter | N female → BNC male, DC–11 GHz | Read |
| 233-00214 | Product manual, 9 p (Rev 2) | BWI Eagle (Cattron) Air-Eagle XLT 461-8000-DC E-Stop receiver | 902–928 MHz spread spectrum, 8 selectable networks, built-in repeater; 4 SPDT relays 5 A; 9–36 VDC, 5 W; safety-delay timer 5–90 s; TNC antenna port; IP66 | Read |
| 233-00216 | Product info booklet, 6 p | BWI Eagle 49-3101 omni base antenna (E-Stop) | 698–960 / 1710–2700 MHz, 4.5 dBi, VSWR 1.5:1, N(f), fiberglass, 320 mm | Read |
| 233-00232 | Installation manual, 44 p (IME-36680-J1, Apr 2026) | Furuno DRS6A/12A/25A-NXT radar sensor | Solid-state Doppler X-band 9380–9440 MHz (3 channels); DRS6A 25 W (DRS12A 100 W, DRS25A 200 W); DRS6A 12/24 VDC, 9.5 / 5.0 A max; integral slotted-waveguide array, no RF test port; LAN 100Base-TX to MFD. No sensitivity, VSWR or self-test specs | Read (agent) |
| 233-00264 | Datasheet, 8 p | Pasternack PEANGPS1019-SM-060 GNSS antenna (for AIS) | L1 active, 1559–1606 MHz, LNA gain 40 dB (44.3 dBic), NF 3 dB, VSWR ≤1.8:1; 2.5–16 VDC, 20 mA; 60 in pigtail with SMA male; IP69K | Read |
| 233-00279 | Brochure, 6 p | Furuno FAR-22x8-BB BlackBox radar series | X-band 9410 MHz 12 kW (2218) / 25 kW (2228); S-band 3050 MHz 30 kW magnetron or 250 W solid state; 24 VDC up to 13.7 A (FAR-2228-BB) | Read |
| 233-00298 | Installation manual, 110 p, 24 MB | Cobham SAILOR 7226 VHF transceiver (SAILOR 7222 VHF DSC system) | GMDSS Class A VHF DSC, LAN-controlled black box | Title + WB (too large to open: >20 MB) |
| 233-00299 | Garmin web spec page (printed 11/12/26), 7 p | Garmin Cortex Neuro (010-02815-21) | Remote VHF + AIS Class B SOTDMA + GNSS; VHF TX 156.025–161.600 MHz, 25 W / 1 W, −116 dBm (12 dB SINAD); AIS 5 W, −113 dBm (20 % PER); DSC −115 dBm (1 % BER); 9–33 VDC, 6 A max / 0.7 A nominal @ 12 V; SO-239 (UHF) antenna, BNC splitter, SMA GNSS, RP-SMA Wi-Fi/LTE | Read |
| 233-00300 | Datasheet, 8 p | Pasternack PE71S6519 RF switch | SPDT failsafe electromechanical, DC–12 GHz, 600 W avg; ≤1 GHz: IL ≤0.3 dB, isolation ≥90 dB, VSWR ≤1.25:1; 11–13 VDC coil, 450 mA; switching <20 ms; 3× N(f); IP64 | Read |
| 234-00035 | Datasheet, 2 p | Ground Control RockBLOCK RTU (SAT E-Stop) | Iridium SBD data logger (NTN NB-IoT planned); 8–32 VDC; RS-232/UART + 4 analog/digital inputs; IP68; integrated antenna, no RF connector | Read |
| 242-00266 / 242-00267 | Brochure, 2 p (identical files) | Thales VesseLINK on Iridium Certus 700 (antenna + below-deck terminal) | 352 kbps up / 704 kbps down; terminal 10–32 VDC, TNC to antenna, RP-SMA Wi-Fi, 3× PoE LAN; antenna IP67, powered at 24 VDC by terminal | Read |
| 242-00634 | Datasheet, 11 MB | Maxtena M10HCT-A-TNC GNSS antenna | L1/L2/L5 + L-band active Helicore, TNC, IP67 | Title + WB (could not be loaded: dropped by the reader's request limit) |
| 242-00664 | Reference manual v2.3, 210 p (Dec 2025) | Advanced Navigation Boreas D90 FOG GNSS/INS (manual also covers D70) | 9–36 VDC, 12 W typ; PRI + SEC TNC antenna ports for dual-antenna heading; LNA supply 4.5–4.6 V, 200 mA max, needs ≥33 dB gain at connector; bands set by fitted receiver (X20P or MX5); 1PPS output 5 V / 3.3 V; antenna open/short fault flags; IP67 | Read (agent) |
| 242-00689 | Install & operation manual, 102 p (81390-5, 03-2021) | Raymarine AIS4000 Class A AIS transceiver | VHF 156.025–162.025 MHz, TX 1 W / 12.5 W; RX <−107 dBm @ 20 % PER; 12–24 VDC (10.8–31.2 V), 0.9 A typ / 6.0 A peak @ 12 V; VHF SO-239, GNSS TNC(f) with 5 V bias, active antenna >15 dB gain; VSWR alarm and status screen (good = 3:1) | Read (agent) |
| 446-00546 | Installation manual, 274 p, 46 MB | Furuno FAR-2xx8 series radar | Installation manual | Title + WB (too large to open: >20 MB) |
| SGS100A_specs | Spec sheet v05.01, 16 p (Sep 2026) | R&S SGS100A SGMA RF source (test equipment E03) | CW 1 MHz–6 GHz (B106) or –12.75 GHz (B106 + B112); level −10 to +15 dBm (−120 dBm with B26); VSWR <2.0; max reverse power 0.5 W; rear-panel SMA(f) RF; LAN/SCPI; AC 70 W | Read (agent) |
| ZNL_specs | Spec sheet v10.00, 32 p (Sep 2025) | R&S ZNL VNA family (ZNL14 = test equipment E01) | ZNL14: 5 kHz–14 GHz, 2 ports N(f); output −10 to 0 dBm; damage +27 dBm / 30 V DC; dynamic range >110 dB; options ZNL14-B1 spectrum analysis, ZNL-K3 distance-to-fault; AC 300 W max or optional DC FPL1-B30 | Read (agent) |
| ZNL14_…jpg | Product photo | R&S ZNL14 front panel | — | File name |

**Notes from the spec sheets**
- `233-00149`: the Maxtena datasheet lists SMA-male pigtails as standard, but the block diagram shows ANT22/23 with N-M ports. Confirm what connector was ordered.
- `233-00165`: the drawing marks RF-PWR_DIV2 as "3-way [?]". The file is a copy of the 2-way CV04-500-629 sheet, but the same datasheet also covers the 3-way CV04-501-629 (split 4.8 dB, IL ≤1.6 dB).
- `233-00216`: the cover says "900 MHz", but the spec table lists 698–960 MHz and 1710–2700 MHz.
- `242-00266` / `242-00267`: one brochure covers both the antenna and the below-deck terminal, so the antenna has no separate datasheet.
- `233-00166`: these 5 W CW loads terminate the unused StreamCaster ports J2/J4 (block diagram sheet 3). The 233-00139 radio is listed at up to 20 W per the workbook (SC44K0X). If the radio can transmit on J2/J4, a 5 W load would be overdriven. Confirm the radio model and that TX is disabled on those ports.
- `233-00264`: the datasheet shows a 60 in pigtail ending in an SMA male, but the block diagram (sheet 6) shows RF-ANT11 J1 as TNC-F, with C208 replaced by a TNC test cable. Confirm the connector, or add an SMA-to-TNC adapter to the test kit.
- `233-00150`: the datasheet gives two figures for C-band peak gain, 7.2 dBi in the features list and 7.6 dBi in the spec table.
- **ZNL14 input protection:** the damage level is +27 dBm (0.5 W). The AIS4000 transmits up to 12.5 W (+41 dBm), the Ray90/91 and Cortex 25 W, the SC4400X up to 43 dBm (20 W, per the ICD), the NXR-1700 VoIP repeater up to 50 W (+47 dBm, 20 dB over, per the ICD), and the 5G adapter about 26 dBm. Any TX measurement into the ZNL needs high-power attenuators. The ZNL sheet lists the R&S RBU100/RBU50/RDL50 attenuators and ZN-B13 limiter as accessories.
- **Boreas D90 bias:** it supplies 4.5–4.6 V / 200 mA to its antennas, not 5 V. Check the M10HCT-A-TNC's minimum supply voltage against that.
- **Ray90/91 GPS port:** it needs a passive antenna and provides no bias.
- **Manuals vs filenames:** the Boreas manual also covers the D70, the Furuno DRS manual covers three models (only the DRS6A is 25 W / 12 V-capable), and the Ray manual covers Ray90 and Ray91. The Boreas receiver variant (X20P or MX5) isn't identified anywhere in the folder.
- **Not read:** `446-00546` (46 MB) and `233-00298` (24 MB) exceed the reader's 20 MB limit, and `242-00634` (11 MB) was dropped twice. The SAILOR J1/J2 port claims and the FAR-2xx8 power figures remain unverified.

## ICD and design documents (`ICD_DOCs`)

| Document | Contents |
|---|---|
| `MUSV RF-COMM ICD Rev6.pdf` | *ICD – RF Sensors and Communications* Rev 6.0, 43 p, Saronic Proprietary. Rev 1 dated 10/31/2025, Rev 6 dated 10/28/2026, all revisions by David Cobos. Covers the RF-Comm sub-system's interfaces to the VSM and power electronics: subsystem descriptions (§3), antenna summary (Table 1: gain, FOV, polarization, band), RF interfaces (Table 2: port count, connector, cable type, max length, length matching), electrical (Table 3: voltage, connector, power), data (Table 4), key RF performance (Table 5: TX power, EIRP, RX sensitivity), FOV and keep-out zones with 3D renders (§8, Figs 1–9, all TBR), and placement rules (§9). §10–16 are TBS or point to Appendices A, B, C and F, which aren't in the folder. |
| `Marauder RFSC - EWIS Handover Pkg.pptx` | 9-slide handover to EWIS, last updated 11/15/2026. System overview: four GNSS/INS chains (one Boreas D90 and three Septentrio RBi3, eight antennas); Starlink Gen3 and Thales VesseLINK, each 2-for-1; six Silvus SDRs on six 120° sectors (a primary and a cold-standby twin per sector); RockBLOCK 2-for-1 and one BWI Eagle receiver with two antennas; S-band FAR-2238S and X-band DRS25A-NXT radars; AIS4000; Ray90 with an NXR-1700 VoIP repeater; one W1855. Links to Arena, the RF work instructions, the Zuken net schematics and `440-001_rf_eng_bom_assembly_2.1v.xlsx` (hardware and coax tabs), none of which are in the folder. Install notes: F520 for every cable leaving the vessel's interior, LMR-240-DB allowed inside but F520 preferred, interconnects no shorter than 12 in, separate RF from power and noisy cables, bond both ends of RF cables, check connectors and lengths against the pull schedule. Slides 3 and 4 are duplicates. |
| `Marauder VHF Antennas - Decision 11-04-2026 Update.pptx` | 5-slide decision brief (Nov 2026, for David Muller and Geoffrey Single). Recommends Option B: move both VHF antennas ("red" and "blue") off their current mounts (item #15). The red antenna is blocked by the FLIR camera and its mount, and could interfere with it. The blue one is shadowed by the deck top and sits near the rails and stairs where crew work. No decision outcome is recorded. |

**What the ICD documents change** (to confirm with RF engineering)
- **Radar models differ from the test docs.** The ICD (Rev 4 onward) and the handover package specify the X-band **DRS25A-NXT** (200 W, 24 V, 134.4 W max) and the S-band **FAR-2238S-NXT-BB** (230 VAC). TR-007 and the workbook list the DRS6A-NXT (25 W) and the FAR-22x8 / FAR-2xx8 family. The DRS manual on file covers the DRS25A, so it can be used for the limits.
- **VHF line-up differs.** The ICD and handover package list the Ray90, the AIS4000 and a Kenwood NXR-1700 VoIP repeater (136–174 MHz, receive-only VoIP, 25 or 50 W TX). The SAILOR 7226 and Garmin Cortex in TR-006 and the workbook aren't mentioned, and the NXR-1700 isn't in TR-006. The ICD marks all three VHF/AIS units and the E-Stop receiver "under review". The ICD (Rev 6, 10/28) predates drawing .02 (Rev 10.0, 11/16), so confirm which baseline is current before acting on the SAILOR J1/J2 question.
- **VoIP repeater load.** The 233-00167 load (50 W CW) is labelled for the VoIP repeater, which the ICD rates at up to 50 W TX. That leaves no margin, so confirm that the repeater's TX is disabled or set to 25 W.
- **Cable types disagree with the drawings.** For the LOS E-Stop, the ICD says LMR-400 (12 m max) but drawing .03 says C120 is LMR-240. For Cell/LTE, the ICD says F520 (6 m max) but drawing .07 says C121–C124 are LMR-195. The handover notes say external runs must be F520.
- **AIS GNSS connector.** The ICD lists it as UHF-F. The AIS4000 manual and drawing .02 say TNC, so the ICD entry is probably a typo.
- **Max cable lengths for the test cable list.** GNSS 12 m, length-matched; LOS 3 m, length-matched; VHF and AIS 6 m on LMR-400; LOS E-Stop 12 m; Cell/LTE 6 m, length-matched.
- **Candidate EOL limits from Table 5 (at the antenna aperture).** GNSS C/N0 ≥ 40 dB-Hz. AIS RX ≤ −99 dBm at 20 % PER. Ray90 RX ≤ −102 dBm at 12 dB SINAD. SC4400X RX ≤ −74 dBm at MCS0, 20 MHz. W1855 RX ≤ −96 dBm. E-Stop and VoIP values are TBD.
- **Starlink model.** The ICD names the Flat High Performance terminal (49 V PoE, 150 W max), which partly closes the "model not specified" gap.
- **The relocated VHF antennas will need new cable runs.** If Option B is approved, check the new runs against the ICD's 6 m VHF limit and the ≥ 80° cone between the VHF/AIS and GNSS antennas (Fig 15).
- **Internal ICD inconsistencies:**
  - Table 1 labels Starlink 10.7–12.7 GHz as uplink and 14.0–14.5 GHz as downlink, the reverse of §3.1.2 and Table 5.
  - §3.1.2 gives the uplink as 14–14.7 GHz.
  - Iridium data rates are 256/702 kbps in §3.1.3 and 352/704 kbps in Table 5.
  - The S-band frequency is 3073.75 MHz in Table 1 and 3063.75 MHz in Table 5.
  - The X-band row in Table 5 has leftover tracked-change text ("9.44 GHz400 MHz ± 60 MHz", "52.149.9 dBW").
  - The Silvus supply reads "2415 V DC" and the repeater supply "13.2 V DC24 V DC".

## `MUSV_RF_Test_Setup_Block_Diagram_v0.2.pdf`

A seven-sheet draft from Nov 19 that maps every MUSV RFSC test hookup, using the tags from the v0.9 workbook BOM:

1. Rack, cart, power and instrument LAN
2. Incoming inspection (IQC) bench setups
3. GNSS and LOS-MANET sub-assembly tests
4. SAT-TER and E-Stop sub-assembly tests
5. End-of-line (EOL) integration at FLA
6. VHF/AIS
7. Radar and Cell/LTE

It flags the missing equipment in orange: power sensor, spectrum option, radio/AIS tester, higher-power DC supply, SIM cards and the waveguide adapter.
