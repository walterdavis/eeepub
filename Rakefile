require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "walterdavis-eeepub"
    gem.summary = %Q{ePub generator}
    gem.description = %Q{EeePub is a Ruby ePub generator. This version is forked from the original https://github.com/jugyo/eeepub}
    gem.email = "waltd@wdstudio.com"
    gem.homepage = "http://github.com/walterdavis/eeepub"
    gem.authors = ["jugyo", "walterdavis"]
    gem.add_dependency "builder"
    gem.add_development_dependency "rspec"
    gem.add_development_dependency "rr"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

begin
  require 'yard'
  YARD::Rake::YardocTask.new
rescue LoadError
  task :yardoc do
    abort "YARD is not available. In order to run yardoc, you must: sudo gem install yard"
  end
end
