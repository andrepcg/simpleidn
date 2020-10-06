require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec)

task :default => :spec

namespace :mapping do
  task :download do
    sh "curl https://www.unicode.org/Public/idna/latest/IdnaMappingTable.txt > tables/IdnaMappingTable.txt"
  end

  task :update do
    ruby "tables/generate_mapping_table.rb tables/IdnaMappingTable.txt > lib/simpleidn/uts46mapping.rb"
  end
end

