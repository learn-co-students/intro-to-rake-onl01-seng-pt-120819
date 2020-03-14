namespace :greeting do
  desc 'ouptus hello to the terminal'
  task :hello do 
    puts "hello from Rake!" #should print out 'hello from Rake!'
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!" #should print out 'hola de Rake!'
  end
end

namespace :db do
  desc 'gives our task access to this file'
  task :environment do
    require_relative './config/environment' #invokes the :environment task as a dependency
  end
  
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table #create the students table in the database
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb' #seeds the database with dummy data from a seed file
  end
end

desc 'drop into the Pry console' #this task can remain dependent on our environment task so that the Student class and the database connection load first
task :console => :environment do
  Pry.start #define a task that starts up the Pry console  
end
