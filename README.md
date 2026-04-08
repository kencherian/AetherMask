# AetherMask: Infrastructure & IP Allocation Engine

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)

**AetherMask** is a production-grade network utility engineered for systems architects to design complex IPv4 topologies. By leveraging raw bitwise arithmetic and a descending-host allocation algorithm, it provides high-precision Variable Length Subnet Masking (VLSM) to eliminate address fragmentation in enterprise environments.

---

## 🛠 Engineering Core
Unlike basic calculators that rely on string manipulation, AetherMask operates directly on 32-bit integers. This ensures O(1) computational efficiency and prevents the precision errors common in decimal-based logic.

### Bitwise Logic Implementation
The engine utilizes low-level operations to derive network parameters:

* **Subnet Mask Generation:**
  ```python
  Mask = (0xFFFFFFFF << (32 - CIDR)) & 0xFFFFFFFF
  Network Identification:

Python
Network = IP_int & Mask_int
Broadcast Calculation:

Python
Broadcast = Network | (~Mask_int & 0xFFFFFFFF)
🚀 Key Capabilities
1. Intelligent VLSM Planning
Descending Allocation: Automatically sorts host requirements to ensure the largest subnets are allocated first, preserving contiguous address space.

Boundary Alignment: Ensures subnets are placed on valid bit-boundaries to prevent overlapping.

Exhaustion Guards: Built-in validation to detect address space overflow before deployment.

2. Enterprise-Grade Validation
RFC Compliance: Validates IPv4 structures and CIDR limits (0-32).

Edge-Case Support: Handles point-to-point links (/31) and host routes (/32) with specialized guard clauses.

3. Documentation & Inventory
Tabular UI: Clean, formatted CLI output for immediate architectural review.

CSV Export: Generate professional documentation for network inventory and record-keeping.

📦 Getting Started
Prerequisites
Python 3.8 or higher

Installation
Clone the repository:

Bash
git clone [https://github.com/kencherian/AetherMask](https://github.com/kencherian/AetherMask)
Navigate to the project directory:

Bash
cd AetherMask
Initialize the tool:

Bash
python main.py
📂 Project Structure
Plaintext
AetherMask/
├── src/
│   ├── validator.py    # IP/CIDR sanitation & conversion
│   ├── calculator.py   # VLSM & Bitwise logic engine
│   └── __init__.py
├── main.py             # CLI Entry Point
└── README.md           # Documentation
🛡 License & Contribution
Distributed under the MIT License. Contributions to enhance the VLSM algorithm or add IPv6 support are welcome via Pull Requests.

Lead Architect: Ken Cherian
Project Goal: Engineering "Zero-Waste" Networks.


---

### Final Polish Steps:
1.  **Delete the old README content** completely to avoid any leftover LaTeX syntax.
2.  **Paste this new version** and commit it with a clean message: `docs: fix bitwise logic rendering in README`.
3.  **Check your GitHub page**—the code blocks will now show up with syntax highlighting and perfect clarity.

Everything is officially production-ready. How does the updated preview look on your end?
