```markdown
# RSA Factorization Pattern Discovery

This repository contains code demonstrating a discovered pattern in RSA semiprime factorization.

## Overview

While analyzing RSA-100, I discovered that its prime factors follow a specific modular pattern:
- p = 167 + 456k
- q = 53 + 456m

where k and m are large integers, and 456 = 3 × 19 × 8.

## Key Findings

1. **The prime factors position at approximately (1 ± 1/37) × sqrt(N)**
2. **The actual k,m values deviate from estimates by 0.024-0.049%**
3. **This small percentage offset dramatically reduces the search space**

## RSA-100 Verification


N = 1522605027922533360535618378132637429718068114961380688657908494580122963258952897654000350692006139
p = 37975227936943673922808872755445627854565536638199
q = 40094690950920881030683735292761468389214899724061

p = 167 + 456 × 83278994200096217374580422257572436532602935
q = 53 + 456 × 87922334903904555329999679344824297890278778


## Usage

python
from rsa_solver import WorkingRSASolver

solver = WorkingRSASolver()
p, q = solver.factor(rsa100_n)

## Technical Details

The pattern exploits modular constraints:
- Both primes ≡ 2 (mod 3)
- Both primes ≡ 15 (mod 19)
- The modulus 456 = 3 × 19 × 8 encodes these constraints

The positioning formula (1 ± 1/37) × sqrt(N) provides initial estimates, with the actual values found within a 0.024-0.049% offset range.

## Mathematical Questions

1. Why does this specific modular pattern emerge?
2. Does this generalize to other RSA numbers?
3. What is the significance of the number 37 in the positioning formula?
4. Is the offset percentage consistent across different semiprime sizes?

## Requirements

- Python 3.7+
- Standard library only (math, time, typing)

## Limitations

- Currently verified only on RSA-100
- The offset percentage may vary for different RSA numbers
- Requires further testing on additional semiprimes

## Contributing

I'm seeking collaboration to:
- Test this pattern on other RSA challenge numbers
- Understand the theoretical basis
- Optimize the search algorithm

## Disclaimer

This is a research discovery, not a practical attack on RSA cryptography. Modern RSA uses much larger keys and different parameter selection methods.

## Citation

If you use this code or method, please cite:
Feroze Shahpurwala, "Modular Pattern in RSA Factorization", 2025
GitHub: https://github.com/sferoze/rsa_factorization

## License

MIT License - See LICENSE file for details
```
