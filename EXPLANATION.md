# Metric Support Implementation Details

This fork converts the BirdNET-Pi environmental dashboard from imperial (Fahrenheit/MPH) to metric (Celsius/km/h).

## Locations of Changes
- **`scripts/utils/weather.py`**: Updated data retrieval logic to ingest native metric units.
- **`scripts/insights.php`**: 
  - Updated SQL `CASE WHEN` logic to categorize temperatures into Celsius brackets (0°C–35°C+).
  - Updated `$master_brackets` PHP array for consistent metric dashboard labels.
  - Global string replacement of 'mph' to 'km/h' for UI consistency.

## Why we did it
The original implementation hardcoded Fahrenheit logic thresholds. For regions using the metric system (such as Canada), this caused incorrect data categorization and illogical chart scaling. This implementation normalizes all weather telemetry to metric standards.
