# Weather MCP Server

This project is a Model Context Protocol (MCP) server that provides weather information using the US National Weather Service (NWS) API. It is built with FastMCP and exposes tools for retrieving weather alerts and forecasts for US locations.

## Features

- **Get Weather Alerts:** Retrieve active weather alerts for any US state.
- **Get Weather Forecast:** Get a detailed weather forecast for a specific US location (latitude/longitude).

## Requirements

- Python 3.9+
- [httpx](https://www.python-httpx.org/)
- [mcp.server.fastmcp](https://github.com/modelcontext/mcp)

Install dependencies:

```sh
pip install -r requirements.txt
```

## Usage

Run the MCP server:

```sh
python weather.py
```

The server communicates using the MCP protocol (stdio transport by default).

## Tools

### `get_alerts(state: str)`
Get active weather alerts for a US state.
- **state:** Two-letter US state code (e.g., `CA`, `NY`)

### `get_forecast(latitude: float, longitude: float)`
Get a weather forecast for a US location.
- **latitude:** Latitude of the location (must be within US bounds)
- **longitude:** Longitude of the location (must be within US bounds)

> **Note:** The NWS API only provides data for the United States and its territories. Requests for locations outside the US will return an informative error message.

## Example

```python
# Example usage with MCP client (pseudo-code)
result = get_forecast(40.7128, -74.0060)  # New York City
print(result)
```

## License

MIT License
