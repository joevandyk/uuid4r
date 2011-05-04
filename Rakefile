require 'rubygems'
require 'rake/gempackagetask'

def gemspec
  @gemspec ||= begin
    gem_name =  File.basename(File.dirname(__FILE__))
    file = File.expand_path("../#{gem_name}.gemspec", __FILE__)
    eval(File.read(file), binding, file)
  end
end

Rake::GemPackageTask.new(gemspec) do |pkg|
  pkg.need_tar = true
end
task :gem => :gemspec

desc "Validates the gemspec"
task :gemspec do
  gemspec.validate
end
