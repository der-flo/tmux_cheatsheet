task :default => [:pdf]
task :pdf do
  require 'bundler/setup'
  require 'redcarpet'
  require 'pdfkit'
  cwd = File.dirname(__FILE__)
  markdown = File.read(File.join(cwd, 'README.md'))
  renderer = Redcarpet::Markdown.new(Redcarpet::Render::HTML, :tables => true)
  html = renderer.render(markdown)
  pdfkit = PDFKit.new(html, :page_size => 'A4', :margin_left => '5mm',
                      :margin_right => '5mm', :margin_top => '5mm',
                      :margin_bottom => '5mm')
  pdfkit.stylesheets << File.join(cwd, 'style.css')
  pdfkit.to_file(File.join(cwd, 'cheatsheet.pdf'))
end

