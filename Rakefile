
# -*- ruby -*-

require 'rubygems'

gem 'rdoc', '~> 3.12'

require 'rubygems/package_task'
require 'rake/testtask'
require 'rdoc/task'
require 'bundler/gem_tasks'

if RUBY_VERSION >= '1.9'
  begin
    gem 'psych'
  rescue Exception => e
    # it's okay, fall back on the bundled psych
  end
end

$:.push 'lib'

version = Proj4::VERSION

desc 'Test Proj4 interface'
Rake::TestTask.new(:test) do |t|
  t.test_files = FileList['test/**/*_tests.rb']
  t.verbose = !!ENV['VERBOSE_TESTS']
end

desc 'Build docs'
Rake::RDocTask.new do |t|
  t.title ="ffi-proj4 #{version}"
  t.main = 'README.rdoc'
  t.rdoc_dir = 'doc'
  t.rdoc_files.include('MIT-LICENSE', 'lib/**/*.rb')
end
