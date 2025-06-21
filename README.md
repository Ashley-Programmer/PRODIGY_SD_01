# 🌡️ PRODIGY_SD_01 - Temperature Converter Project

A comprehensive temperature conversion project featuring both Python and web-based implementations, with manual and automatic conversion modes for web versions.

## 📋 Table of Contents

- [Overview](#overview)
- [Version Comparison](#version-comparison)
- [Features](#features)
- [How to Use](#how-to-use)
- [Conversion Formulas](#conversion-formulas)
- [File Structure](#file-structure)
- [Technical Details](#technical-details)
- [Installation](#installation)
- [Usage Examples](#usage-examples)
- [Browser Compatibility](#browser-compatibility)

## 🔍 Overview

This **PRODIGY_SD_01** project includes multiple implementations of a temperature converter:

1. **Python Version** (`Python_Converter_version/`) - Command-line temperature converter
2. **Web Manual Converter** (`Web_converter_version/index.html` + `converter2.js`) - Click-to-convert web version
3. **Web Auto Converter** (`Web_converter_version/` + `converter.js`) - Real-time web conversion version

All converters provide accurate temperature conversions between Celsius, Fahrenheit, and Kelvin with comprehensive validation and user-friendly interfaces.

## ⚖️ Version Comparison

| Feature | Manual Converter | Auto Converter |
|---------|------------------|----------------|
| **Conversion Trigger** | Button click | Real-time (as you type) |
| **Formula Display** | Basic result only | Shows conversion formula |
| **Input Validation** | Basic number check | Advanced validation with absolute zero checks |
| **Error Handling** | Simple error messages | Detailed error messages with context |
| **User Experience** | Traditional form submission | Modern real-time feedback |
| **Code Architecture** | Simple functions | Object-oriented with nested conversion functions |

## ✨ Features

### Common Features (Both Versions)
- **Multi-scale conversion**: Convert between Celsius (°C), Fahrenheit (°F), and Kelvin (K)
- **Precise calculations**: Results rounded to 2 decimal places
- **Input validation**: Handles invalid inputs with helpful error messages
- **Clean interface**: User-friendly design with clear instructions
- **Responsive design**: Works on desktop and mobile devices
- **Clear functionality**: Reset form with one click

### Auto Converter Exclusive Features
- **Real-time conversion**: Instant results as you type
- **Formula display**: Shows the mathematical formula used for each conversion
- **Advanced validation**: Checks for absolute zero violations
- **Smart error handling**: Context-aware error messages
- **Dynamic updates**: Conversion updates when scales are changed

## 🚀 How to Use

### Manual Converter
1. Enter a temperature value in the input field
2. Select the source temperature scale from the first dropdown
3. Select the target temperature scale from the second dropdown
4. Click the "Convert" button to see the result
5. Use "Clear All" to reset the form

### Auto Converter
1. Enter a temperature value in the input field
2. Select the source temperature scale from the "From" dropdown
3. Select the target temperature scale from the "To" dropdown
4. Results appear automatically as you type or change selections
5. View the conversion formula below the result
6. Use "Clear All" to reset the form

## 🧮 Conversion Formulas

Both applications use standard temperature conversion formulas:

- **Celsius to Fahrenheit**: `°F = (°C × 9/5) + 32`
- **Celsius to Kelvin**: `K = °C + 273.15`
- **Fahrenheit to Celsius**: `°C = (°F - 32) × 5/9`
- **Fahrenheit to Kelvin**: `K = (°F - 32) × 5/9 + 273.15`
- **Kelvin to Celsius**: `°C = K - 273.15`
- **Kelvin to Fahrenheit**: `°F = (K - 273.15) × 9/5 + 32`

## 📁 File Structure

```
PRODIGY_SD_01/
├── Python_Converter_version/
│   └── temperature_converter_gui.py
├── Web_converter_version/
│   ├── index2.html         # Manual conversion HTML
│   ├── converter2.js       # Manual conversion JavaScript
│   ├── style2.css          # Manual converter styling
│   ├── index.html          # Auto conversion HTML (alternative version)
│   ├── converter.js        # Auto conversion JavaScript (from paste.txt)
│   └── style.css           # Auto converter styling
└── README.md               # This documentation
```

## 🔧 Technical Details

### Manual Converter Architecture
**HTML Structure**:
- Simple form with dropdown selectors
- Button-triggered conversion
- Basic result display

**JavaScript Functions**:
- `convertTemp()`: Main conversion logic with switch statements
- `clearForm()`: Resets form and hides results
- `hideResult()`: Hides the result display
- Event listener for form submission

### Auto Converter Architecture
**HTML Structure**:
- Enhanced form with better accessibility
- Visual arrow indicator between conversion scales
- Separate divs for results, errors, and formulas

**JavaScript Functions**:
- **Nested Conversion Object**: `conversions` object with organized conversion functions
- `validateInput()`: Advanced input validation with absolute zero checks
- `convertTemperature()`: Clean conversion logic using the nested object
- `showResult()` / `showError()`: Enhanced display functions
- **Real-time Event Listeners**: Input, change, and form submission handlers

### Key Technical Differences

#### Manual Converter
```javascript
// Simple switch-based conversion
switch(from_unit) {
    case 'celsius':
        celsius = input_temp;
        break;
    // ...
}
```

#### Auto Converter
```javascript
// Object-oriented conversion system
const conversions = {
    celsius: {
        fahrenheit: (c) => (c * 9 / 5) + 32,
        kelvin: (c) => c + 273.15
    },
    // ...
};
```

## 🛠️ Installation

### Python Version
1. Navigate to `Python_Converter_version/` directory
2. Run the Python script with: `python temperature_converter.py`
3. Follow the command-line prompts

### Web Versions
1. **Download Files**: Navigate to the `Web_converter_version/` directory
2. **File Organization**: Ensure CSS files are in the same directory as HTML files
3. **Choose Version**: 
   - For manual conversion: Open `index.html`
   - For auto conversion: Create or open the HTML file that uses `converter.js`
4. **Start Converting**: Open your chosen HTML file in any modern web browser

## 📊 Usage Examples

### Manual Converter
- Enter `100`, select `Celsius` → `Fahrenheit`, click Convert → `212.00°F`
- Enter `32`, select `Fahrenheit` → `Celsius`, click Convert → `0.00°C`

### Auto Converter
- Type `273.15`, select `Kelvin` → `Celsius` → Instantly shows `0.00°C`
- Formula displays: `°C = K - 273.15`
- Invalid input like `-300°C` shows: `Temperature cannot be below absolute zero (-273.15°C)`

## 🌐 Browser Compatibility

**Requirements**:
- Modern browsers supporting ES6 JavaScript features
- HTML5 form elements
- CSS3 styling
- Event listener support

**Tested On**:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 🎯 Which Version to Choose?

**Choose Manual Converter If**:
- You prefer traditional form-based interfaces
- You want simpler, lightweight code
- You need basic conversion functionality
- You're learning web development fundamentals

**Choose Auto Converter If**:
- You want modern, real-time user experience
- You need advanced input validation
- You want to see conversion formulas
- You prefer object-oriented JavaScript architecture

## 🏢 Built For

ProDigy InfoTech

---

*Two approaches, one goal: Simple, accurate, and user-friendly temperature conversions for everyone.*
