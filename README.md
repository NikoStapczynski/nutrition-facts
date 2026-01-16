# nf - Nutrition Facts CLI

A command-line tool to get macronutrient information for any food using the USDA FoodData Central API.

## Installation

### Prerequisites

- Node.js (v12 or higher)
- A free USDA FoodData Central API key

### Github Install

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
# Single food defaults to 1 serving
nf apple
# 1 apple APPLE: 52 calories, 0g protein, 14g carbs, 1g fat

# Multiple foods should be comma seperated
nf chicken breast, rice, broccoli
# Chicken Breast: 165 calories, 31g protein, 0g carbs, 3.6g fat
# Rice: 130 calories, 2.7g protein, 28g carbs, 0.3g fat
# Broccoli: 55 calories, 3.7g protein, 11g carbs, 0.6g fat
# ---
# Total: 350 calories, 37.4g protein, 39g carbs, 4.5g fat

# Foods with quantities and units
nf 1 lb ground beef, 1 gal milk, 500 eggs
# 1 lb Beef, ground, 80% lean meat / 20% fat, patty, cooked, broiled: 1120 calories, 130g protein, 0g carbs, 67g fat
# 1 gal Milk, whole, 3.25% milkfat, with added vitamin D: 1460 calories, 72g protein, 104g carbs, 80g fat
# 500 eggs Eggs, Grade A, Large, egg whole: 3575 calories, 325g protein, 25g carbs, 350g fat
# ---
# Total: 6155 calories, 527g protein, 129g carbs, 497g fat

# Mixed formats
nf apple, 200g chicken breast, 1 cup rice
# Apples, raw, with skin: 52 calories, 0g protein, 14g carbs, 0g fat
# 200g Chicken, broilers or fryers, breast, meat only, cooked, roasted: 331 calories, 62g protein, 0g carbs, 7g fat
# 1 cup Rice, white, long grain, regular, cooked: 205 calories, 4.3g protein, 44g carbs, 0.4g fat
# ---
# Total: 588 calories, 66.3g protein, 58g carbs, 7.4g fat

# View help
nf --help
```

### Supported Units

- **Weight**: g, lb, oz, kg
- **Volume**: cup, tbsp, tsp, ml, l, gal, qt, pt, fl_oz
- **Special**: egg, eggs (50g each)

### Example Output

```
$ nf apple banana
Apples, raw, with skin (Includes foods for USDA's Food Distribution Program): 52 calories, 0g protein, 14g carbs, 0g fat
Bananas, raw: 89 calories, 1g protein, 23g carbs, 0g fat
---
Total: 141 calories, 1g protein, 37g carbs, 0g fat

$ nf 1 lb ground beef, 500 eggs
1 lb Beef, ground, 80% lean meat / 20% fat, patty, cooked, broiled: 1120 calories, 130g protein, 0g carbs, 67g fat
500 eggs Eggs, Grade A, Large, egg whole: 3575 calories, 325g protein, 25g carbs, 350g fat
---
Total: 4695 calories, 455g protein, 25g carbs, 417g fat
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
