# encoding: utf-8
require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "nested_set"
    gem.summary = "An awesome nested set implementation for Active Record"
    gem.description = gem.summary
    gem.email = "info@collectiveidea.com"
    gem.homepage = "http://github.com/skyeagle/nested_set"
    gem.authors = ["Brandon Keepers", "Daniel Morrison"]
    gem.add_dependency "railties", ['>= 3.0.0']
    gem.add_dependency "activerecord", ['>= 3.0.0']
    gem.add_development_dependency "sqlite3-ruby"
    gem.add_development_dependency "actionpack", ['>= 3.0.0']
    gem.add_development_dependency "activesupport", ['>= 3.0.0']
    gem.add_development_dependency "bench_press", ['>= 0.3.1']
    gem.add_development_dependency "jeweler"
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/*_test.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "nested_set #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
