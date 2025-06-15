# 🧠 DNS_exfil: DNS Exfiltration Detection Dataset

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC--BY--NC%204.0-blue.svg)](LICENSE)
![Last Updated](https://img.shields.io/badge/last%20updated-June%202025-blue)
[![Cite this Dataset](https://img.shields.io/badge/cite-paper-orange)](#-citation)

This repository contains a custom-generated dataset and supporting documentation for detecting DNS exfiltration attacks using machine learning.

---

## 🔬 Overview

This dataset accompanies a research paper that explores the use of supervised ML to detect DNS exfiltration attacks. It includes both benign and malicious DNS traffic captured in a virtualized testbed.

---

## ⚙️ Experimental Setup

The environment includes:
- 🖥️ **Target PC** – Contains the sensitive file to be exfiltrated.
- 🧱 **DNS Server** – Handles legitimate DNS requests.
- 🐧 **Monitor Node** – Runs [Argus](https://www.qosient.com/argus/) and Wireshark.
- 🧪 **Kali Linux (Attacker)** – Launches DNS exfiltration via:
  - [`dnscat2`](https://github.com/iagox86/dnscat2)
  - A custom Python script

---

## 📦 Dataset Structure

```
dataset_v1/
├── benign/         # Legitimate DNS traffic (.pcap)
├── malicious/      # Exfiltration traffic (.pcap)
└── features/       # Pre-extracted features (.csv)
```

---

## 🧠 Example Use

```bash
# Convert pcap to argus
argus -r malicious/sample1.pcap -w sample1.argus

# Extract features
ra -r sample1.argus -s stime dur proto saddr daddr dport bytes pkts ...
```

---

## 📄 Citation

If you use this dataset, please cite:

```bibtex
@misc{dns_exfil_dataset,
  author       = {Rajesh Thomas and Suleiman Y. Yerima and others},
  title        = {DNS Exfiltration Attack and Dataset Generation for Machine Learning-based Detection},
  year         = {2025},
  howpublished = {\url{https://github.com/cyberjonlab/DNS_exfil/tree/main/dataset_v1}},
  note         = {Accessed: 2025-06-15}
}
```

---

## 📜 License

This dataset is licensed under the [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) license.

📌 Free for academic and research use **with citation**.  
🚫 Commercial use is **not permitted without prior approval**.  
📩 For licensing, contact: [rthomas1@hct.ac.ae](mailto:rthomas1@hct.ac.ae)
