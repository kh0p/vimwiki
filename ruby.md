## ruby

### Rakefile args

rakefile args with `:example` task:
```ruby
task :example, :arga, :argb do |t, args|
  args.display_times.to_i.times do
    puts args.display_value
  end
end
```
after running `rake example['oi',1]`; output: `oi`
