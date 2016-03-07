require 'html-proofer'

# Build
desc 'Build for deployment (but do not deploy).'
task :build do
  jekyll("build --config _config.yml")
end

# Test
desc 'Check with htmlproofer if generatied HTML is valid and links are working.'
task :test do
HTMLProofer.check_directories( ["./_site"], { :url_swap => { "https://txmichel.github.io" => "" } } ).run
end

# launch jekyll
def jekyll(directives = '')
  sh 'bundle exec jekyll ' + directives
end
