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

## Cryptographic Primitives
### Dilithium Post-Quantum Signatures
- Purpose: Authentication and non-repudiation
- Security: Lattice-based cryptography resistant to quantum attacks
- Usage: Signs ring signatures and protocol messages

### Monero-Style Ring Signatures
- Purpose: Participant anonymity within a ring
- Features: Linkability prevents double-spending
- Key Image: Unique identifier that reveals double-signing attempts

### SPDZ Secret Sharing
- Method: Additive secret sharing over finite field
- Security: Information-theoretic privacy for honest majority
- Authentication: MAC-protected shares prevent tampering

## Cryptographic Steps
### Input Authentication
- Each party creates a ring signature of their input
- Dilithium signature authenticates the ring signature
- Coordinator verifies all authenticated inputs

### Secret Sharing
- Each value is split into random shares using additive secret sharing
- Shares are authenticated with MACs using a global MAC key
- Each party receives one share of each input

### Secure Computation
- Addition: Shares are locally summed
- Multiplication: Uses Beaver triples for secure multiplication
- Reconstruction: Final result computed by combining shares

### Verification
- MACs verified for integrity
- Ring signatures checked for authenticity
- Result validated against expected computation

## Acknowledgments
- Based on original SPDZ protocol by Damgård et al.
- Dilithium implementation inspired by PQClean project
- Ring signatures following Monero cryptographic constructions
