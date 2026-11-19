# US State & County FIPS Codes Cheatsheet

Use this reference to update `STATE_FIPS` and `COUNTY_FIPS` in your configuration script. Keep all FIPS codes formatted as **strings** (e.g., `'01'`, `'48'`) so leading zeros are preserved.

---

## US State & Territory FIPS Codes (`STATE_FIPS`)

| State / Territory | Abbr. | FIPS | | State / Territory | Abbr. | FIPS |
| :--- | :---: | :---: | --- | :--- | :---: | :---: |
| **Alabama** | AL | `'01'` | | **Montana** | MT | `'30'` |
| **Alaska** | AK | `'02'` | | **Nebraska** | NE | `'31'` |
| **Arizona** | AZ | `'04'` | | **Nevada** | NV | `'32'` |
| **Arkansas** | AR | `'05'` | | **New Hampshire** | NH | `'33'` |
| **California** | CA | `'06'` | | **New Jersey** | NJ | `'34'` |
| **Colorado** | CO | `'08'` | | **New Mexico** | NM | `'35'` |
| **Connecticut** | CT | `'09'` | | **New York** | NY | `'36'` |
| **Delaware** | DE | `'10'` | | **North Carolina** | NC | `'37'` |
| **District of Columbia** | DC | `'11'` | | **North Dakota** | ND | `'38'` |
| **Florida** | FL | `'12'` | | **Ohio** | OH | `'39'` |
| **Georgia** | GA | `'13'` | | **Oklahoma** | OK | `'40'` |
| **Hawaii** | HI | `'15'` | | **Oregon** | OR | `'41'` |
| **Idaho** | ID | `'16'` | | **Pennsylvania** | PA | `'42'` |
| **Illinois** | IL | `'17'` | | **Rhode Island** | RI | `'44'` |
| **Indiana** | IN | `'18'` | | **South Carolina** | SC | `'45'` |
| **Iowa** | IA | `'19'` | | **South Dakota** | SD | `'46'` |
| **Kansas** | KS | `'20'` | | **Tennessee** | TN | `'47'` |
| **Kentucky** | KY | `'21'` | | **Texas** | TX | `'48'` |
| **Louisiana** | LA | `'22'` | | **Utah** | UT | `'49'` |
| **Maine** | ME | `'23'` | | **Vermont** | VT | `'50'` |
| **Maryland** | MD | `'24'` | | **Virginia** | VA | `'51'` |
| **Massachusetts** | MA | `'25'` | | **Washington** | WA | `'53'` |
| **Michigan** | MI | `'26'` | | **West Virginia** | WV | `'54'` |
| **Minnesota** | MN | `'27'` | | **Wisconsin** | WI | `'55'` |
| **Mississippi** | MS | `'28'` | | **Wyoming** | WY | `'56'` |
| **Missouri** | MO | `'29'` | | **Puerto Rico** | PR | `'72'` |

---

## Texas & Major Metro County FIPS Codes (`COUNTY_FIPS`)

All Texas counties use `STATE_FIPS = '48'`. Pass county codes as a list of 3-digit strings (e.g., `COUNTY_FIPS = ['113', '439']`).

### DFW Metroplex Counties
| County | FIPS | County | FIPS |
| :--- | :---: | :--- | :---: |
| **Dallas** | `'113'` | **Johnson** | `'251'` |
| **Tarrant** | `'439'` | **Kaufman** | `'257'` |
| **Collin** | `'085'` | **Parker** | `'367'` |
| **Denton** | `'121'` | **Rockwall** | `'397'` |
| **Ellis** | `'139'` | **Wise** | `'497'` |

### Other Major Texas Metro Counties
| Metro Area | County | FIPS |
| :--- | :--- | :---: |
| **Houston** | Harris | `'201'` |
| **Houston** | Fort Bend | `'157'` |
| **Houston** | Montgomery | `'339'` |
| **San Antonio** | Bexar | `'029'` |
| **Austin** | Travis | `'453'` |
| **Austin** | Williamson | `'491'` |
| **Austin** | Hays | `'209'` |
| **El Paso** | El Paso | `'141'` |
| **Rio Grande Valley** | Hidalgo | `'215'` |
| **Bryan–College Station** | Brazos | `'041'` |

---

## Quick Lookup Tips

* **Why strings?** Single-digit state codes (like `'06'` for California) and county codes (like `'029'` for Bexar) require leading zeros. Formatting them as Python integers will drop the leading zero and break Census/TIGER dataset queries.
* **5-Digit GEOID:** If a dataset asks for a combined 5-digit county GEOID, concatenate `STATE_FIPS + COUNTY_FIPS` (e.g., Dallas County = `'48' + '113'` = `'48113'`).
* **Full National Lookup:** You can look up any of the 3,143 US county FIPS codes directly via the [US Census Bureau ANSI/FIPS Reference](https://www.census.gov/library/reference/code-lists/ansi.html).