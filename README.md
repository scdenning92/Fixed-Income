# Fixed-Income
Objects useful for modelling bonds and other instruments

YieldCurve Object:
Yield Curve can read either a set of observed bonds: 
  -add_instrument(par, maturity, coupon, price, compounding_frequency)
or can pass a par curve in the constructor:
  -YieldCurve([mats], [yields])
Object methods can give spot rates and forward rates:
YieldCurve.get_zero_rates()
YieldCurve.get_forward_rates(n)


Bond Object: 
Reads either a dictionary of {datetime:cashflow} pairs,
or coupon, par, issue date and maturity date in constructor:
  --dict of cashflows created from these variables (assumes semi-annual coupons and par paid at maturity)
Bond Object can find price and duration of the bond:
get_price(datetime, YieldCurve)
--given a datetime and corresponding YieldCurve for that day, returns price
get_duration(datetime, YieldCurve)
--given a datetime and corresponding YieldCurve for that day, returns duration

