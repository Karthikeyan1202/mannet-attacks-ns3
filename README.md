# 🛰️ MANET Attacks & Defences in NS-3

**A Comprehensive NS-3 Simulation Framework for Modern MANET Security Research**  
---

## 🚀 Overview

Dive deep into the security challenges of Mobile Ad Hoc Networks (MANETs) with this extensive, hands-on simulation framework, meticulously crafted for **routing-layer attack** exploration via NS-3. Focus centers on the most disruptive real-world threats—**RREQ Flooding** and **Sybil Identity** attacks—along with resilient, lightweight **defence mechanisms** rigorously evaluated for effectivity.

**Key Features:**
- **Granular performance metrics:** PDR, packet drops, throughput analytics
- **Wireshark compatibility:** Packet-level trace export for detailed forensic study
- **NetAnim support:** Real-time network topology and node mobility visualization
- **Scalability:** Node-level simulation, perfect for academic research and real-world prototype validation

---

## ⚙️ Attack Mechanisms

### 🔸 RREQ Flooding Attack
- **Concept:**  
  Malicious nodes destabilize routing by bombarding the network with a flood of fake Route Request (RREQ) packets in AODV.
- **Implementation:**  
  - Attack rate: ~480 RREQs/sec  
  - Short bursts: 3–5 requests every few milliseconds  
  - Spoofed destination addresses poison authentic routing tables
- **Network Impact:**  
  - Chokes CPU and bandwidth resources  
  - Overflows routing tables, inflicting crippling congestion  
  - Can plummet Packet Delivery Ratio (PDR) to as low as ~0.7%

### 🔸 Sybil Identity Attack
- **Concept:**  
  A single adversary node projects multiple fabricated IP identities (e.g., 10.0.0.200–205) to impersonate several network nodes.
- **Implementation:**  
  - Cyclic bursts of transmissions, each with a spoofed identity  
  - Simulates a coordinated attack from multiple false sources
- **Network Impact:**  
  - Induces routing confusion and surges in control overhead  
  - Amplifies congestion, dropping PDR to an alarming ~29%

---

## 🛡️ Defence Mechanisms

### 🔹 RREQ Flooding Defence
- **Rate Limiting:** Strictly enforces a ≤3/sec RREQ threshold per node  
- **Reputation Management:** Monitors, tracks, and isolates persistent violators  
- **Packet Filtering:** Real-time packet validation leveraging IPv4 event hooks  
- **Impact:** Successfully blocks >90% of malicious RREQs and sharply boosts PDR from 0.71% to 76.43%

### 🔹 Sybil Defence
- **Burst Detection:** Flags any source dispatching ≥4 packets in a 5-second window  
- **Anomaly Analytics:** Identifies irregular, rapid packet patterns  
- **Violation Counting:** Instantly blacklists repeat offenders  
- **Impact:** Filters ~1,479 spoofed packets and sustains **100% legitimate PDR** under attack

---

## 📊 Results at a Glance

| Scenario            | PDR (%) | Packets Sent | Packets Blocked | Network Status |
|---------------------|---------|--------------|-----------------|----------------|
| **Flooding Attack** | 0.71    | 14,397       | --              | Unstable       |
| **Flooding Defence**| 76.43   | 14,397       | 1,909           | Stable         |
| **Sybil Attack**    | 29.73   | 147          | --              | Congested      |
| **Sybil Defence**   | 100.00  | 27,000       | 1,479           | Stable         |

**Key Insights:**
- Flooding defence mechanisms rapidly restore network throughput and connectivity with minimal overhead.
- Sybil defence achieves complete mitigation—absolutely no legitimate packet drops, even during active attacks.
- Both methods proactively neutralize attackers, maintaining system resilience at minimal performance cost.

---

## 🧪 Simulation Snapshots

### Flooding Attack
![Flooding Attack](results/images/flooding-attack-result.png)

### Flooding Defence
![Flooding Defence](results/images/flooding-attack-defence.png)

### Sybil Attack
![Sybil Attack](results/images/sybil-attack-result.png)

### Sybil Defence
![Sybil Defence](results/images/sybil-defence-result.png)

---

Unlock a practical, scalable, and visually insightful approach to MANET security research—directly within NS-3.
