# fe-crypto

**Features**
- Groth16 Verifier
- BN254 Pairing Friendly Elliptic Curve
- Precompile Pairing Function

## Groth16 Verifier in fe-lang

Groth16 Verifier in fe-lang allows you to verify circom circuits using [snarkjs][https://github.com/iden3/snarkjs]

Using the groth16.fe, you will be able to leverage zero-knowledge proofs with fe-lang

### How to use the verifier in your fe-lang project?

As we mention above, you will be able to verify circom circuits in your fe-lang project. [This page] [https://docs.circom.io/getting-started/proving-circuits/] provides an information on how to prove circuits with zero-knowledge.

To be able to use groth16 verifier in your project, you need to write your zero-knowledge circuits in circom (other zero-knowledge frameworks will be provided later)

1. Clone snarkjs repo
`git clone https://github.com/iden3/snarkjs.git`

2. Go to local repository

3. Find snarkjs/templates/verifier_groth16.sol.ejs

4. Delete all the lines inside verifier_groth16.sol.ejs

5. Copy all the lines inside groth16.fe and paste it into verifier_groth16.sol.ejs

6. Using the [circom documentation] [https://docs.circom.io/getting-started/proving-circuits/#verifying-a-proof], you should use all the instructions until this part, [Verifying from a Smart Contract] [https://docs.circom.io/getting-started/proving-circuits/#verifying-a-proof]

**Note:** instead of `snarkjs` command use `~/snarkjs/cli.js` as the command

7. In the last step change `verifier.sol` with `verifier.fe` using the following command:

`~/snarkjs/cli.js zkey export solidityverifier multiplier2_0001.zkey verifier.fe`

8. You are able to crate groth16 verifier in fe-lang!

9. To generate the verifier inputs, use `~/snarkjs/cli.js generatecall`

10. Insert the verifier inputs to `verifyProof()` function in `verifier.fe` file

### Disclaimer:

**This implementation has not been reviewed or audited. Use at your own risk.** 
We do not give any warranties and will not be liable for any losses incurred through any use of this code base.