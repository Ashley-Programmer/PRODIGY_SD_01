# 🌡️ PRODIGY_SD_01 - Temperature Converter Project

A comprehensive temperature conversion project featuring Python GUI and web-based implementations, with manual and automatic conversion modes across different platforms.

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
- [System Requirements](#system-requirements)

## 🔍 Overview

This **PRODIGY_SD_01** project includes multiple implementations of a temperature converter:

1. **Python GUI Version** (`Python_Converter_version/`) - Desktop application with Tkinter GUI
2. **Web Manual Converter** (`Web_converter_version/index.html` + `converter2.js`) - Click-to-convert web version
3. **Web Auto Converter** (`Web_converter_version/` + `converter.js`) - Real-time web conversion version

All converters provide accurate temperature conversions between Celsius, Fahrenheit, and Kelvin with comprehensive validation and user-friendly interfaces.

## ⚖️ Version Comparison

| Feature | Python GUI | Web Manual | Web Auto |
|---------|------------|------------|----------|
| **Platform** | Desktop (Cross-platform) | Web Browser | Web Browser |
| **Interface** | Tkinter GUI with radio buttons | HTML form with dropdowns | HTML form with dropdowns |
| **Conversion Trigger** | Button click + Real-time | Button click | Real-time (as you type) |
| **Formula Display** | ✅ Shows formula below result | ❌ Basic result only | ✅ Shows conversion formula |
| **Input Validation** | ✅ Advanced with absolute zero checks | ⚠️ Basic number check | ✅ Advanced validation with absolute zero checks |
| **Error Handling** | ✅ Detailed error messages | ⚠️ Simple error messages | ✅ Detailed error messages with context |
| **User Experience** | Native desktop app feel | Traditional form submission | Modern real-time feedback |
| **Keyboard Shortcuts** | ✅ Enter, Ctrl+N | ❌ None | ❌ None |
| **Additional Features** | Menu bar, About dialog, Exit confirmation | Basic functionality | Object-oriented architecture |

## ✨ Features

### Common Features (All Versions)
- **Multi-scale conversion**: Convert between Celsius (°C), Fahrenheit (°F), and Kelvin (K)
- **Precise calculations**: Results rounded to 2 decimal places
- **Input validation**: Handles invalid inputs with helpful error messages
- **Clean interface**: User-friendly design with clear instructions
- **Clear functionality**: Reset form/inputs with one click

### Python GUI Exclusive Features
- **Desktop Application**: Native cross-platform desktop app
- **Real-time + Manual Conversion**: Updates as you type AND button-triggered conversion
- **Advanced UI**: Radio buttons, styled labels, resizable window
- **Keyboard Shortcuts**: Enter to convert, Ctrl+N to clear
- **Menu System**: Help menu with About dialog and Exit option
- **Window Management**: Centered window, exit confirmation dialog
- **Temperature Facts**: Built-in educational content about temperature scales

### Web Auto Converter Exclusive Features
- **Real-time conversion**: Instant results as you type
- **Formula display**: Shows the mathematical formula used for each conversion
- **Advanced validation**: Checks for absolute zero violations
- **Smart error handling**: Context-aware error messages
- **Dynamic updates**: Conversion updates when scales are changed

### Web Manual Converter Features
- **Simple Interface**: Traditional form-based approach
- **Lightweight**: Minimal JavaScript code
- **Basic Validation**: Simple number validation
- **Cross-browser**: Works on all modern browsers

## 🚀 How to Use

### Python GUI Version
1. Run the application (python file)
2. Enter a temperature value in the input field
3. Select source temperature scale using radio buttons (left side)
4. Select target temperature scale using radio buttons (right side)
5. Click "Convert Temperature" or press Enter
6. View result, formula, and any error messages
7. Use "Clear All" or Ctrl+N to reset

### Web Manual Converter
1. Enter a temperature value in the input field
2. Select the source temperature scale from the first dropdown
3. Select the target temperature scale from the second dropdown
4. Click the "Convert" button to see the result
5. Use "Clear All" to reset the form

### Web Auto Converter
1. Enter a temperature value in the input field
2. Select the source temperature scale from the "From" dropdown
3. Select the target temperature scale from the "To" dropdown
4. Results appear automatically as you type or change selections
5. View the conversion formula below the result
6. Use "Clear All" to reset the form

## 🧮 Conversion Formulas

All applications use standard temperature conversion formulas:

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
│   └── temperature_converter_gui.py    # Complete Tkinter GUI application
├── Web_converter_version/
│   ├── index2.html                     # Manual conversion HTML
│   ├── converter2.js                   # Manual conversion JavaScript
│   ├── style2.css                      # Manual converter styling
│   ├── index.html                      # Auto conversion HTML 
│   ├── converter.js                    # Auto conversion JavaScript
│   └── style.css                       # Auto converter styling
└── README.md                           # This documentation
```

## 🔧 Technical Details

### Python GUI Architecture
**Framework**: Tkinter with ttk (themed widgets)
**Key Classes**:
- `TemperatureConverter`: Main application class
- **Window Management**: Custom styling, centering, resizing
- **Event Handling**: Real-time updates, keyboard shortcuts, menu system
- **Validation**: Advanced input validation with absolute zero checks

**Key Methods**:
```python
def setup_window(self):     # Window configuration and styling
def create_variables(self):  # Tkinter variables for data binding
def create_widgets(self):   # GUI layout and widget creation
def setup_events(self):     # Event bindings and shortcuts
def perform_conversion(self): # Core conversion logic
def validate_temperature(self): # Input validation
```

### Web Manual Converter Architecture
**HTML Structure**:
- Simple form with dropdown selectors
- Button-triggered conversion
- Basic result display

**JavaScript Functions**:
- `convertTemp()`: Main conversion logic with switch statements
- `clearForm()`: Resets form and hides results
- `hideResult()`: Hides the result display
- Event listener for form submission

### Web Auto Converter Architecture
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

### Code Architecture Comparison

#### Python GUI (Object-Oriented)
```python
class TemperatureConverter:
    def __init__(self, root):
        self.setup_window()
        self.create_variables()
        self.create_widgets()
        self.setup_events()
    
    def get_conversion(self, temp_value, from_scale, to_scale):
        conversions = {
            ("celsius", "fahrenheit"): lambda c: (c * 9/5) + 32,
            # ... other conversions
        }
        return conversions[(from_scale, to_scale)](temp_value)
```

#### Web Manual (Procedural)
```javascript
function convertTemp() {
    switch(from_unit) {
        case 'celsius':
            celsius = input_temp;
            break;
        // ...
    }
}
```

#### Web Auto (Object-Oriented)
```javascript
const conversions = {
    celsius: {
        fahrenheit: (c) => (c * 9 / 5) + 32,
        kelvin: (c) => c + 273.15
    },
    // ...
};
```

## 🛠️ Installation

### Python GUI Version
**Requirements**:
- Python 3.6+ (with Tkinter - usually included)
- No additional packages required

**Installation**:
1. Navigate to `Python_Converter_version/` directory
2. Run: `python temperature_converter_gui.py`
3. The GUI window will open automatically

### Web Versions
**Requirements**:
- Modern web browser
- No server required (runs locally)

**Installation**:
1. Navigate to `Web_converter_version/` directory
2. Choose your preferred version:
   - **Manual**: Open `index.html`
   - **Auto**: Open the HTML file that uses `converter.js`
3. Start converting temperatures!

## 📊 Usage Examples

### Python GUI Version
- **Real-time**: Type `100`, select Celsius → Fahrenheit radio buttons → Automatically shows `212.00°F`
- **Manual**: Type `32`, select Fahrenheit → Celsius, click "Convert Temperature" → `0.00°C`
- **Shortcuts**: Press Enter to convert, Ctrl+N to clear
- **Validation**: Enter `-300` in Celsius → Shows error: "Temperature cannot be below absolute zero (-273.15°C)"

### Web Manual Converter
- Enter `100`, select `Celsius` → `Fahrenheit`, click Convert → `212.00°F`
- Enter `32`, select `Fahrenheit` → `Celsius`, click Convert → `0.00°C`

### Web Auto Converter
- Type `273.15`, select `Kelvin` → `Celsius` → Instantly shows `0.00°C`
- Formula displays: `°C = K - 273.15`
- Invalid input like `-300°C` shows: `Temperature cannot be below absolute zero (-273.15°C)`

## 💻 System Requirements

### Python GUI Version
- **Operating System**: Windows, macOS, Linux
- **Python**: 3.6 or higher
- **GUI Framework**: Tkinter (usually pre-installed with Python)
- **Memory**: ~10MB RAM
- **Storage**: ~1MB disk space

### Web Versions
- **Browser Compatibility**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **JavaScript**: ES6 support required
- **Internet**: Not required (runs offline)
- **Memory**: ~5MB RAM per browser tab

## 🎯 Which Version to Choose?

### Choose Python GUI If:
- You want a **desktop application**
- You need **keyboard shortcuts** and advanced UI features
- You prefer **native application** feel
- You want **real-time + manual conversion** options
- You need **educational features** (temperature facts, formulas)
- You're working **offline** without a browser

### Choose Web Manual If:
- You prefer **traditional form-based** interfaces
- You want **simpler, lightweight** code
- You need **basic conversion** functionality
- You're **learning web development** fundamentals
- You want **cross-platform** without installing software

### Choose Web Auto If:
- You want **modern, real-time** user experience
- You need **advanced input validation**
- You want to **see conversion formulas**
- You prefer **object-oriented JavaScript** architecture
- You want **instant feedback** while typing

## 🏢 Built For

ProDigy InfoTech

---

*Three platforms, one goal: Simple, accurate, and user-friendly temperature conversions for everyone, everywhere.*
