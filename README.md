# Regata Subscription System

## Contributors

- Gildas Quéméner <gildas dot quemener at gmail dot com>

## License

MIT License

## Background Context

This is a TDD sandbox project aiming to try, fail, improve introducing TDD in a legacy context, while following [this course](https://journal.optivem.com/p/tdd-in-legacy-code-outline) on the Optivem Journal.

The domain of the project is the subscription step to a regata.

## Use cases

The system allows sailors to register their boat, along with their crew, at a scheduled regata.

The system allows them to make modification to their registration, as long as the registration are opened (usually 30 minutes prior to the beginning of the race).

The system allows them to pay online any registration fees.

Sailors receive in real-time race-related information (documents, amendment, etc.)

## External Systems

- EasyPay: a payment gateway providing online payment service
- EasyWeatherForecast: a weather forecast service providing detailed conditions on the water body
- EasyWhatsApp: a WhatsApp integration, allowing to automatically send messages to a WhatsApp group
