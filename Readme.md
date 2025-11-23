# **SHA-256 Bit Distribution Analysis & Hash Rate Experiment**
---

## **📌 Overview**
The `sha256_experiments.py` program is designed to analyze the statistical properties and performance of the **SHA-256 cryptographic hash function**.  
It generates thousands of unique random inputs, computes their SHA-256 hashes, counts the number of 1-bits in each digest, and produces a histogram showing the distribution.  
This experiment demonstrates the randomness characteristics of SHA-256 and verifies that its bit distribution approximates a **binomial distribution B(256, 0.5)**.

Additionally, the program measures hash computation performance, calculates **hashes per second**, and estimates the theoretical time required to mount cryptographic attacks such as:

- **Birthday attack (weak collision resistance):** requires ~2¹²⁸ operations  
- **Brute-force preimage attack (strong collision resistance):** requires ~2²⁵⁶ operations  

The script also computes exact binomial probabilities for user-specified bit counts (e.g., 128, 100).

---

## **⚙️ Features**
- Generates large sets of unique inputs
- Computes SHA-256 hashes efficiently
- Counts 1-bits using NumPy bit operations
- Produces histogram visualization using Matplotlib
- Saves bit-count frequency data to CSV
- Measures and prints:
  - Total time taken
  - Hash rate (hashes/second)
  - Mean & standard deviation of bit counts
- Estimates cryptographic attack durations
- Computes binomial probabilities for exact bit counts

---

## **📘 Algorithm Flow**
1. User inputs the number of random test cases.
2. Program generates unique random strings by combining counters and random bits.
3. Each string is hashed using SHA-256 (`hashlib.sha256()`).
4. The 256-bit digest is converted to bytes and unpacked using NumPy to count 1-bits.
5. All results are stored and statistically analyzed.
6. Histogram of bit counts is plotted.
7. Hash rate is measured based on total runtime.
8. Time estimates for:
   - **Birthday attack** (requires ~2¹²⁸ hashes)
   - **Brute force** (requires ~2²⁵⁶ hashes)
9. User enters two bit-count values and the program computes the exact binomial probability:
   \[
   P(X = k) = \frac{\binom{256}{k}}{2^{256}}
   \]

---

## **▶️ How to Run**
### **1. Install Python Dependencies**
```bash
pip install numpy matplotlib
2. Run the Program
bash
Copy code
python sha256_experiments.py
3. Follow the Prompts
Example:

vbnet
Copy code
Number of distinct inputs to generate (e.g., 10000): 10000
Enter k1 to compute P(X=k1): 128
Enter k2 to compute P(X=k2): 100
4. Output Includes
Histogram window

CSV file saved as:

Copy code
sha256_ones_counts.csv
Hash rate

Mean and variance

Estimated attack times

Exact binomial probabilities

📂 Output Files
sha256_ones_counts.csv – stores bit-count frequency distribution

Histogram Plot Window – shows the distribution visually

📎 Dependencies
Python 3.x

NumPy

Matplotlib

CSV (built-in)

📜 License
This project is provided for academic and research purposes.
Modification and reuse are permitted.
