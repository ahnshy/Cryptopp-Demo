# 📦 Crypto++ Demo
 This repository demonstrates how to use the **Crypto++** (Crypto++) v8.9(Oct 2, 2023 Released) library in simple C++ projects. It includes hashing, AES encryption/decryption.<br/>
 ✅ Tested on Windows 10 / Visual Studio 2019 / CMake 3.31.8 
<br/>

# 🧩 About Crypto++
This repository demonstrates how to use the **Crypto++** (https://cryptopp.com/) library in simple C++ projects. 
It includes hashing, encryption/decryption, digital signatures, and more.
<br/><br/>

## ⚙️ Build Environment
- `Windows 10+` <br/>
- `Git for Windows` <br/>
- `C++ ISO 17` compatible compiler (GCC, Clang, MSVC) <br/>
- [Visual Studio 2019](https://visualstudio.microsoft.com/) <br/>
- [CMake ≥ 3.10](https://cmake.org/download/) <br/>
- [Crypto++ library ≥ 8.0](https://github.com/weidai11/cryptopp) installed or available <br/>
<br/><br/>

## 🚀 Build Instructions
```bash
git clone https://github.com/ahnshy/Cryptopp-Demo.git
cd Cryptopp-Demo
```
<br/><br/>

## 📁 Repository Tree
```
/ `Root` <br/>
├── CMakeLists.txt         # Build configuration
├── include/               # Header files (if any)
├── src/                   # Source files with examples
│   ├── HashExample.cpp
│   ├── SymmetricCipher.cpp
│   ├── AsymmetricExample.cpp
│   └── DigitalSignature.cpp
└── README.md              # You are here
```
<br/><br/>

## 🔍 Notes
- When using RSA/ECDSA examples, ensure secure key sizes (e.g. RSA‑2048 or ECDSA P‑256).
- Make sure to use `AutoSeededRandomPool` for cryptographically secure randomness.
- Don't handle sensitive data (keys, IVs) in hard-coded strings in production.
<br/><br/>

## 📤 Output
Compiled libraries (.lib, .dll, .exe) will be located in:<br/
```path
 Win32/cryptest
 Win32/cryptlib
 Win32/Output
```
<br/><br/>

### 🔍 Usage Example code for `SymmetricCipher`
```test.cpp

int CRYPTOPP_API main(int argc, char *argv[]) {
	UNREFERENCED_PARAMETER(argc);
	UNREFERENCED_PARAMETER(argv);

	CryptoPP::byte key[CryptoPP::AES::DEFAULT_KEYLENGTH], initVector[CryptoPP::AES::BLOCKSIZE];
	memset(key, 0x00, CryptoPP::AES::DEFAULT_KEYLENGTH);
	memset(initVector, 0x00, CryptoPP::AES::BLOCKSIZE);

	std::string plainText = "PlainText Test 가나다라 with Korean.";

	auto ciphertext = AESEncrypt(plainText, key, initVector);
	auto decryptedtext = AESDecrypt(plainText, key, initVector);
}
```
<br/><br/>

## 🧪 Running Examples
| File                     | Description                                      |
|--------------------------|--------------------------------------------------|
| `HashExample.cpp`        | SHA‑256, SHA‑1, MD5 hashing demonstrations       |
| `SymmetricCipher.cpp`    | AES‑CBC and AES‑GCM encryption/decryption flows |
| `AsymmetricExample.cpp`   | RSA key generation, encryption, decryption        |
| `DigitalSignature.cpp`    | Signing and verifying data with RSA/ECDSA         |

```bash
./HashExample
./SymmetricCipher
./AsymmetricExample
./DigitalSignature
```
<br/><br/>

## 📝 License
 This demo project is distributed under the **MIT License**. Crypto++ itself is licensed under **Crypto++ License (similar to BSD)** — see LICENSE files for details.
<br/><br/>
