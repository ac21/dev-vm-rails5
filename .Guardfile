

group :gem do
  guard :rspec, cmd: 'bundle exec rspec' do
    watch(%r{^spec/.+_spec\.rb$})
    watch(%r{^lib/(.+)\.rb$})       { |m| "spec/#{m[1]}_spec.rb" }
  end
end

group :rails do
  guard :rspec, cmd: 'bundle exec rspec' do
    watch(%r{^spec/.+_spec\.rb$})
    watch(%r{^lib/(.+)\.rb$})       { |m| "spec/#{m[1]}_spec.rb" }
    watch(%r{^app/(.+)\.rb$})       { |m| "spec/#{m[1]}_spec.rb" }
  end
end
