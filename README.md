<img src="assets/logo.png" alt="Jerry" width="64" height="64">

# Jerry

Shop for insurance from Cursor or Grok Bot. Jerry is a licensed insurance broker that compares real quotes from 100+ insurers. Your agent gathers what the quotes need, Jerry gets them, and you buy the policy you pick in the Jerry app.

This plugin connects your agent to Jerry's MCP server at `https://mcp.jerry.ai/mcp`. It holds no code, only that address.

## What you can do

- Get quotes for car, motorcycle, home, condo, townhouse and renters insurance.
- Answer only what's left. Jerry fills in what it can once it has your name, date of birth and address, and your agent asks you for the rest.
- Compare quotes by plan, price, coverages, discounts and payment plans.
- Get the final price on the quote you pick, then finish buying it in the Jerry app.

Nothing goes to an insurer until you've seen a summary of what will be sent and said yes.

## Sign in

The first time your agent uses Jerry, it asks you to sign in. Enter your US mobile number and the code Jerry texts you. If you don't have a Jerry account, signing in creates a free one. Then review what the agent will be allowed to do, and allow it.

There's nothing to configure and no API key. `mcp.json` sends `X-Jerry-Require-Sign-In: true` so that Jerry asks you to sign in when the agent first connects, which is when Cursor and Grok Bot open sign-in. It also names Jerry's registered client for Cursor (`auth.CLIENT_ID`), so the sign-in page shows the request as coming from Cursor.

## Example prompts

- "Find me cheaper car insurance. I'm paying about $180 a month with Geico for my 2019 Honda Civic."
- "Get me car insurance quotes for me and my wife. We have two cars and live in Austin."
- "Compare the three cheapest quotes Jerry found. What's different about the coverage and discounts?"
- "I want full coverage with a $500 deductible. Can you get me quotes for that?"
- "Get me the final price on the Progressive quote."
- "I just moved into an apartment. Can you get me renters insurance quotes through Jerry?"

## Tools

| Tool | What it does |
| --- | --- |
| `jerry_get_account` | Reads the name, email and phone on your Jerry account. |
| `jerry_start_shopping` | Starts shopping for the insurance you want, or picks up where you left off. |
| `jerry_update_application` | Saves your drivers, cars, address, coverage and insurance history, and adds the drivers and cars Jerry found once you confirm them. |
| `jerry_get_status` | Shows what's still needed, what Jerry found, and the summary to confirm when a request is ready. |
| `jerry_request_quotes` | Asks insurers for quotes, after you've seen the summary and said yes. |
| `jerry_wait` | Waits while quotes or a final price come in. |
| `jerry_get_quotes` | Lists the quotes, cheapest first, and compares up to 4 of them in detail. |
| `jerry_request_final_price` | Asks the insurer for the final price of the quote you picked, after your yes. |

Full documentation, including endpoints, authentication, scopes, errors and limits, is at <https://mcp.jerry.ai/docs>.

## Privacy and support

Jerry uses what you provide to fill in your application and get your quotes, and shares it with insurers only to quote and price. It keeps your yes on each request as the record of your consent. Payment and signing happen in the Jerry app, never through your agent. See the [privacy policy](https://jerry.ai/privacy-policy/) and [terms of use](https://jerry.ai/terms-of-use/).

For help, email [hi@jerry.ai](mailto:hi@jerry.ai). To disconnect Jerry, uninstall this plugin or remove the Jerry MCP server in your agent's settings.

## License

[MIT](LICENSE)
