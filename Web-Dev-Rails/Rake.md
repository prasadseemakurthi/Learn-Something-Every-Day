# Rake 
Rake is a utility for build automation, based on unix utility make. It is a part of the rails command line.

`Rakefile` and `.rake` files to build lists of tasks. 

## Writing Rake Tasks
In rails, `rails g task` generates rake files.

```ruby
namespace :db do # not required
  desc "some description for task"
  task task_name: [:prerequisite_tasks, :other_tasks_run_before] do
    # Any ruby code
  end
end
```
Creates a rake task that can be called with `$ bin/rake db:task_name`

```ruby 
task :task_name, [:arg_1, :arg_2] => [:pre_1, :pre_2] do |t, args|
  # code
end
```
Creates a rake task called by `$ bin/rake task_name[1, 'x']` which passes 1 and x as parameters. (zsh you need to escape square brackets)

## In Rails
- `rake routes` lists all defined routes.
- `rake test` runs tests
- `rake db:migrate`, `rake db:version`, reset, up, down, redo are tasks that automate migration management.