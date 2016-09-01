namespace :build do
  desc 'prepare build'
  task :prebuild do
    Dir.mkdir 'media' unless Dir.exists? 'media'
  end

  desc 'Generate HTML outputs'
  task :html => :prebuild do
    puts "Converting to HTML..."
    `bundle exec asciidoctor User_Guide_Manual.adoc`
    puts " -- HTML output at User_Guide_Manual.html"
  end

  desc 'Generate PDF outputs'
  task :pdf => :prebuild do
    puts "Converting to PDF... (this one takes a while)"
    `bundle exec asciidoctor-pdf User_Guide_Manual.adoc`
    puts " -- PDF  output at User_Guide_Manual.pdf"
  end

end

desc 'Build all default formats'
task :build => [ "build:html", "build:pdf" ]
