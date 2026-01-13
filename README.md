# nf - Nutrition Facts CLI

A fast command-line tool to get macronutrient information for any food using the USDA FoodData Central API.

## Features

- 🚀 Fast and lightweight - no dependencies
- 🍎 Access to 400,000+ foods from USDA database
- 📊 Get protein, carbs, and fat information instantly
- 🎨 Color-coded terminal output
- 🔒 Secure API key storage in `~/.config/nf/`

## Installation

### Prerequisites

- Node.js (v12 or higher)
- A free USDA FoodData Central API key

### Quick Install

```bash
# Clone the repository
git clone https://github.com/NikoStapczynski/nutrition-facts.git
cd nutrition-facts

# Make the script executable
chmod +x nf

# Move to your PATH (choose one)
sudo mv nf /usr/local/bin/nf
# OR for user-only install:
mkdir -p ~/.local/bin
mv nf ~/.local/bin/nf
```

### Get Your Free API Key

1. Visit [USDA FoodData Central API signup](https://fdc.nal.usda.gov/api-key-signup.html)
2. Fill out the form (name, email, organization)
3. Copy your API key
4. Configure nf: `nf --setup YOUR_API_KEY_HERE`

## Usage

```bash
# Single food
nf apple

# Multiple foods (shows totals)
nf chicken breast rice broccoli

# Foods with spaces (use quotes)
nf "sweet potato" "peanut butter"

# View help
nf --help
```

### Example Output

```
$ nf apple banana
Apples, raw, with skin (Includes foods for USDA's Food Distribution Program): 0g protein, 14g carbs, 0g fat
Bananas, raw: 1g protein, 23g carbs, 0g fat
---
Total: 1g protein, 37g carbs, 0g fat
```

## Configuration

Your API key is stored in `~/.config/nf/config.json`

To reconfigure:
```bash
nf --setup NEW_API_KEY
```

## License

GPL-3.0 License - see [LICENSE](LICENSE) file for details

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Author

Niko Stapczynski

## Acknowledgments

- Nutrition data provided by [USDA FoodData Central](https://fdc.nal.usda.gov/)