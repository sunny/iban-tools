# iban-tools

iban-tools is a Ruby library for manipulating and validating IBAN account numbers.

This is a fork of [iulianu/iban-tools](https://github.com/iulianu/iban-tools)
with a few changes:

- [#31](https://github.com/iulianu/iban-tools/pull/31): Add a few countries and fix existing patterns 🌐
- [#27](https://github.com/iulianu/iban-tools/pull/27): README: Drop mention of rubyforge, use https

## Installation

```sh
bundle add iban-tools
```

## Usage

```rb
IBANTools::IBAN.valid?("GB82 WEST 1234 5698 7654 32")
# => true
```

Advanced usage, gives more detailed error messages:

```rb
IBANTools::IBAN.new("XQ75 BADCODE 666").validation_errors
# => [:unknown_country_code, :bad_check_digits]
```

Pretty print, canonicalize, and extract fields from an IBAN code:

```rb
iban = IBANTools::IBAN.new(" ro49  aaaa 1B31007593840000")

iban.code
# => "RO49AAAA1B31007593840000"

iban.country_code
# => "RO"

iban.prettify
# => "RO49 AAAA 1B31 0075 9384 0000"
```

## Read more

You can [read more about IBAN](http://en.wikipedia.org/wiki/International_Bank_Account_Number) on Wikipedia.
