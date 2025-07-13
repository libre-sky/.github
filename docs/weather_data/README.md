# Weather Data

## Instantaneous Readings

Data such as temperature, humidity, and pressure are measured at an instant.

## Temporal Readings

Data like precipitation is reported as an amount and a type over some time frame (ie: 3 inches of snow over the last 12 hours).

## Resolution

How do we aggregate data?

### Time

- **Current:** The current reading. What does *current* mean? Some guarantee of data freshness should be present on a per-metric level.
  - *Instantaneous Readings:* 1 Minute
  - *Temporal Readings*: 1 Hour
- **Historical:** Get readings from the past. Hourly?

### Location

What is a useful way to aggregate data based on location?

- what are aggregation options?
  - *polar grid*
    - most geo data is polar coords
    - inconsistent region size - does that matter
  - *square tiles*
    - consistent size
    - nonstandard - needs translation
- At what precision does it not make sense to provide more local precision?
- How to protect identity of nodes?
  - 100m precision? 1km?
