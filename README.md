# Simple E-Commerce Demo


This project demonstrates a catalogue display, shopping cart, and transaction endpoints using XHTML, CSS, JavaScript, PHP, and an optional C# Web API backend example.


## Features
- Product catalogue with responsive layout (XHTML + CSS)
- Add/remove/update cart (JavaScript + localStorage)
- Place order (PHP endpoint /server/api.php) — mocked transaction handler
- C# Web API example (OrdersController) showing how to replace PHP with ASP.NET Core


## How to run


### Static site (XHTML + JS)
1. Open `index.xhtml` in a browser. For full functionality (calling PHP), run via a local web server.
- On macOS/Linux: `php -S localhost:8000 -t .`
- Or place in Apache `htdocs` and ensure `server/api.php` is reachable at `/server/api.php`.


### PHP server
1. Ensure PHP 7.4+ is installed.
2. Start the built-in server in repository root: `php -S localhost:8000`
3. Open `http://localhost:8000/index.xhtml`.


### C# Web API (optional)
1. Requires .NET 7+ SDK.
2. Navigate to `/csharp` folder and run `dotnet run`.
3. Replace the client `fetch` URLs to point to the C# endpoints.


## Notes & Best Practices
- **Security**: Do not process payments directly in PHP without PCI compliance. Use payment provider SDKs for production.
- **Input validation**: Validate on client and server side. Server-side validation is authoritative.
- **Sanitize outputs**: Prevent XSS by escaping any untrusted values.
- **Error handling**: Respond with clear error codes & messages from API endpoints. Show friendly messages to users.
- **Performance**: Minify assets, use caching headers, lazy load images, and paginate large catalogues.


## Files to modify for your project
- `index.xhtml`: UI and catalogue listing
- `scripts/app.js`: cart logic & API calls
- `server/api.php`: order creation and transaction flow
- `csharp/*`: optional replacement API using ASP.NET Core
