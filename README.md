# 📦 InAppKit-iOS

**InAppKit-iOS** is a high-performance, lightweight Swift framework designed to manage in-app purchases and subscriptions. It serves as the official iOS client for the InAppKit ecosystem, providing a seamless bridge between your app and secure server-side validation.


---

## ✨ Features

* **StoreKit 2 Integration:** Built from the ground up using Apple's latest Swift-native APIs.
* **Secure Validation:** Works in tandem with **InAppKit-Server** to perform server-side receipt validation (SSRV), preventing local bypasses and fraud.
* **Remote Paywalls:** Change your subscription offers, pricing, and UI metadata remotely without a new App Store submission.
* **Subscription Lifecycle:** Robust handling of renewals, expirations, grace periods, and refunds.

## 🚀 Installation

### Swift Package Manager (SPM)
In Xcode, go to `File > Add Packages` and enter the repository URL:
`https://github.com/Dijital-Vizyon/InAppKit-iOS`

## 💻 Usage

### 1. Initialize
Configure the SDK in your `AppDelegate` or `@main` App struct:

```swift
import InAppKit

InAppKit.shared.configure(apiKey: "YOUR_DV_API_KEY")

```

### 2. Purchase a Product

```swift
InAppKit.shared.purchase(productID: "com.dv.premium.monthly") { result in
    switch result {
    case .success(let transaction):
        print("Purchase successful! Expiry: \(transaction.expiryDate)")
    case .failure(let error):
        print("Purchase failed: \(error.localizedDescription)")
    }
}

```

### 3. Restore Purchases

```swift
InAppKit.shared.restorePurchases { success in
    if success {
        print("Purchases restored successfully.")
    }
}

```

---

© 2026 **Digital Vision**. Distributed under the MIT License.
