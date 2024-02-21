Calculating bit planes involves isolating the contribution of each bit position to the overall pixel value. Here's a breakdown of the process:

**1. Determine the number of bits per pixel:**

This depends on the image type. For example, a grayscale image with 256 intensity levels (8 bits per pixel) will have 8 bit planes.

**2. Create masks:**

For each bit plane (from least significant to most significant), generate a binary mask with a 1 at the target bit position and 0s elsewhere.

**3. Apply bitwise operations:**

Perform a bitwise AND operation between the image and each mask. This isolates the bits corresponding to the current plane.

**4. Normalize and shift:**

Shift the resulting bit plane to the right by its corresponding bit position (0 for LSB, 7 for MSB in an 8-bit image). This normalizes the plane's values to represent its actual contribution.

**5. Repeat for all bit planes:**

Perform steps 2-4 for each bit position to obtain all individual bit planes.

Here's an example in Python to illustrate the concept:

Python

```python
import numpy as np

def calculate_bit_planes(image):
  """
  Calculates the bit planes of a grayscale image.

  Args:
    image: A 2D numpy array representing the grayscale image.

  Returns:
    A list of 2D numpy arrays, each representing a bit plane.
  """

  # Get the number of bits per pixel
  num_bits = int(np.log2(np.max(image) + 1))

  # Initialize the list of bit planes
  bit_planes = []

  # Iterate through each bit plane
  for i in range(num_bits):
    # Create a mask with 1 at the current bit position
    mask = 2**i

    # Extract the bit plane by performing bitwise AND with the mask
    bit_plane = np.bitwise_and(image, mask)

    # Shift the bit plane to the right by i positions
    bit_plane = bit_plane >> i

    # Add the bit plane to the list
    bit_planes.append(bit_plane)

  return bit_planes
```


This code defines a function that takes an image as input and returns a list of its bit planes. Each plane represents the contribution of a specific bit position to the overall pixel values.