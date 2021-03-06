# Japan Bitcoin Index (JBI)  

JBI is a volume weighted average of btc market price in Japan.  The figure is currently taken from five major Japanese btc markets who have more than 90% volume share in entire JPY based trading; bitFlyer, Quoine, BtcBox, Zaif and coincheck.

## Aims  

JBI is intended to serve as a standard retail price reference for industry participants, both personal and professional. Following use applications are assumed but are not limited to.  
- Price reference for commercial transaction between individuals and merchant.
- Price reference for micro-payment among individuals.
- Ticker for websites.
- Benchmark for index funds e.c. ETF.

## Calculation

1. Selecting top 5 Japanese btc markets who have own JPY-BTC ticker, are able to deposit and withdraw JPY.
2. Taking last traded price and 24 hours trading volume of actuals from the top 5 Japanese btc markets' public APIs, and round off decimals to simplify the calculation.
3. Calculating volume weighted average price from the data above.

- The 5 markets are called by their volume share, and will be reviewed annually, end of each year.
- JBI historical data commenced on 16 December 2016, and recorded every 5 minutes.
- In case API error, the data will not be recorded and skipped.

## Form of implementation and function

The script is written as Google Apps Script function aiming to record the index in Fusion Tables and provide Web API.  

To access the historical data table;
https://www.google.com/fusiontables/DataSource?docid=1Ci5IUvYy_59-wIU751i6Xc7x7R2yxaq6Yxei1O7I  

Web API end point which gives realtime JBI and its time stamp is;  
https://script.google.com/macros/s/AKfycbxHoGcej3QbKLdw0vF5qoijwD5n9dZNP-N2DzLM7AiuqzuYTTE/exec  
with `?option=market` gives JBI with market data of calculation base.  Please note: since this API is implemented in Google Apps Script, [the API serves from redirected one-time URL](https://developers.google.com/apps-script/guides/content#redirects), so please configure your HTTPS client to follow the redirect. For Node.js, you can use [this module](https://github.com/olalonde/follow-redirects).
## Usage of code

The project is licensed as MIT license.  There are no restrictions for forks, reutilizations and other forms of implementation as long as those keep the characteristics of index: data sources and calculation base.

Please feel free to use JBI and its code. If you have any queries, please drop a message to [@M_Igashi](https://twitter.com/M_Igashi) by twitter.
