<!-- prettier-ignore-start -->

# ATM Simulation CLI ⭐️

[![npm version](https://img.shields.io/npm/v/@edeveloper132-ilyas/atmsystem)](https://www.npmjs.com/package/@edeveloper132-ilyas/atmsystem) [![license](https://img.shields.io/npm/l/@edeveloper132-ilyas/atmsystem)](LICENSE) [![node version](https://img.shields.io/node/v/@edeveloper132-ilyas/atmsystem)](#requirements)

> A fully interactive, terminal‑based ATM simulator with PIN management, transactions, balance inquiry, and integration hooks. Perfect for demos, teaching, or embedding in larger CLI tools.

---

## 📋 Table of Contents

* [✨ Features](#-features)
* [🚀 Installation](#-installation)
* [💻 Usage](#-usage)

  * [Programmatic API](#programmatic-api)
  * [CLI Invocation](#cli-invocation)
* [📝 Examples](#-examples)
* [⚙️ Configuration](#️-configuration)
* [🔗 API Reference](#-api-reference)
* [🏷️ Keywords](#️-keywords)
* [🤝 Contributing](#-contributing)
* [🛡️ License](#️-license)
* [📫 Contact](#️-contact)

---

## ✨ Features

* 🔒 **PIN Management**

  * **Setup:** Create a secure 3‑digit PIN (100–999).
  * **Change:** Verify old PIN before updating.
  * **Recovery:** Reset PIN via your registered 13‑digit CNIC/NIC.
* 💰 **Transactions**

  * **Deposit:** Minimum ₹500 per transaction.
  * **Withdraw:** Withdraw up to your balance; maintain a minimum ₹100.
* 📊 **Balance Inquiry**

  * Instantly view your current balance.
* 🔄 **Integration Hooks**

  * `onExit(callback)`: Run custom logic when ATM session ends.
* 🎨 **Customizable**

  * Programmatic functions `plusBalance` & `minusBalance` for advanced demos.

---

## 🚀 Installation

Install from npm under your scope:

```bash
npm install @edeveloper132-ilyas/atmsystem
```

Or add as a project dependency:

```bash
yarn add @edeveloper132-ilyas/atmsystem
```

> **Requires** Node.js v14 or higher. Ensure your terminal supports modern ANSI colors.

---

## 💻 Usage

### Programmatic API

Import and embed the ATM in any Node.js application:

```ts
import { ATM, getBalance, plusBalance, minusBalance, onExit, NIC } from "@edeveloper132-ilyas/atmsystem";

// Optional: Hook to run after ATM session completes
onExit(() => {
  console.log("🔄 Returned from ATM to host application. Final balance:", getBalance());
});

// Launch interactive ATM
await ATM();
```

### CLI Invocation

Use npx or your local binary to start the ATM directly:

```bash
# via npx
npx @edeveloper132-ilyas/atmsystem

# if installed globally
atmsystem
```

---

## 📝 Examples

### 1️⃣ Full Session

```bash
$ npx @edeveloper132-ilyas/atmsystem
|||||||||||||||| WELCOME TO OUR BANK'S ATM ||||||||||||||||||||||

? Please enter your NIC Number here: 3210123456789
? Please enter your new PIN here: 123
✔ Your PIN 123 has been set successfully!

? Select an action:
  ❯ Deposit Amount
    Withdraw Amount
    Check Balance
    Manage PIN
    Exit

# Deposit ₹1000
? Enter deposit amount: 1000
✔ Amount deposited: ₹1000
ℹ Current balance: ₹1000

# Withdraw ₹400
? Enter withdrawal amount: 400
✔ Amount withdrawn: ₹400
ℹ Current balance: ₹600

# Recover PIN
? Manage PIN -> Recover PIN
? Enter your CNIC: 3210123456789
✔ Verification successful!
? Enter your new PIN: 321
✔ PIN updated successfully!

# Exit
Thank you for using our ATM service!
Goodbye 👋
```

---

## ⚙️ Configuration

No external config files required. All settings are in‑memory and reset per session.

> **Tip:** Use `plusBalance` and `minusBalance` in tests to simulate initial bank balance.

---

## 🔗 API Reference

| Member                 | Type                    | Description                                          |
| ---------------------- | ----------------------- | ---------------------------------------------------- |
| `ATM()`                | `Promise<void>`         | Launch interactive ATM CLI.                          |
| `getBalance()`         | `(): number`            | Get current balance.                                 |
| `plusBalance(amount)`  | `(n: number) => number` | Increase balance programmatically (for demos/tests). |
| `minusBalance(amount)` | `(n: number) => number` | Decrease balance programmatically.                   |
| `NIC`                  | `number`                | Registered 13‑digit CNIC/NIC of the user.            |
| `onExit(callback)`     | \`(fn: () => void       |                                                      |

```
                       | Register a hook when ATM session ends.                           |
```

---

## 🏷️ Keywords

```yaml
keywords:
  - atm
  - bank
  - cli
  - simulation
  - pin
  - cnic
  - nic
  - nodejs
  - typescript
  - demo
```

---

## 🤝 Contributing

Love this project? Please contribute:

1. **Fork** the repo
2. **Clone**: `git clone https://github.com/eDeveloper132/ATM_SYSTEM.git`
3. **Branch**: `git checkout -b feature/YourFeature`
4. **Commit**: `git commit -m "Add YourFeature"`
5. **Push**: `git push origin feature/YourFeature`
6. **PR**: Open a Pull Request against `main`

Follow the code style and include tests for any new functionality.

---

## 🛡️ License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📫 Contact

👤 **Muhammad Ilyas**

* GitHub: [edeveloper132-ilyas](https://github.com/eDeveloper132)
* npm: [edeveloper132-ilyas](https://www.npmjs.com/~edeveloper132-ilyas)

> Crafted with ❤️ and ☕

<!-- prettier-ignore-end -->
