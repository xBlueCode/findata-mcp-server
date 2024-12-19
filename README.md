# Financial Data - MCP Server

This is an MCP server that provides access to the Alpha Vantage API, allowing stock data retrieval to be used as context to LLMs.

<a href="https://glama.ai/mcp/servers/czslwc47w9"><img width="380" height="200" src="https://glama.ai/mcp/servers/czslwc47w9/badge" alt="findata-mcp-server MCP server" /></a>

## Available Features

*   `getStockQuote`: Get the current quote for a stock.
*   `getHistoricalData`: Get historical data for a stock (daily, weekly, or monthly).
*   (More tools will be added later for technical analysis, company overview, etc.)

## Setup

```bash
npm install findata-mcp-server
```

## Usage in Host
1. Obtain an API key from Alpha Vantage https://www.alphavantage.co/support/#api-key.


2. Configure your MCP client (e.g., Claude Desktop) to connect to the server:

```JSON
{
  "mcpServers": {
    "alphaVantage": {
      "command": "npx",
      "args": ["-y", "findata-mcp-server"],
      "env": {
        "ALPHA_VANTAGE_API_KEY": "PUT_YOUR_API_KEY_HERE"
      }
    }
  }
}
```

## Tools
### `getStockQuote`
Get the current quote for a stock.

Input:

`symbol`: The stock symbol (e.g., AAPL)
Output Example:


### `getHistoricalData`
Get historical data for a stock.

Input:

- `symbol`: the stock symbol (e.g., AAPL)
- `interval`: the time interval for the data (`daily`, `weekly`, or `monthly`) (optional, default: `daily`)
- `outputsize`: the size of the output (`compact` or `full`) (optional, default: `compact`)
Output:

JSON object containing the historical data. The structure of the output depends on the interval parameter.

## Contributing
Contributions are welcome! Please open an issue or pull request.


### License
MIT
