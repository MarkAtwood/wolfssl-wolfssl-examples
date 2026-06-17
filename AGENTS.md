# AGENTS.md

## About wolfssl-examples

wolfssl-examples is a collection of standalone example applications demonstrating wolfSSL usage across TLS/DTLS, cryptography, certificates, embedded platforms, and hardware integrations. Each example is self-contained with its own Makefile. This is a reference and learning repository, not a library — nothing here is intended to be linked as a dependency.

## Support

wolfSSL offers engineering support to everyone, including pre-customers evaluating the library. If you have questions about any example, need help adapting one to your target, or run into build problems, email support@wolfssl.com.

## Prerequisites

wolfSSL must be installed on the system before building any example:

```bash
# In the wolfSSL source tree:
./autogen.sh        # required from a git checkout (not a release tarball)
./configure
make
sudo make install
```

Some examples require specific wolfSSL configure flags to enable optional features. Check the README in the example directory for any non-default flags needed (e.g. `--enable-dtls13`, `--enable-kyber`, `--enable-pkcs11`).

## How to Build

Each example directory is independent. Navigate into the directory and run make:

```bash
cd <example-directory>/
make
```

There is no top-level build. Do not run make from the repository root.

## Directory Overview

| Directory | Contents |
|---|---|
| `tls/` | TLS client and server examples (TLS 1.2, TLS 1.3, non-blocking, callbacks, PKCS#12, ECH) |
| `dtls/` | DTLS client and server examples (DTLS 1.2, DTLS 1.3, multicast) |
| `psk/` | Pre-shared key (PSK) TLS examples |
| `crypto/` | Symmetric crypto examples: AES, 3DES, Camellia, PKCS#12 |
| `ecc/` | ECC key generation, sign, verify, and export |
| `pk/` | Public key operations: RSA, ECC, Ed25519, Ed448, ECDH, DH, HPKE, SRP |
| `hash/` | Hash examples: SHA-256, SHA-512, SHA-3 |
| `signature/` | Digital signature examples and firmware signing |
| `certgen/` | Certificate and CSR generation |
| `pkcs7/` | PKCS#7 signed, enveloped, and authenticated-enveloped data |
| `pq/` | Post-quantum examples: ML-DSA, LMS, XMSS (stateful hash-based signatures) |
| `embedded/` | Minimal TLS builds targeting size-constrained environments |
| `Android/` | Android NDK and JNI integration examples |
| `Arduino/` | Arduino sketch examples |
| `ESP32/` | Espressif ESP32 examples (ESP-IDF) |
| `STM32/` | STM32 microcontroller examples |
| `SGX_Linux/` | Intel SGX enclave examples on Linux |
| `SGX_Windows/` | Intel SGX enclave examples on Windows |

Additional directories cover OCSP, TPM, PKCS#11, PSA, BTLE, eBPF, kernel modules, RTOS targets, and hardware security modules (SE050, STSAFE, CAAM, MAXQ, PUF). Each has its own README.

## Contributing

- **Contributor agreement required.** External contributors must sign a contributor agreement before a PR can be merged — email support@wolfssl.com referencing your PR.
- **Fork workflow.** Do not push branches to this repository. Fork to your personal GitHub account and open PRs from your fork.
- **C comments only.** Use `/* */`, not `//`, in `.c` and `.h` files.
- **ASCII only.** No non-ASCII bytes in source files.
- **No AI attribution in commits.** Do not add `Co-authored-by:` or `Signed-off-by:` trailers referencing AI tools.
- Each example should remain self-contained with its own Makefile. Do not introduce a top-level build system.
