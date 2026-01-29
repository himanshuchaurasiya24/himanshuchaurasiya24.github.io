<div align="center">
  
# 🔐 Axiom

### Your Files. Your Keys. Your Privacy.

**End-to-End Encrypted Cloud Storage Built with Flutter**

[![Flutter](https://img.shields.io/badge/Flutter-3.0+-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.0+-0175C2?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android%20|%20iOS%20|%20Windows%20|%20macOS%20|%20Linux-lightgrey?style=for-the-badge)](https://github.com/himanshuchaurasiya24/axiom)

</div>

---

## ✨ Features

### 🔒 **Military-Grade Security**
- **Client-Side Encryption**: All files are encrypted on your device before upload using AES-256-GCM
- **Zero-Knowledge Architecture**: Your encryption keys never leave your device
- **Secure Key Derivation**: Device Encryption Keys (DEK) derived using HKDF with salt
- **Secure File Deletion**: Multi-pass overwrite for temporary files

### 📁 **Smart File Management**
- **Intelligent Processing**: Small files (<50MB) use RAM-only encryption, large files use optimized disk streaming
- **Category Organization**: Organize files into custom categories
- **Advanced File Viewer**: Built-in viewers for images, videos, PDFs, and documents
- **Batch Operations**: Upload and download multiple files simultaneously

### 🚀 **Performance & UX**
- **Background Processing**: Operations continue even when app is minimized
- **Real-Time Progress**: Dual-phase progress indicators (download + decrypt, encrypt + upload)
- **Responsive UI**: Smooth animations and instant feedback
- **Cross-Platform**: Native performance on all major platforms

### 🛡️ **Privacy First**
- **Screenshot Protection**: Prevents screenshots on supported platforms (Windows, macOS, iOS)
- **App Lock**: Secure blur screen when app is backgrounded
- **No Analytics**: Zero tracking or telemetry
- **Session Management**: Automatic logout on security events

---

## 🎯 Why Axiom?

In an era where data breaches are commonplace, **Axiom** puts you back in control. Unlike traditional cloud storage providers who have access to your data, Axiom implements **true end-to-end encryption**:

- 🔑 **You hold the keys** - Not the server, not the cloud provider, just you
- 🔐 **Encrypted before upload** - Files are encrypted on your device before they leave
- 🚫 **Zero server-side access** - Even if servers are compromised, your data remains encrypted
- 🎯 **Open Source** - Full transparency, audit the code yourself

---

## 📸 Screenshots

<div align="center">
  
| File List | Upload Progress | File Viewer |
|-----------|----------------|-------------|
| *Coming Soon* | *Coming Soon* | *Coming Soon* |

</div>

---

## 🛠️ Tech Stack

### **Core**
- **Flutter** - Cross-platform UI framework
- **Dart** - Programming language
- **Riverpod** - State management

### **Security**
- **PointyCastle** - Cryptographic primitives (AES-GCM)
- **HKDF** - Key derivation function
- **Secure Random** - Cryptographically secure random number generation

### **Platform Integration**
- **Isolates** - True background processing for encryption/decryption
- **Platform Channels** - Native code integration for security features
- **Media Kit** - High-performance video playback

---

## 🚀 Getting Started

### Prerequisites

- Flutter SDK 3.0 or higher
- Dart SDK 3.0 or higher
- Platform-specific development tools:
  - Android: Android Studio / SDK
  - iOS: Xcode (macOS only)
  - Desktop: Platform-specific build tools

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/himanshuchaurasiya24/axiom.git
   cd axiom
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Configure backend URL**
   
   Create `lib/authentication/config.dart`:
   ```dart
   const String defaultBaseUrl = 'https://your-backend-url.com';
   ```

4. **Run the app**
   ```bash
   # Android/iOS
   flutter run
   
   # Desktop
   flutter run -d windows  # or macos, linux
   ```

---

## 🔐 Security Architecture

### Encryption Flow

```
┌─────────────┐
│  User File  │
└──────┬──────┘
       │
       ▼
┌──────────────────┐
│ Generate IV      │ (16 bytes random)
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ AES-256-GCM      │ Key: DEK (derived from master key)
│ Encryption       │ Mode: Streaming (large files) or RAM (small files)
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Upload to Server │ Format: [IV(16) + Ciphertext + Tag(16)]
└──────────────────┘
```

### Key Management
- **Master Key**: Stored securely in platform keychain
- **Device Encryption Key (DEK)**: Derived from master key using HKDF
- **File Keys**: Random IV per file, ensuring unique encryption

---

## 📦 Key Features Breakdown

### Background Operations
- Uses `AxiomBackgroundService` to maintain foreground notification
- Prevents OS from killing the app during long operations
- Graceful resume on app foregrounding

### Progress Indicators
- **Dual-Phase Tracking**: Separate progress for download/upload and encrypt/decrypt
- **Smart Estimation**: 0-60% dummy progress for fast operations, real progress for I/O
- **Cancellation Support**: Clean cancellation with resource cleanup

### File Viewer
- **Universal Support**: Images, videos, audio, PDFs, text files
- **Secure Playback**: Decrypted content served from secure temporary storage
- **Auto-Cleanup**: Temporary files securely wiped on viewer close

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Built with ❤️ using [Flutter](https://flutter.dev)
- Encryption powered by [PointyCastle](https://pub.dev/packages/pointycastle)
- State management with [Riverpod](https://riverpod.dev)

---

<div align="center">
  
### 🌟 Star this repo if you find it useful!

**Made with 🔐 by [Himanshu Chaurasiya](https://github.com/himanshuchaurasiya24)**

</div>
