## 🛠️ **Aiken Smart Contract — Custodial Staking Architecture**

### 🔧 **Handles Overview**

1. **`Spend`** – Used to **lock ADA** into the script.
2. **`Publish`** – Used to **delegate** or **deregister** the stake.
3. **`Withdraw`** – Used to **withdraw staking rewards** for the user.

---

### 🧾 **Handle Behaviors and Rules**

#### ✅ **Spend** (Lock Funds)

- Purpose: Users lock a defined amount of ADA (`LOCKAMOUNT`) into the script.
- Result: Funds are held under the script's control, associated with the user's stake key in the datum.

#### ✅ **Publish** (Delegate or Deregister)

- **Delegation**:

  - Allowed **only if** `LOCKAMOUNT` is present in the script under the user's credentials.
  - Ensures that the stake delegation certificate matches the user’s stake key.

- **De-registration**:

  - Allowed **only when** the corresponding `LOCKAMOUNT` is **being withdrawn** from the script in the same transaction.

#### ✅ **Withdraw** (Withdraw Rewards)

- Used to withdraw staking **rewards** associated with the user's stake key.
- Ensures the reward withdrawal is valid and belongs to the correct user.

---

### 🏦 **Reward Attribution Mechanism**

To ensure rewards are also calculated for locked amount (`LOCKAMOUNT`), we construct a **combined address** like this:

```plaintext
Address {
  paymentCredential: scriptCredential,
  stakingCredential: userStakeCredential
}
```

This hybrid address:

- Gives **control over funds** to the script (enabling locking logic).
- Routes **staking rewards** to the user’s stake key.

---
