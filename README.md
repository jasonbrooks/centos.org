This is a repository for a yet-to-be-announced project. Consider
everything here company confidential until the announcement.


The site is built with *nanoc* and *Bootstrap 3*.

  * http://www.nanoc.ws
  * http://getbootstrap.com

We use haml for templates where it makes sense and mostly markdown for
content.


Required Gems:

  * nanoc
  * cri
  * compass
  * haml
  * nokogiri // available from Fedora (EPEL?) repository
  * kramdown 
  * pry
  * rainpress
  * rubypants
  * sass
  * susy
  * systemu
  * asciidoc // also requires the asciidoc package
  * adsf // if using 'nanoc view' command

May be in RPM:

  * ruby
  * asciidoc
  * nokogiri

Installing on Fedora 20:

<pre>
sudo yum install ruby asciidoc nokogiri
gem install nanoc adsf cri compass haml kramdown pry rainpress rubypants sass susy systemu
</pre>
