require 'rake/testtask'
require "bundler/gem_tasks"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# # My own (complicated) solution
# desc 'List all files'
# task :inventory do
#   Find.find('.') do |path|
#     next if path == '.'
#     if File.directory?(path) && File.basename(path).start_with?('.')
#       Find.prune
#     elsif File.file?(path)
#       puts path unless File.basename(path).start_with?('.')
#     end
#   end
# end

desc 'List all files'
task :inventory do
  Find.find('.') do |path|
    next if path.include?('/.')
    puts path if File.file?(path)
  end
end
