# 📦 PeykLink - P2P Logistics & Delivery Platform (Beta)

> **Note:** The source code for this project is currently private as it is a pre-release startup. This repository serves as a technical showcase of the architecture, UI/UX, and security implementations.
<div align="center">
  <img src="https://raw.githubusercontent.com/tourajshah/PeykLink-Showcase/main/assets/PL-SC.gif" width="25%" />
  
  📺 **[Watch Full 60FPS Demo on YouTube ->](https://www.youtube.com/watch?v=GyoMVWgLNFk)**
</div>

## 🚀 Technical Overview
PeykLink connects international travelers with local shoppers, acting as a secure escrow and delivery verification platform. It was built from the ground up prioritizing 60FPS animations, native-like gesture controls, and cryptographically secure transactions.

### 🛠 Tech Stack
* **Frontend:** React Native (Expo), TypeScript
* **Animations & Graphics:** React Native Reanimated (v3/v4), `@shopify/react-native-skia`
* **Backend & Real-time:** Convex (WebSocket optimized)
* **Security:** Web Crypto API (`AES-GCM`, `SHA-256`)
* **State Management & State:** React Context, custom hooks with `React.memo` optimization

## 🔐 Core Engineering Highlights

### 1. Bank-Grade Delivery Verification
Replaced standard pseudo-random number generation (`Math.random`) with native `crypto.getRandomValues` for secure 6-digit delivery codes. 
* **Encryption:** Implemented two-way `AES-GCM` symmetric encryption, strictly enforcing 32-byte (256-bit) keys. The initialization vector (IV) is safely stored alongside the encrypted payload.
* **Decryption:** Decryption logic is seamlessly embedded within Convex queries, resolving the plaintext code in a single network request while safely evaluating user permissions.

### 2. High-Performance UI (60FPS)
* **Skia Integration:** Utilized `@shopify/react-native-skia` for high-performance `BackdropBlur` and `Canvas` rendering, replacing heavy DOM-based styling.
* **Scroll Physics:** Built complex scroll interpolations replacing legacy `Animated` API with `react-native-reanimated`.
* **Memory Optimization:** Eliminated heavy Lottie animations inside scrollable lists and refactored layout animations to resolve severe infinite loop/transform overwrite conflicts.

## 📸 Screenshots

| Smart Radar Dashboard | 3D Discovery Cards | User Wallet & Identity |
|:---:|:---:|:---:|
| <img src="https://raw.githubusercontent.com/tourajshah/PeykLink-Showcase/refs/heads/main/assets/PL-EXPLORE-SC.png" width="75%" /> | <img src="https://raw.githubusercontent.com/tourajshah/PeykLink-Showcase/refs/heads/main/assets/PL-HOMESCREEN-SC.png" width="75%" /> | <img src="https://raw.githubusercontent.com/tourajshah/PeykLink-Showcase/refs/heads/main/assets/PL-PROFILE-SC.png" width="75%" /> |

## 💡 Status
Currently in Beta testing.
