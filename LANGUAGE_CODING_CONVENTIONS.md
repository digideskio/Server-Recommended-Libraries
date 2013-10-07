#Source Code Layout
* Indentation: two spaces(ruby), no tabs

* Use consistent structure in your class definitions

```ruby  
class Person  
  # extend and include go first  
  extend SomeModule  
  include AnotherModule  
  
  # constants are next
  SOME_CONSTANT = 20

  # afterwards we have attribute macros
  attr_reader :name

  # followed by other macros (if any)
  validates :name

  
  # public class methods are next in line
  def self.some_method
  end

  # followed by public instance methods
  def some_method
  end

  # protected and private methods are grouped near the end
  protected

  def some_protected_method
  end

  private

  def some_private_method
  end
end
```
* Use empty lines to break up a method into logical paragraphs , and add comment to each paragraphs

```ruby
# BAD
def method
  data = initialize(options)
  data.manipulate!
  data.result
end

# GOOD
def method
  # initialize data
  data = initialize(options)

  # manipulate data
  data.manipulate!
        
  # return data
  data.result
end
```
* When define multiple class methods using

```ruby
class << self
  def first_class_method
    # body
  end
  
  def second_class_method
    #body
  end
end
```
* Use spaces around operators, after commas, colons and semicolons, around { and before }

```ruby
# BAD
sum=1+2
a,b=1,2
[1,2,3].each{|i|i+1}

# GOOD
sum = 1 + 2
a, b = 1, 2
[1, 2, 3].each { |i| i + 1 }
```
* When assigning the result of a conditional expression to a variable, preserve the usual alignment of its branches

```ruby
# BAD
result = if condition
  "bad"
else
  "terrible"
end

result = case i
when 0 then "zero"
when 1 then "one"
when 2 then "two"
else "zero"

# GOOD
result = if condition
           ...     
           "excellent"
         else
           ...
           "good"
         end
         
result = case i
         when 0 then "zero"
         when 1 then "one"
         when 2 then "two"
         else "zero"
```
* Align the parameters of a method call if they span more than one line. When aligning parameters is not appropriate due to line-length constraints (80 characters per line)

```ruby
# BAD
Mailer.deliver(to: 'bob@example.com', from: 'us@example.com', subject: 'Important message')

# GOOD
Mailer.deliver(
  to: 'bob@example.com',
  from: 'us@example.com',
  subject: 'Important message'
)
```
#Syntax
* Use def with parentheses when there are arguments

```ruby
# BAD
def method a,b
def method()

# GOOD
def method(a, b)
def method
```
* Add underscores to large numeric literals to improve their readability

```ruby
# BAD
x = 1000000000

# GOOD
x = 1_000_000_000
```
* Favor modifier if/unless/while/until... usage when you have a single-line body

```ruby
# BAD
if condition
  x = 2
end

if condition
  x = 2
else
  x = 1
end

# GOOD
x = 2 if condition

condition ? x = 2 : x = 1
```
* Using “&&, ||” instead of “and, or”

```ruby
# BAD
foo = :foo
bar = nil
x = bar or foo 
=> x = nil (because precedence '=' > 'or')

# GOOD
foo = :foo
bar = nil
x = bar || foo
=> x = :foo (because precedence '||' > '=')
```
* Prefer { … } over do...end for single-line blocks, prefer do...end for multi-line blocks, avoid do...end when chaining

```ruby
# BAD
names.each do 
  |name| name.capitalize! 
end.map(&:reverse)

# GOOD
names.each { |name| name.capitalize! }.map(&:reverse)
  
names.each do |name|
  line1
  line2
end
```
* Avoid “return“ where not required for flow of control

* Avoid “self” where not required. (It is only required when calling a self write accessor)

```ruby
# BAD
class MyClass < ActiveRecord::Base
  scope :my_scope, ->{ self.where(id: 1)}
end

# GOOD
class MyClass < ActiveRecord::Base
  scope :my_scope, ->{ where(id: 1)}
end
```
* Avoid use of nested conditionals for flow of control. Prefer a guard clause when you can assert invalid data. A guard clause is a conditional statement at the top of a function that bails out as soon as it can

```ruby
# BAD
def compute_thing(thing)
  if thing[:foo]
    update_with_bar(thing)
    if thing[:foo][:bar]
      partial_compute(thing)
    else
      thing
    end
  end
end

# GOOD
def compute_thing(thing)
  return unless thing[:foo]
  update_with_bar(thing)
  return thing unless thing[:foo][:bar]
  partial_compute(thing)
end
```
* Prefer %w, %i to the literal array syntax when you need an array of words or array of symbols

```ruby
ROLE = %w(admin mod user) => ["admin", "mod", "user"]

ADDRESSABLE = %i(address city state)  => [:address, :city, :state]
```
* When accessing the first or last element from an array, prefer first or last over [0] or [-1]

```ruby
# BAD
array = %w(a b c)
array[0]
array[-1]

# GOOD
array = %w(a b c)
array.first
array.last
```

* Prefer symbols instead of strings as hash keys

```ruby
# BAD
hash = {"one" => 1, "two" => 2}

# GOOD
hash = {one: 1, two: 2}
```
* Prefer string interpolation instead of string concatenation

```ruby
# BAD
email_with_name = user.name + '<' + user.email + '>'

# GOOD
email_with_name = "#{user.name}<#{user.email}>"
```
#Naming
* Use __CamelCase__ for classes and modules

```ruby
class MyCamelCaseClass
```
* Use __snake_case__ for symbols, methods and variables

```ruby
:some_symbol
def some_method; end
some_variable
```
* Use __SCREAMING_SNAKE_CASE__ for constants

```ruby
MY_CONSTANT = 5
```
* The names of predicate methods (methods that return a boolean value) should end with a __question mark__. (i.e Array#empty?)

* The names of potentially dangerous methods (i.e modify self or the arguments) should end with an __exclamation mark__ if there exists a safe version of that dangerous method

* Use _ for unused block parameters

```ruby
# BAD
result = hash.map { |k, v| v + 1 }

# GOOD
result = hash.map { |_, v| v + 1 }
```
* The length of an identifier determines its scope.  Use one-letter variables for short block/method parameters, according to this scheme

```ruby
a,b,c: any object
d: directory names
e: elements of an Enumerable
ex: rescued exceptions
f: files and file names
i,j: indexes
k: the key part of a hash entry
m: methods
o: any object
r: return values of short methods
s: strings
v: any value
v: the value part of a hash entry
x,y,z: numbers
```
#Rails
####Model
* Move finder, filter to scope (reuse and readability)

```ruby
# BAD
class EntriesController < ApplicationController
  def index
    @entries = Entry.where(published: true).where(“updated_at > ?”, Time.now)
  end
end

# GOOD
class EntriesController < ApplicationController
  def index
    @entries = Entry.published.from_time(Time.now)
  end
end

class Entry < ActiveRecord::Base
  scope :published, ->{ where(published: true) }
  scope :from_time, ->(time){ where(“updated_at > ?”, time) }
end
```
* Prefer __has_many :through__ to __has_and_belongs_to_many__. Using has_many :through allows additional attributes and validations on the join model

* Keep finder on their own model

```ruby
# BAD
class UsersController < ApplicationController 
  def index						
    @user = User.find(params[:id])						
    @recent_active_memberships = @user.find_recent_active_memberships 
  end						
end
						
class User < ActiveRecord::Base 
  has_many :memberships
						
  def find_recent_active_memberships 
    memberships.where(:active => true).order("last_active_on DESC")
  end 
end

# GOOD
class UsersController < ApplicationController 
  def index						
    @user = User.find(params[:id])						
    @recent_active_memberships = @user.memberships.only_active.recent
  end						
end

class User < ActiveRecord::Base 
  has_many :memberships
end
						
class Membership < ActiveRecord::Base 
  belongs_to :user						
  scope :only_active, where(:active => true)						
  scope :recent, order('last_active_on DESC') 
end
```
####Routing
* Try to use RESTful resource
* Use member / collection if you need to define more actions
* Use namespace to group the routes
* Use only, except to omit unnecessary routes
* Never use nested resources more than one level

```ruby
namespace :admin do
  resources :categories
  resources :entries
  resources :users
end

namespace :api do
  namespace :v1 do
    resources :entries, only: :index do
      resources :comments, only: :create
    end
  end
end
```
####Database
* If you get a lot of queries of one specific type, you could create an index for the query
* Try to do performance test because indexes can slow down update and insert statements
