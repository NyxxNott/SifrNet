# MPC SPDZ with Ring Signatures and Dilithium Signatures
## Overview
This project implements a secure Multi-Party Computation (MPC) system using the SPDZ protocol, enhanced with Monero-style ring signatures for anonymity and Dilithium-based post-quantum cryptography for authentication. The system enables multiple parties to jointly compute functions over their private inputs while maintaining privacy, integrity, and post-quantum security.

## Key Features
🔒 Security Features
- Post-Quantum Security: Dilithium-based digital signatures resistant to quantum attacks
- Anonymity: Monero-style ring signatures for participant anonymity
- Linkability: Ring signatures prevent double-spending and replay attacks
- Integrity Protection: MAC-based authentication of secret shares
- Privacy-Preserving: Inputs remain private through secret sharing

🛠️ Technical Components
- SPDZ Protocol: Secure multi-party computation with authenticated shares
- Additive Secret Sharing: Values split into random shares across parties
- Beaver Triples: Pre-computed multiplication triples for efficient secure multiplication
- MAC Verification: Cryptographic integrity checks on all computations

## Protocol Architecture

┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Party Node 1  │    │   Party Node 2  │    │   Party Node 3  │
│                 │    │                 │    │                 │
│ - SPDZ Party    │    │ - SPDZ Party    │    │ - SPDZ Party    │
│ - Ring Sig      │    │ - Ring Sig      │    │ - Ring Sig      │
│ - Dilithium     │    │ - Dilithium     │    │ - Dilithium     │
│ - Secret Shares │    │ - Secret Shares │    │ - Secret Shares │
└─────────────────┘    └─────────────────┘    └─────────────────┘
          │                       │                       │
          └───────────────────────────────────────────────┘
                                  │
                        ┌─────────────────┐
                        │  Coordinator    │
                        │                 │
                        │ - SPDZCoordinator│
                        │ - Authentication│
                        │ - Reconstruction│
                        └─────────────────┘
