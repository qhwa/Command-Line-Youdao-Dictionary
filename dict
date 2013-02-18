#!/usr/bin/env ruby
# encoding: utf-8

require 'net/http'
require 'rexml/document'

class YoudaoDict

  def translate(word)
    if word && !word.empty?
      @word = word
      parse Net::HTTP.get( "dict.youdao.com", "/fsearch?q=#{word}" )
    end
  end

  def parse(src)
    xml = REXML::Document.new(src)
    parse_phonetic_symbol xml

    __ "辞典翻译: #{@word}", "="
    parse_dict_trans      xml

    __ "网络释义", "="
    parse_web_trans       xml
  end

  protected
    # 音标
    def parse_phonetic_symbol( xml )
      xml.each_node('//phonetic-symbol') do |node|
        if node.text
          indent
          print @word
          puts " [#{node.text}]".cyan
        end
      end
    end

    # 辞典
    def parse_dict_trans( xml )
      xml.each_node('//translation/content') do |node|
        indent
        puts node.text.green
      end
    end

    # 网络释义
    def parse_web_trans( xml )
      xml.each_node('//yodao-web-dict/web-translation') do |node|
        __ node.first_node('key/').text
        node.each_node('trans/value/') do |val|
          indent
          puts val.text
        end
      end
    end

  private
    def __(t, pad='-', len=30 )
      puts " #{t} ".center(len, pad)
    end

    def indent(idt=2)
      print " " * idt
    end

end

##################################
######## Helper classes ##########
##################################

module REXML
  # REXML::Element patch
  # for better readablitiy
  class Element
    def each_node(path, &block); XPath.each(self, path, &block); end
    def first_node(path); XPath.first(self, path); end
  end
end

class String
  COLORS = %w(black red green yellow blue magenta cyan white)
  COLORS.each_with_index do |color, idx|
    define_method color do
      "\e[3#{idx}m" << self.to_s << "\e[0m"
    end

    define_method "#{color}_bg" do
      "\e[4#{idx}m" << self.to_s << "\e[0m"
    end
  end
end

## script entrace
YoudaoDict.new.translate(ARGV.join ' ') if __FILE__ == $0
