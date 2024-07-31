## ZK SNARK DESIGNER
In this project I have created a zKSnark circuit using the circom programming language that implements the following logical operations:
The circuit consists of an AND gate, NOT gate, OR gate.

![image](https://github.com/user-attachments/assets/b2b088b3-e884-433b-a252-f9a0e300a246)


The goal of the project is to prove that the inputs A=0 and B=1 yield a 0 output.


# Installation
1. clone the hardhat-circom repository :
 ```sh
git clone https://github.com/gmchad/zardkat
 ```

2. Change current working directory :
 ```sh
cd ./zardkat
 ```

3. Install the required dependencies :
 ```sh
npm i
 ```
   
4. Installing snarkjs :
 ```sh
npm install -g snarkjs
 ```

6. Write the correct logic and compile circom
 ```sh
npx hardhat circom
 ```
 this script generates proofs and a verifier.

 

# Implementation
1. Write the correct circuit.circom implementation.
2. Compile the circuit to generate circuit intermediaries
```sh
npx hardhat run scripts/deploy.ts
``` 
3. It will generate the CustonCircuitVerifier.sol contract.
4. If `True` deploy on sepolia ehterscan test network
```sh
npx hardhat run scripts/deploy.ts --network Sepolia
```

# Deployment
`npx hardhat run scripts/deploy.ts --network mumbai`
This script does 4 things:
1. It deploys the CustonCircuitVerifier.sol contract.
2. Generates a proof from circuit intermediaries with `generateProof()`.
3. Generates calldata with `generateCallData()`.
4. Calls `verifyProof()` on the verifier contract with calldata.
5. Lastly, the asserted output should turn out to be  `TRUE`.

![image](https://github.com/user-attachments/assets/a904dfde-3b78-4e79-a006-f395fd470756)

