# StockMarket
A C program that handles values of an investment company's shares, derivatives and CDS

The integer array risk[11] represents the estimated risk for each CDS derivative that appears in the cds_prices[] array:

c
Copy code
float cds_prices[11] = {38.5, 33.4, 67.8, 12.1, 16.0, 10.25, 11, 23, 36, 10.1, 30.4};
int risk[11] = {90, 10, 20, 30, 50, 60, 30, 30, 30, 10, 10};
Traders assign a rating value to each CDS, derived from the following rules:

If the CDS price is less than 20 and the risk is less than 50, the rating value is 20.
If the CDS price is greater than or equal to 20 and the risk is less than 80, the rating value is calculated using the formula: 10 + (cds * risk) / 100.
In any other case, the CDS value is calculated using the formula: 100 + (cds * risk) / 100.
The program displays for each CDS derivative, its price, risk, and corresponding rating value.

The array deriv_day_data[5][10] contains, for each of the five derivatives, the price evolution throughout a trading day, i.e., 10 prices during the day per derivative. The last price is the closing price.

A function named high_low calculates, for a given derivative i, how many daily prices were strictly higher than the closing price and how many were strictly lower, by examining the array deriv_day_data for the specific derivative.

The function should display (within the main() function) for each derivative how many prices were above and how many were below the closing price.

A function:

c
Copy code
bool element(float value, int row, int *pos, int r, int c, float table[r][c])
should return TRUE if the value is found in the specified row of the table[r][c]. The function searches for the value in the row of the array table[r][c], and if found, it returns TRUE and the position (column) in the argument *pos. If the element is not found, the function returns FALSE.
