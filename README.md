## Countries.json

A comprehensive JSON dataset containing country information with phone number validation rules and metadata.

### Structure

Each country entry contains:

- **code**: ISO 3166-1 alpha-2 country code (e.g., "SA", "EG", "AF")
- **name**: Country name in English
- **name_ar**: Country name in Arabic (Unicode format)
- **phone**: Phone number specifications
  - `dial_code`: International dialing code (e.g., "+966")
  - `digit_count`: Number of digits in phone numbers
  - `trunk_prefix`: National dialing prefix (e.g., "0") or `null`
  - `validation`: Regular expression patterns for validation
    - `local_pattern`: Pattern for local format (with trunk prefix)
    - `international_pattern`: Pattern for international format
  - `examples`: Sample phone numbers
    - `local`: Example in local format
    - `international`: Example in international format
- **meta**: Additional metadata
  - `flag_emoji`: Unicode flag emoji representation
  - `region`: Geographic region in English
  - `region_ar`: Geographic region in Arabic (Unicode format)

### Example Entry

```json
{
  "code": "SA",
  "name": "Saudi Arabia",
  "name_ar": "المملكة العربية السعودية",
  "phone": {
    "dial_code": "+966",
    "digit_count": 9,
    "trunk_prefix": "0",
    "validation": {
      "local_pattern": "^0?[5][0-9]{8}$",
      "international_pattern": "^\\+966[5][0-9]{8}$"
    },
    "examples": {
      "local": "0512345678",
      "international": "+966512345678"
    }
  },
  "meta": {
    "flag_emoji": "🇸🇦",
    "region": "Middle East",
    "region_ar": "الشرق الأوسط"
  }
}
```

### Use Cases

- Phone number validation and formatting
- Country selection dropdowns with flags
- International dialing interfaces
- Localization support (Arabic translations)
- Regional filtering and grouping
