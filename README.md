To complete this project, we need to create a function `pascal_triangle` that generates Pascal's Triangle up to `n` rows and returns it as a list of lists. Here's a step-by-step guide on how to implement this in Python:

### Step-by-Step Implementation

1. **Function Definition**: Define the function `pascal_triangle(n)` that takes an integer `n` as input.
2. **Handle Edge Cases**: If `n` is less than or equal to 0, return an empty list.
3. **Initialize the Triangle**: Start with the top of the triangle, which is always `[1]`.
4. **Generate Rows**:
    - Use a loop to generate each row.
    - Each element in the new row (except the first and last elements, which are always 1) is the sum of the two elements directly above it in the previous row.
5. **Return the Triangle**: After generating all rows, return the list of lists.

### Code Implementation

Here is the Python code for the `pascal_triangle` function:

```python
def pascal_triangle(n):
    if n <= 0:
        return []
    
    triangle = [[1]]  # Start with the first row

    for i in range(1, n):
        row = [1]  # The first element is always 1
        for j in range(1, i):
            # Each element is the sum of the two elements above it
            row.append(triangle[i-1][j-1] + triangle[i-1][j])
        row.append(1)  # The last element is always 1
        triangle.append(row)
    
    return triangle
```

### Testing the Function

We will use the provided `0-main.py` script to test our function:

```python
#!/usr/bin/python3
"""
0-main
"""
pascal_triangle = __import__('0-pascal_triangle').pascal_triangle

def print_triangle(triangle):
    """
    Print the triangle
    """
    for row in triangle:
        print("[{}]".format(",".join([str(x) for x in row])))


if __name__ == "__main__":
    print_triangle(pascal_triangle(5))
```

Running the above script should give the following output:

```plaintext
[1]
[1,1]
[1,2,1]
[1,3,3,1]
[1,4,6,4,1]
```

### Creating a README.md

Create a `README.md` file in the repository with the following content:

```markdown
# Pascal's Triangle

This project implements a function to generate Pascal's Triangle in Python.

## Description

The `pascal_triangle` function takes an integer `n` and returns a list of lists representing Pascal's Triangle with `n` rows.

## Usage

To use the function, import it and call it with the desired number of rows:

```python
from 0_pascal_triangle import pascal_triangle

print(pascal_triangle(5))
```

## Example

```python
[
    [1],
    [1, 1],
    [1, 2, 1],
    [1, 3, 3, 1],
    [1, 4, 6, 4, 1]
]
```

## Requirements

- Python 3.6+

## Author

[Your Name]

## License

This project is licensed under the MIT License.
```

### Final Directory Structure

Your project directory should look like this:

```
0x00-pascal_triangle/
├── 0-main.py
├── 0-pascal_triangle.py
└── README.md
```

### Repository

Commit your code and push it to your GitHub repository under the specified path:

```
GitHub repository: alx-interview
Directory: 0x00-pascal_triangle
File: 0-pascal_triangle.py
```

This completes the Pascal's Triangle project implementation in Python.
