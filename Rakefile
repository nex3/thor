require 'rubygems'
require 'rake/gempackagetask'
require 'rubygems/specification'
require 'spec/rake/spectask'
require 'date'

GEM = "thor"
GEM_VERSION = "0.9.2"
AUTHOR = "Yehuda Katz"
EMAIL = "wycats@gmail.com"
HOMEPAGE = "http://yehudakatz.com"
SUMMARY = "A gem that maps options to a class"

spec = Gem::Specification.new do |s|
  s.name = GEM
  s.version = GEM_VERSION
  s.platform = Gem::Platform::RUBY
  s.has_rdoc = true
  s.extra_rdoc_files = ["README.markdown", "LICENSE"]
  s.summary = SUMMARY
  s.description = s.summary
  s.author = AUTHOR
  s.email = EMAIL
  s.homepage = HOMEPAGE
    
  s.require_path = 'lib'
  s.autorequire = GEM
  s.bindir = "bin"
  s.executables = %w( thor )
  s.files = %w(LICENSE README.markdown Rakefile) + Dir.glob("{bin,lib,specs}/**/*")
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.gem_spec = spec
end

task :default => :install
desc "install the gem locally"
task :install => [:package] do
  sh %{sudo gem install pkg/#{GEM}-#{GEM_VERSION} --no-rdoc --no-ri --no-update-sources}
end