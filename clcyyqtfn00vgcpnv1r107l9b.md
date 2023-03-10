# Why do we have config.js?

The config.js file is a JavaScript file that contains configuration settings for your application. These settings can include things like API keys, server URLs, and other settings that are likely to change depending on the environment (development, staging, production) or settings that you want to keep separate from your application code.

By keeping these settings in a separate file, it makes it easier to manage and maintain your application, as you can change the settings in one place and have them propagate throughout your app.

A good example is API keys, often API keys are specific to an environment and you don't want to hardcode them in your codebase. Instead, you can store them in the config file and call them accordingly when required.

The config.js file could also be used to store other environment-specific settings, such as server URLs, database connection strings, and so on. This makes it easy to switch between different environments without having to manually update the settings in your code.

Having a config file also makes it easier to manage security sensitive information as you don't have to hard code them, also it's a best practice to not check in sensitive information like API keys and secrets into your version control system, by keeping it separate you can keep this information secure and also not pollute your codebase.

Overall, the config.js file is a useful tool for keeping your application organized and maintainable and can help you more easily manage settings that are likely to change or are sensitive.