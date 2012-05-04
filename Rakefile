require 'rubygems'
require 'bundler'
require 'logger'
require 'fileutils'
require 'pathname'

Bundler.require

namespace :assets do
  desc 'Compile assets'
  task :compile do
    # compile javascript
    javascript = sprockets['application.js']
    compiled_js = Pathname.new(File.join('public', 'js', 'application.js'))
    FileUtils.mkdir_p compiled_js.dirname
    javascript.write_to(compiled_js)

    # compile css
    css = sprockets['application.css']
    compiled_css = Pathname.new(File.join('public', 'css', 'application.css'))
    FileUtils.mkdir_p compiled_css.dirname
    css.write_to(compiled_css)
  end
end

def sprockets
  sprockets = Sprockets::Environment.new(File.dirname(__FILE__)) { |env| env.logger = Logger.new(STDOUT) }
  sprockets.append_path File.join('assets', 'javascripts')
  sprockets.append_path File.join('assets', 'stylesheets')
  sprockets.css_compressor = YUI::CssCompressor.new
  sprockets.js_compressor  = Uglifier.new(:mangle => true)
  sprockets
end