# Algorithms Analysis: A Comprehensive Study of Classic Algorithms

![GitHub stars](https://img.shields.io/github/stars/yourusername/algorithms_analysis?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/yourusername/algorithms_analysis?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/yourusername/algorithms_analysis?style=flat-square)
![GitHub license](https://img.shields.io/github/license/yourusername/algorithms_analysis?style=flat-square)

---

## Overview

Dive deep into the world of classic algorithms with this comprehensive repository. This project provides detailed implementations, theoretical explanations, and complexity analyses of fundamental algorithms in Jupyter Notebook format.

Perfect for:
- Students learning computer science fundamentals
- Developers preparing for technical interviews
- Educators looking for teaching resources
- Algorithm enthusiasts wanting to explore classic solutions

Each notebook follows a consistent structure:
- **Theory** — Mathematical foundations and problem context
- **Pseudocode** — Clear algorithmic representation
- **Python Implementation** — Working code examples
- **Output** — Visual demonstration of results
- **Complexity Analysis** — Time and space complexity breakdown

---

## Features

- **Comprehensive Coverage** — 12 classic algorithms implemented and analyzed
- **Educational Structure** — Each algorithm follows a consistent, well-documented format
- **Practical Examples** — Working code with test cases and visual outputs
- **Theoretical Depth** — Detailed explanations of mathematical foundations
- **Interactive Learning** — Jupyter Notebook format for hands-on exploration
- **Performance Analysis** — Complete complexity breakdowns for each algorithm
- **Ready-to-Use** — All code is production-ready and tested

---

## Tech Stack

| Category         | Technologies Used                          |
|------------------|--------------------------------------------|
| **Language**     | Python (Jupyter Notebook)                  |
| **Notebook**     | JupyterLab 4.5.6                           |
| **Dependencies** | See [requirements.txt](requirements.txt)   |

**System Requirements:**
- Python 3.8+
- Jupyter Notebook environment
- Basic understanding of Python programming

---

## Installation

### Prerequisites

Ensure you have the following installed:
- [Python 3.8+](https://www.python.org/downloads/)
- [Jupyter Notebook](https://jupyter.org/install)

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/algorithms_analysis.git
   cd algorithms_analysis
   ```

2. **Set up a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

5. Open and explore the notebooks in your browser.

### Alternative Installation (Docker)

For users who prefer containerized environments:

```bash
docker build -t algorithms-analysis .
docker run -it --rm -p 8888:8888 algorithms-analysis
```

Access Jupyter Notebook at `http://localhost:8888` with the token provided in the output.

---

## Usage

### Basic Usage

Each notebook follows this structure:

1. **Theory Section** — Understand the mathematical foundation
2. **Pseudocode** — See the algorithmic representation
3. **Python Implementation** — Copy and run the code
4. **Output** — View the results of test cases
5. **Complexity Analysis** — Learn about time and space complexity

### Advanced Usage

For developers looking to extend or modify the algorithms:

- **Custom Test Cases** — Modify the test cases in each notebook to test your own inputs
- **Algorithm Optimization** — Experiment with different implementations
- **Visualization** — Add your own visualizations to better understand the algorithms
- **Benchmarking** — Compare performance between different implementations

**Example: Adding Custom Test Cases**

```python
def gcd_iterative(a, b):
    # ... existing implementation ...
    return b

if __name__ == "__main__":
    test_cases = [(48, 18), (100, 75), (56, 98), (0, 5), (17, 13)]
    custom_cases = [(123456789, 987654321), (1000000, 999999)]

    all_cases = test_cases + custom_cases
    print(f"{'a':>10} {'b':>10} {'GCD':>10}")
    print("-" * 30)
    for a, b in all_cases:
        print(f"{a:>10} {b:>10} {gcd_iterative(a, b):>10}")
```

---

## Project Structure

```
algorithms_analysis/
│
├── .gitignore                  # Specifies intentionally untracked files
├── requirements.txt            # Project dependencies
│
├── 01_gcd.ipynb                # Greatest Common Divisor (Euclidean Algorithm)
├── 02_fibonacci.ipynb          # Fibonacci Sequence
├── 03_linear_search.ipynb      # Linear Search
├── 04_bubble_sort.ipynb        # Bubble Sort
├── 05_insertion_sort.ipynb     # Insertion Sort
├── 06_quick_sort.ipynb         # Quick Sort
├── 07_merge_sort.ipynb         # Merge Sort
├── 08_kruskal_algorithm.ipynb  # Kruskal's Algorithm for MST
├── 09_dijkstra_algorithm.ipynb # Dijkstra's Algorithm
├── 10_binary_knapsack.ipynb    # 0/1 Knapsack Problem
├── 11_n_queens.ipynb           # N Queens Problem
├── 12_subset_sum.ipynb         # Subset Sum Problem
│
└── latex/                      # LaTeX documentation (optional)
```

---

## Configuration

### Environment Variables

Create a `.env` file in your project root for custom configurations:

```env
DEFAULT_TEST_CASES=true
CUSTOM_TEST_CASES=false
```

### Customization Options

Each algorithm notebook includes parameters you can easily modify:

```python
# Example from 02_fibonacci.ipynb
def fibonacci_iterative(n):
    # ... implementation ...
    return b

if __name__ == "__main__":
    print_range = 10  # Change this to test up to F(20), etc.
    print(f"n   :   " + " ".join(f"{i:>3}" for i in range(print_range)))
    print(f"F(n):   " + " ".join(f"{fibonacci_iterative(i):>3}" for i in range(print_range)))
```

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## Additional Resources

- [Wikipedia: List of Algorithms](https://en.wikipedia.org/wiki/List_of_algorithms)
- [GeeksforGeeks Algorithms Tutorial](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [MIT OpenCourseWare: Introduction to Algorithms](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/)
