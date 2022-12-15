# rake (task:) allows users to automate specific jobs
# desc allows us to describe what each rake command does.
desc 'outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
end

# namespace: allows users to group certain rakes or tasks together
# the namespace: below is grouped under :greeting
namespace :greeting do
desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

# Running rake commands: --> $ bundle exec rake greeting:hello

# migrate database by applying sql statements that alter the database
namespace :db do
  desc 'migrate changes to your database'
  task migrate: :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end

# Sets up an environment task for migrating database
task :environment do
  require_relative './config/environment'
end
# $ bundle exec rake db:migrate

desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end