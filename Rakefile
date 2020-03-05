namespace :greeting do

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
  
  
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end
end

namespace :db do
  desc 'migrate changes to your database'
  task :environment do
    require_relative './config/environment'
  end
  task :migrate => :environment do
    Student.create_table
  end
  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end
  desc 'drop into the Pry console'
  task :console => :environment do
    Pry.start
  end
end