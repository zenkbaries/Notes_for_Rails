# SimpleForm and Bootstrap

Add `config.input_class = "form-control"` to `config/initializers/simple_form.rb` like this:

```ruby
# Use this setup block to configure all options available in SimpleForm.
SimpleForm.setup do |config|
  config.input_class = "form-control"

  # Wrappers are used by the form builder to generate a
  # complete input. You can remove any component from the

  # a whole bunch more stuff here .....
end

```
===============================================================================

  Be sure to have a copy of the Bootstrap stylesheet available on your
  application, you can get it on http://getbootstrap.com/.

  Inside your views, use the 'simple_form_for' with one of the Bootstrap form
  classes, '.form-horizontal' or '.form-inline', as the following:

    = simple_form_for(@user, html: { class: 'form-horizontal' }) do |form|

===============================================================================
```
