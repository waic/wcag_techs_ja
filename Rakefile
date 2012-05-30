# -*- coding: utf-8; -*-
#
# Rakefile for WCAG 2.0 Technics transration to ja
#

HTML_DIR = './html_ja'
XML_DIR = './xml_ja'; directory XML_DIR

HTMLS = Dir.glob( "#{HTML_DIR}/[A-Z]*[0-9]*.html" ).sort
XMLS = HTMLS.map{|a| a.gsub( /html/, 'xml' )}
XMLS.each_with_index do |x, i|
	file x => HTMLS[i] do |t|
		sh "bundle exec bin/html2xml #{t.prerequisites.join ' '} #{XML_DIR} > #{t.name}"
	end
end

task :default => :html2xml

desc 'convert HTML to XML'
task :html2xml => XMLS

desc 'clean up'
task :clean do |t|
	rm XMLS
end
