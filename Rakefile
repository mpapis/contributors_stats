task :test do
  $LOAD_PATH.unshift('lib', 'test')
  Dir.glob('./test/**/*_test.rb') { |f| require f }
end

task :yard do
  at_exit {
    require 'yard'
    require 'yard/cli/yardoc'
    require 'yard/cli/stats'
    YARD::CLI::Yardoc.new.run("--no-stats", "lib/**/*.rb")
    YARD::CLI::Stats.new.run("--list-undoc", "--compact")
  }
end

# reversed order for at_exit
task :default => [:yard, :test]

task :example_data do
  require "example_data"
  example = ExampleData.new
  example.parse_org(  example.url_builder("orgs/railsinstaller/repos") )
  example.parse_repo( example.url_builder("repos/rvm/pluginator/contributors") )
  example.parse_repo( example.url_builder("repos/mpapis/rubygems-bundler/contributors") )
end
