# nxtbn Commerce Multi-Currency Plugin

## Installation

### Via nxtbn Dashboard
1. Go to the nxtbn dashboard.
2. Navigate to `Settings > Plugin`.
3. Upload the zip file by selecting the plugin category `Currency Backend`.
4. Ensure you have downloaded the zip file from [here](https://github.com/nxtbn-com/freecurrencyapi).

### Manual Installation
1. Extract the zip file.
2. Place the extracted files in `nxtbn.plugin.source`.

The plugin will be automatically registered as a currency backend, and your site will be ready for multi-currency support.

### Via API
You can also upload using the API responsible for uploading plugins:
http://127.0.0.1:8000/core/dashboard/api/pluggin-install-via-git/

```

In the payload, send:

```json
{
    "git_url": "github plugin url",
    "plugin_type": "CURRENCY_BACKEND"
}

```

**Note:** nxtbn is not affiliated with [https://app.freecurrencyapi.com/](https://app.freecurrencyapi.com/) and does not recommend any specific currency API. nxtbn follows a philosophy of freedom, allowing you to choose any currency API and write your own currency backend. For more details on creating your own currency backend, refer to the nxtbn documentation. https://docs.nxtbn.com/

## Enabling FreeCurrencyAPI Backend

### Environment Configuration
Ensure the following environment variables are set in your `.env` file:

```
CURRENCY_BACKEND=nxtbn.plugins.sources.freecurrencyapi
CURRENCY_EXCHANGE_API_KEY=<your API key>
ALLOWED_CURRENCIES=EUR,USD,CAD,JPY,AUD
```


Add the currencies that your payment gateway and currency API support to the `ALLOWED_CURRENCIES` variable.

### Updating the .env File
1. Via nxtbn Dashboard:
   - Go to `Settings > .env`.
2. Directly in the codebase:
   - Open the `.env` file with a text editor (e.g., `nano .env`) and add the required variables.

## Refreshing Currency Rates

### Manual Refresh
1. Go to the Django admin panel.
2. Navigate to `Currency Exchange`.
3. Click on `Refresh Rate` to update the database with the latest exchange rates.

### Scheduled Refresh
1. Go to `nxtbn Settings > Cron Job`.
2. Enable `Currency Backend Auto Populate`.
3. Set the frequency for updating the exchange rates (per day, week, or hour).

nxtbn uses Celery and Celery Beat for scheduled tasks.

## Getting FreeCurrencyAPI Key
Sign up at [FreeCurrencyAPI](https://app.freecurrencyapi.com/) and obtain your free API key.

---

By following these steps, you can easily install and configure the multi-currency plugin for your nxtbn Commerce platform, ensuring seamless currency management for your e-commerce site.


# nxtbn Disclaimer

nxtbn does not endorse any specific platform, third-party service, API, payment gateway, or cloud platform. To provide merchants with the freedom to scale and select third-party services according to their preferences, nxtbn is designed with a pluggable architecture. We have developed numerous plugins for payment gateways, currency management, general purposes, CRM, automation, and integrations with various third-party APIs. However, nxtbn is not affiliated or associated with any of these third parties.

Most of the plugins developed by nxtbn are intended for demonstration purposes, enabling developers to create custom plugins tailored to their specific needs. With infinite possibilities, nxtbn does not impose limitations on customization, scalability, or platform choice. This ensures that users have the utmost flexibility to adapt and grow their systems according to their unique requirements.

