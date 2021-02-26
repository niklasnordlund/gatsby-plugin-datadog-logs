[![](https://img.shields.io/npm/v/gatsby-plugin-datadog-logs.svg)](https://github.com/niklasnordlund/gatsby-plugin-datadog-logs)

# gatsby-plugin-datadog-logs

Gatsby plugin to add Datadog log collection to your Gatsby site.

Learn more about Datadog [here](https://www.datadoghq.com/).

## Install

`npm install --save gatsby-plugin-datadog-logs`

## How to setup

```javascript
// In your gatsby-config.js
plugins: [
  {
    resolve: "gatsby-plugin-datadog-logs",
    options: {
      clientToken: 'YOUR_CLIENT_TOKEN',
      site: 'datadoghq.com',
      sampleRate: 100,
      enabled: !IS_DEV,
    }
  }
];
```

Options available are same as the [Datadog initialization parameters](https://docs.datadoghq.com/logs/log_collection/javascript/#initialization-parameters). Additionally, the parameter `enabled` (boolean) is available to programatically turn the plugin integration on/off.

## How to use

`datadogLogs` is available on the global window object, so you can use it like this:

```javascript
datadogLogs.logger.info("Hello World!");

```