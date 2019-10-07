#Smart Contracts Tools

There are bunch of tools for developers in Earths ecosystem.

## Code
You have two main options to write code with syntax highlighting and IntelliSense (code completion):
 - [Online IDE](https://ide.earths.ga)
 - [Visual Studio Code Extension](../developer-tools/earths-ide.md)

>[!TIP]
> Online IDE and Visual Studio Code Extension support helper functions in REPL-like consoles.
> [Read more]() to find out more details about supported functions.

## Compiling and decompiling scripts
RIDE compiler is a part of [Earths Node](https://github.com/earthspay/Earths) and available in API. For example, you can find documentation for Earths public nodes by the following link: [https://nodes.earths.ga/api-docs/index.html#!/utils/compile](https://nodes.earths.ga/api-docs/index.html#!/utils/compile).
If you want to compile scripts without a node you can use [ride-js](https://github.com/earthspay/ride-js) library or use [Maven Compiler](../ride-language/maven-compiler.md)

>[!NOTE]
> To decompile script please use [/utils/decompile](https://nodes.earths.ga/api-docs/index.html#!/utils/decompile_1) method.

## Testing
You can use [Earths IDE Console]() to send transactions and test your contract. We highly recommend to read more about console function in the [overview](../earths-console-commands/earths-console-commands.md) and [examples](../earths-console-commands/examples.md) sections of documentation.