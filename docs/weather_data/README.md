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
- **Historical:** Get readings from the past. Hourly? 8hr? Daily?

#### How to represent time ranges?

Candlesticks seems reasonable, or just one of \(high, low\) or \(begin, end\).

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
  - note: NOAA handles data zones by using a 2.5km by 2.5km grid. The grid coords are retrievable by an endpoint where you specify lat,long coords. You then get data based on that grid tile
- How to protect identity of nodes?
  - 100m precision? 1km?

## Units

### Pollutants

Air quality is calculated based on the concentration of some key pollutants:

- *PM<sub>2.5</sub>:* &mu;g/m<sup>3</sup>
- *PM<sub>10</sub>:* &mu;g/m<sup>3</sup>
- *CO:* ppm or &mu;g/m<sup>3</sup>
- *O<sub>3</sub>:* &mu;g/m<sup>3</sup> or ppm
- *Sulfer Dioxide \(SO<sub>2</sub>\):* &mu;g/m<sup>3</sup> or ppb
- *Nitrogen Oxides \(NO<sub>2</sub>\):* &mu;g/m<sup>3</sup> or ppb

For info on AQI calculation, see [here](https://document.airnow.gov/technical-assistance-document-for-the-reporting-of-daily-air-quailty.pdf). note: some stations only report pollutants on 8-hour basis.


### Precipitation

Precipitation magnitude should be reported in cm with precision \(maybe\) down to 0.1cm. Time ranges should be:
- 30 mins \(`30m`\)
- 1 hour \(`1h`\)
- 3 hour \(`3h`\)
- 6 hour \(`6h`\)
- 24 hour \(`24h`\)

### Atmospheric

- *Pressure:* Pascal \(Pa, hPa, kPa\)
- *Temperature:* Celsius \(&#176;C\)
- *Humidity:* Relative Humidity \(%\)
- *Wind Speed:* Meters/second \(m/s\)
- *Wind Direction:* Degrees \(&#176;\) \(reported as wind origin - where the wind is coming from\)
