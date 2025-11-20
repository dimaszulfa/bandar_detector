# 📈 Bandar Detector

A web-based tool for analyzing Indonesian stock broker transaction data to detect dominant broker patterns (Bandar). This tool helps identify buying/selling clusters (Haka/Haki patterns) and visualizes broker activity in real-time.

## 🎯 Features

### Core Functionality
- **Clipboard Data Import**: Paste broker transaction data directly from your clipboard
- **Haka/Haki Detection**: Automatically identifies buying and selling clusters
  - **Haka** (🟦): Multiple transactions from the same broker on the buying side within 1 second
  - **Haki** (🟥): Multiple transactions from the same broker on the selling side within 1 second
  - **Cross** (🟪): Broker active on both buying and selling sides simultaneously
- **Interactive Data Selection**: Excel-style row selection with summary statistics

### Visualizations
1. **Line Chart - Net Volume per Broker + Price**
   - Top 5 most active brokers by net volume
   - Price overlay (VWAP) for context
   - Cumulative net position tracking

2. **Time-based Quantity Chart**
   - Total quantity per time interval
   - Volume-weighted average price (VWAP)

3. **Broker Summary Table**
   - Gross Buy/Sell view
   - Net Buy/Sell view
   - Average price per broker
   - Color-coded broker identification

4. **Detailed Transaction Table**
   - Complete transaction history
   - Visual clustering indicators
   - Group value aggregation
   - Row selection for custom analysis

## 📋 Input Format

The tool expects broker summary data in the following format:

```
Time Stock Brd Price Qty BT BC SC ST
09:30:01 BBCA IDX 8350 100 D WA88 AB12 F
09:30:01 BBCA IDX 8350 50 A WA88 CD34 D
```

### Column Definitions
- **Time**: Transaction timestamp (HH:MM:SS)
- **Stock**: Stock code
- **Brd**: Board type
- **Price**: Transaction price
- **Qty**: Quantity in lots
- **BT**: Buyer type (D=Domestic, F=Foreign, A=Arb)
- **BC**: Buyer broker code
- **SC**: Seller broker code
- **ST**: Seller type (D=Domestic, F=Foreign, A=Arb)

## 🚀 Usage

### Getting Started
1. Open `index.html` in any modern web browser
2. Copy broker transaction data from your source
3. Click on the textarea and paste (CTRL+V / CMD+V)
4. Analysis and visualizations appear automatically

### Analyzing Results

#### Broker Summary
- Toggle between **Gross** and **Net** views using the tabs
- Gross view shows total buying/selling activity
- Net view shows net positions (buy - sell)
- Brokers are color-coded consistently across all visualizations

#### Transaction Details
- Click and drag to select multiple rows
- Selection summary appears in the bottom-right corner with:
  - Total lots
  - Total value
  - Average price
- Color-coded rows indicate Haka/Haki/Cross patterns

#### Charts
- **Net Volume Chart**: Tracks cumulative position changes for top 5 brokers
- **Time Chart**: Shows trading activity distribution throughout the session
- Both charts include price overlays for correlation analysis

## 🎨 Color Coding

### Transaction Types
- **Dark Blue** (#0b3b6b): Haka - Buying cluster
- **Dark Red** (#5a1f2d): Haki - Selling cluster
- **Purple** (#3b255c): Cross - Mixed activity

### Broker Types (BT/ST)
- **Dark** (#020617): Domestic (D)
- **Brown/Yellow** (#854d0e): Foreign (F) or Arbitrage (A)

### Broker Codes
Each broker is assigned a consistent color from a 15-color palette for easy tracking across all visualizations.

## 🔧 Technical Details

### Technologies Used
- Pure HTML/CSS/JavaScript
- [Chart.js](https://www.chartjs.org/) for data visualization
- No backend required - runs entirely in the browser

### Key Algorithms
1. **Cluster Detection**: Groups transactions by timestamp and counts broker occurrences
2. **Net Position Calculation**: Cumulative tracking of buy/sell activity per broker
3. **VWAP Calculation**: Volume-weighted average price for each time interval
4. **Dynamic Selection**: Real-time aggregation of selected rows

### Browser Compatibility
- Chrome/Edge (Recommended)
- Firefox
- Safari
- Any modern browser with ES6+ support

## 📊 Use Cases

- **Day Trading Analysis**: Identify when dominant brokers enter/exit positions
- **Market Manipulation Detection**: Spot coordinated buying/selling patterns
- **Broker Activity Tracking**: Monitor specific broker behavior over time
- **Trade Timing**: Correlate broker activity with price movements
- **Risk Assessment**: Identify concentrated broker positions

## 🔒 Privacy & Security

- All processing happens locally in your browser
- No data is sent to external servers
- No cookies or tracking
- Safe to use with sensitive trading data

## 📝 Example Workflow

1. **Export Data**: Get broker transaction summary from your trading platform
2. **Paste**: Copy the data and paste into the Bandar Detector textarea
3. **Identify Patterns**: Look for Haka/Haki indicators in the transaction table
4. **Analyze Brokers**: Check the broker summary to find dominant players
5. **Correlate with Price**: Use the charts to see how broker activity affects price
6. **Select & Calculate**: Manually select interesting time periods for custom analysis

## 🤝 Contributing

This is an open-source tool for the trading community. Feel free to:
- Report bugs or issues
- Suggest new features
- Submit improvements
- Share your analysis techniques

## ⚠️ Disclaimer

This tool is for educational and analytical purposes only. It does not provide investment advice. Always conduct your own research and consult with financial professionals before making trading decisions.

## 📄 License

MIT License - Free to use and modify

---

**Made for Indonesian stock traders** 🇮🇩

*Bandar = Indonesian term for dominant market players/brokers who can move stock prices*
