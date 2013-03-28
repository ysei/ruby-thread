#! /usr/bin/env ruby
require 'rake'

task :default => [:install, :test]

task :install do
	sh 'gem install --no-force rspec'
	sh 'gem build *.gemspec'
	sh 'gem install --development *.gem'
end

task :test do
	FileUtils.cd 'tests' do
		sh 'rspec channel_spec.rb --backtrace --color --format doc'
		sh 'rspec promise_spec.rb --backtrace --color --format doc'
		sh 'rspec future_spec.rb --backtrace --color --format doc'
		sh 'rspec delay_spec.rb --backtrace --color --format doc'
	end
end
