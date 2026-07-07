![Repo Size](https://img.shields.io/github/repo-size/roshhellwett/projectpaynix?style=for-the-badge)
![Stars](https://img.shields.io/github/stars/roshhellwett/projectpaynix?style=for-the-badge)
![Forks](https://img.shields.io/github/forks/roshhellwett/projectpaynix?style=for-the-badge)
![Issues](https://img.shields.io/github/issues/roshhellwett/projectpaynix?style=for-the-badge)
![Windows](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows)

# PROJECT PAYNIX

PayNix is a highly robust, terminal-based Point of Sale (POS) and inventory management application. Engineered with a "security-first" mindset, PayNix features encrypted data storage, strict buffer-overflow protections, atomic financial transactions, and role-based access control.

---

## Key Features

### Security & Data Integrity
- **Role-Based Access Control (RBAC):** Distinct admin and employee interfaces.
- **Brute-Force Protection:** Progressive time delays on failed login attempts.
- **Safe Memory:** Custom `SafeString` implementation prevents buffer overflows.
- **Binary Protection:** Database files use magic number validation (`PNIX`), schema versioning, and checksums.
- **Schema Migration:** Graceful handling of schema changes with legacy data archiving.
- **OS Signal Traps:** Handles `SIGINT` and `SIGTERM` to flush buffers and lock vaults on shutdown.

### Financial & Billing Engine
- **Integer Math:** Uses integer cents to avoid floating-point rounding issues.
- **Atomic Transactions:** Validates inventory before processing — prevents race conditions and negative stock.
- **Live Terminal:** Real-time cart editing, stock viewing, quantity management.
- **JSON Export:** Transactions exported to secure JSON format.
- **Z-Reports:** Automated end-of-day revenue and audit reports.

### Inventory Management
- Full CRUD for items (Add, Update, Soft-Delete).
- Stock validation and automated deductions.

## 🛠️ Prerequisites

To build and run PayNix, you will need:
* **CMake:** Version 3.20 or higher.
* **C++ Compiler:** C++20 compatible compiler (GCC, Clang, or MSVC).
* **Threads:** OS-level threading support (pthreads/Windows threads).

## 🚀 Build Instructions

PayNix uses CMake for cross-platform compilation. Follow these steps to build from source:

1. **Clone the repository:**
```bash
    git clone https://github.com/roshhellwett/projectpaynix.git
   cd projectpaynix
```

---

## 📂 Project Structure
```
projectpaynix/
├── CMakeLists.txt        # Build configuration
├── security.md           # Vulnerability reporting & supported versions
├── include/              # Header files
│   ├── Core.hpp          # System constants, types, and logging
│   ├── Data.hpp          # Secure binary repository patterns
│   ├── Logic.hpp         # Business logic (Auth, Inventory, Billing)
│   ├── Models.hpp        # Data structures and SafeStrings
│   ├── Security.hpp      # Cryptography, hashing, and sanitization
│   └── UI.hpp            # Terminal rendering and inputs
└── src/                  # Implementation files
    ├── Logic.cpp         
    ├── UI.cpp            
    └── main.cpp          # Application entry point & OS traps

```

---

© 2026 [Zenith Open Source Projects](https://zenithopensourceprojects.vercel.app/). All Rights Reserved. Zenith is an Open Source Project Idea by @roshhellwett
