# okta-insights-queries

A collection of queries useful for an Okta/New Relic Insights integration.

#### Failed Okta Sign-Ins by User (Top 10)

`SELECT count(*) FROM OktaEvents WHERE message LIKE 'Sign-in Failed%' FACET target1 SINCE 2 days ago TIMESERIES LIMIT 10`

#### Failed Okta Multifactor Attempts by User (Top 10)

`SELECT count(*) FROM OktaEvents WHERE message LIKE 'Failed%factor attempt' FACET target1 SINCE 2 DAYS AGO TIMESERIES LIMIT 10`

#### Successful Okta Sign-Ins from Outside US by Country

`SELECT count(*) FROM OktaEvents WHERE message='Sign-in successful' AND srcCountry!='United States' FACET srcCountry SINCE 2 days ago TIMESERIES LIMIT 1000`

#### Successful Okta Sign-Ins from Outside US by User

`SELECT count(*) FROM OktaEvents WHERE message='Sign-in successful' AND srcCountry!='United States' AND FACET target1 SINCE 2 days ago TIMESERIES`

#### Successful Okta Sign-Ins from Outside US by IP Address

`SELECT count(*) FROM OktaEvents WHERE message='Sign-in successful' AND srcCountry!='United States' AND FACET srcIP SINCE 2 days ago TIMESERIES`
