
# Преобразува числата словом на Български и Руски.

[![npm version](https://badge.fury.io/js/number-to-cyrillic.svg)](https://badge.fury.io/js/number-to-cyrillic)

Converts number to words (BGN, UAH, RUB, USD, EUR and without currency).
Тази билиотека поддържа превод на Български и Руски.

## Install

`https://raw.githubusercontent.com/vidul-nikolaev-petrov/number-to-cyrillic/master/lib/numberToString.js`

## API

### `.convert(number[, options])`

Converts an integer into an object witch contain value and the currency name. Optionally you can decide whether to display output with currency or not, to display a capital letter for the value
by adding an object with some propertis. For example:

```js
var numberToString = require('number-to-cyrillic');

numberToString.convert(76.15);
// {
//     convertedFractional: "петнадесет";
//     convertedInteger: "седемдесет и шест";
//     currenyLang: "bg";
//     fractional: 15;
//     fractionalCurrency: "стотинки";
//     fractionalString: "15";
//     integer: 76;
//     integerCurrency: "левa";
//     shortName: "BGN";
// }


numberToString.convert(21, {
  currency: 'uah'
});
// {
//    convertedInteger: 'двадцять одна',
//    integerCurrency: 'гривня',
//    convertedFractional: 'нуль',
//    fractionalCurrency: 'копійок',
//    integer: 21,
//    fractional: 0,
//    shortName: 'грн.'
// }

numberToString.convert(34, {
  currency: 'usd'
});
// {
//    convertedInteger: 'тридцять чотири',
//    integerCurrency: 'долари США',
//    convertedFractional: 'нуль',
//    fractionalCurrency: 'центів',
//    integer: 34,
//    fractional: 0,
//    shortName: 'долара США'
// }

numberToString.convert(76.21, {
  capitalize: true
});
// {
//    convertedInteger: 'Сімдесят шість',
//    integerCurrency: 'гривень',
//    convertedFractional: 'двадцять одна',
//    fractionalCurrency: 'копійка',
//    integer: 76,
//    fractional: 21,
//    shortName: 'грн.'
// }

numberToString.convert(76.26, {
  language: 'en'
});
// {
//    convertedInteger: 'seventy-six',
//    integerCurrency: 'hryvnias',
//    convertedFractional: 'twenty-six',
//    fractionalCurrency: 'cents',
//    integer: 76,
//    fractional: 26,
//    shortName: 'UAH'
// }
```

See detailed description of all available options below:

|              Option              | Default Value | Description                                                                                                                                          |
| :------------------------------: | :-----------: | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
|            capitalize            |  **`false`**  | By setting a value for this option to `true` you might make the first letter in uppercase                                                            |
|             currency             |  **`'uah'`**  | By setting a value to this option to `'usd'` or `'eur'` or `'rub'` or `false` you'll get the output for selected currency name or without currency.  |
|             language             |  **`'ua'`**   | By setting a value to this option to `'en'` or `'ru'` you'll get the output for selected language.                                                   |
| customDecimalNameCasesForEnglish |  **`false`**  | By setting a value for this option to `true` you will change default decimal name cases for UAH and RUB in English translation to `kopek`, `kopeks`. |
| customCurrencyPrefixForEnglish |  **none**  | By setting a value for this option to a string you will change the default currency in English translation. E.g. without prefix: `dollars`, with - `US dollars` |
