# NOTE: If we then use the command, 'rake hello' in another terminal, we the return the 'puts' output below
# It's basically Ruby's version of the 'Makefile' / Crontab jobs

# NOTE: By adding a 'namespace', we can group our related Rake tasks together:
namespace :greeting do

  # NOTE: If we use 'rake -T', this will list the available 'Rake' tasks and their descriptions:
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end

end

# NOTE: We can use these individual tasks using the 'namespace:rake_task' syntax:
# rake greeting:hello
# rake greeting:hola

# NOTE: If you encounter this error:
# rake aborted!
# Gem::LoadError: You have already activated rake 10.4.2,
# but your Gemfile requires rake 10.4.0.
# Prepending `bundle exec` to your command may solve this.

# Then, use this command as the fix:
# bundle exec rake greeting:hello

# NOTE: We will now use the 'rake db:migrate' command to create a database table and migrate the code using
# a 'rake' task:

namespace :db do
  desc "migrate changes to your database"
  task migrate: :environment do
    Student.create_table
  end

  desc "seed the database with some dummy data"
  task seed: :environment do
    require_relative "./db/seeds"
  end
end

task :environment do
  require_relative "./config/environment"
end

desc "drop into the Pry console"
task console: :environment do
  Pry.start
end
