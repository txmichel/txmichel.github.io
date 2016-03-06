require 'html-proofer'

# Build
desc 'Build for deployment (but do not deploy).'
task :build do
  jekyll("build --config _config.yml")
end

# Test
desc 'Check with htmlproofer if generatied HTML is valid and links are working.'
task :test do
HTML::Proofer.new(
  "./_site",
  # hacks to get html proof to pass links we wanted ignored
  href_swap: {
    'https://txmichel.github.io' => '', # canonical link in head
  }
).run
end

# launch jekyll
def jekyll(directives = '')
  sh 'bundle exec jekyll ' + directives
end
