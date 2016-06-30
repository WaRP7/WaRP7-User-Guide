namespace :build do
  desc 'prepare build'
  task :prebuild do
    Dir.mkdir 'media' unless Dir.exists? 'media'
  end

  desc 'Generate HTML outputs'
  task :html => :prebuild do
    puts "Converting to HTML..."
    `bundle exec asciidoctor User_Manual_WaRP7_HW_Linux.adoc`
    puts " -- HTML output at User_Manual_WaRP7_HW_Linux.html"
  end

  desc 'Generate PDF outputs'
  task :pdf => :prebuild do
    puts "Converting to PDF... (this one takes a while)"
    `bundle exec asciidoctor-pdf User_Manual_WaRP7_HW_Linux.adoc`
    puts " -- PDF  output at User_Manual_WaRP7_HW_Linux.pdf"
  end

end

desc 'Build all default formats'
task :build => [ "build:html", "build:pdf" ]
