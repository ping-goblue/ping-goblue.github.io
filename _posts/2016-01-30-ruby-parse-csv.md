---
layout: post
title: Ruby parses CSV file to an array of hash with symbolized keys
category: ruby
---

```ruby
require "csv"

def parse_csv_return_array_of_hash(file_name)
  CSV.read(file_name, :headers => true, :header_converters => :symbol).collect do |row|
    row.to_hash
  end
end
```

For example, with the following input file:

```
year,month,date
2015,01,11
2016,01,12
```
it will return the following result:

```ruby
[
  {:year=>"2015", :month=>"01", :date=>"11"},
  {:year=>"2016", :month=>"01", :date=>"12"}
]
```
[A more detail explanation](http://technicalpickles.com/posts/parsing-csv-with-ruby/)
