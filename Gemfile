source 'https://rubygems.org'
git_source(:github) { |repo| "https://github.com/#{repo}.git" }

ruby '3.0.0'
gem 'rails', '~> 6.1.4', '>= 6.1.4.1'
gem 'puma', '~> 5.0'
gem 'bootsnap', '>= 1.4.4', require: false
gem 'pg', '~> 1.2', '>= 1.2.3'  
gem 'bcrypt', '~> 3.1', '>= 3.1.16'
gem 'jwt', '~> 2.3'
gem 'simple_command', '~> 0.1.0'

group :development, :test do
  gem 'byebug', platforms: [:mri, :mingw, :x64_mingw]
end

group :development do
  gem 'listen', '~> 3.3'
  gem 'spring'
end

gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
