require 'rake'
require 'redis'
require 'mongoid'
require 'mongoid-locker'
require 'telegram/bot'
require 'sucker_punch'
require 'active_support/inflector'

require File.dirname(__FILE__) + '/config/init.rb'
Dir[File.dirname(__FILE__) + '/lib/mimin_tulul_bot/*/*.rb'].each{ |file| require file }
Dir[File.dirname(__FILE__) + '/lib/mimin_tulul_bot/**/*.rb'].each{ |file| require file }

$redis = Redis.new
Mongoid.load!(File.dirname(__FILE__) + '/config/mongoid.yml', :production)

namespace :mimin_tulul do
  task :start do
    MiminTululBot.start
  end
end

task default: 'mimin_tulul:start'
