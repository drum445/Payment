# financials

Methods for performing financial calculations  
Rounds to 6 decimal places

## Installation

Add this to your application's `shard.yml`:

```yaml
dependencies:
  financials:
    github: drum445/financials
```

## Usage

```crystal
require "financials"
```

### Examples (showing rounded results)

##### Payment - Float64
```crystal
# Excel function: =PMT((9.3/100)/12,36,-12995,6000,0)
puts Financials.pmt(9.3/100/12, 36, -12995, 6000, 0) # => 269.92

# Excel function: =PMT((9.3/100)/12,36,-12995,6000,1)
puts Financials.pmt(9.3/100/12, 36, -12995, 6000, 1) # => 267.84
```
##### Present Value - Float64
```crystal
# Excel function: =PV((9.3/100)/12,36,350.50,1000,0)
puts Financials.pv(9.3/100/12, 36, 350.50, 1000, 0) # => -11731.21

# Excel function: =PV(0,36,350.50,1000,0)
puts Financials.pv(0, 36, 350.50, 1000, 0) # => -13618.00

# Excel function: =PV((9.3/100)/12,36,350.50,1000,1)
puts Financials.pv(9.3/100/12, 36, 350.50, 1000, 1) # => -11816.26
```
##### NPER - Float64
```crystal
# Excel function: =NPER((10/100)/12,2625.73,-81374.62,0,0)
puts Financials.nper(10.0/100/12, 2625.73, -81374.62, 0, 0) # => 36

# Excel function: =NPER(0,2625.73,-81374.62,0,1)
puts Financials.nper(0, 2625.73, -81374.62, 0, 1) # => 31
```
##### Future Value - Float64
```crystal
# Excel function: =FV((5.8/100)/12,48,2265.63,-133781.21,0)
puts Financials.fv(5.8/100/12, 48, 2265.63, -133781.21, 0) # => 46550.0

# Excel function: =FV((5.8/100)/12,48,2265.63,-133781.21,1)
puts Financials.fv(5.8/100/12, 48, 2265.63, -133781.21, 1) # => 45960.0

# Excel function: =FV((10/100)/12,36,2625.73,-81374.62,0)
puts Financials.fv(10.0/100/12, 36, 2625.73, -81374.62, 0) # => 0.0
```
##### Rate - Float64
```crystal
# Excel function: =RATE(60,1600,-75304.59,0)
puts Financials.rate(60, 1600, -75304.59, 0) # => 0.008333

# Excel function: =RATE(30,4337.33,-112072.94,0)
puts Financials.rate(30, 4337.33, -112072.94, 0) # => 0.009917

# Excel function: =RATE(18,1909.53,-103616.44,77477)
puts Financials.rate(18, 1909.53, -103616.44, 77477) # => 0.005
```

## Contributing

1. Fork it ( https://github.com/drum445/financials/fork )
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Add some feature')
4. Push to the branch (git push origin my-new-feature)
5. Create a new Pull Request

## Contributors

- [drum445](https://github.com/drum445) ed - creator, maintainer
