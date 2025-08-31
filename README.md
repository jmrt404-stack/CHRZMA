# CHRZMA
Just to further advance.

## Furthermore
This is my systematic experience.

### Space Game
Attack defenses

# Run Python Script

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: windows-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x' # Specify your desired Python version (e.g., '3.9', '3.12')

      - name: Install dependencies (optional)
        run: pip install -r requirements.txt # If your script has dependencies

      - name: Run Python script
        run: python your_script.py # Replace 'your_script.py' with your script's name

from PIL import Image, ImageDraw

def create_crosshair_image(size=500, line_width=5, color="red"):
    """Creates a simple image with a crosshair."""
    img = Image.new('RGB', (size, size), color='black')
    draw = ImageDraw.Draw(img)
    center = size // 2

    # Draw horizontal line
    draw.line((0, center, size, center), fill=color, width=line_width)
    # Draw vertical line
    draw.line((center, 0, center, size), fill=color, width=line_width)

    img.save('crosshair.png')
    print("Crosshair image 'crosshair.png' created successfully.")

if __name__ == "__main__":
    create_crosshair_image()
