require 'rdiscount'
require 'erb'

desc "build docs"
task :docs do
  mdown = RDiscount.new(ERB.new(File.open('doc/doc.md','r').read).result(binding), :smart).to_html
  wrapper = File.open('doc/doc_wrapper.erb','r').read
  mdown   = File.open('index.html','w+') do |f|
    f.write ERB.new(wrapper).result(binding)
  end  
end