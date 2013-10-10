### Common Repeated Code
Once awhile, you might see this kind of codes floating around in your project.

```ruby
def is_visit_count?
	badge_type == "visit_count"
end

def is_spend_time?
	badge_type == "spend_time"
end

def is_spend_amount?
	badge_type == "spend_amount"
end

def is_application_usage?
	badge_type == "application_usage"
end
```

The better code might be probably:

```ruby
def is_badge_type? bt	
	badge_type == bt.to_s.downcase.underscore.strip
end
```

Or:

```ruby
%w(visit_count spend_time spend_amount application_usage).each do |bt|
	define_method "is_#{bt}?" do
		badge_type == bt
	end
end
```

Some other examples:
```ruby
scope :pendings, where(:approval_status => "pending")
scope :approveds, where(:approval_status => "approved")
scope :rejecteds, where(:approval_status => "rejected")
```

