# to run the file in the terminal type rake hello
# We can also use rake -T to view a list of availble Rake tasks and their description:
# To use rake -T first define a rake task description using the(desc)key-word followed by your 'description': run rake -T.

# using rake console to interact with our class and database wothout having to run our entire program.
# building to load up a pry console for us.
# making the console dependent on the environment task so that the student class and the database connection load first.
desc 'creating our environment task'
task :environment do
  require_relative './config/environment'
end

task console: :environment do
  Pry.start
end

desc 'outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
end

namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts 'hola de Rake!'
  end

end

namespace :db do
  desc 'migrate changes to your database'
  # craeting  task dependancy telling rake to run environment task before running migrate.
  task migrate: :environment do
    Student.create_table
  end

  desc 'seed  the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end



