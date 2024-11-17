require "rake/testtask"
require 'find'
require "bundler/gem_tasks"
desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :test do
  sh 'ruby ./test/todolist_project_test.rb'
end

desc 'Run tests'
task :default => :test


Rake::TestTask.new(:test) do |t| #TestTask is a Rake-specific class that provides
  #support for writing task responsible for running a list of tests. 
  #Instantiating TestTask creates a task that runs a set of tests
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names
    puts name if File.file?(name)
  end
end