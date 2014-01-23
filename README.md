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

Installing on Fedora 19/20:
Packages will come later for the dependencies.
<pre>
sudo yum install ruby asciidoc nokogiri
gem install nanoc adsf cri compass haml kramdown pry rainpress rubypants sass susy systemu guard-nanoc
</pre>


#Site Layout
  * Template and menu files live in /layouts
  * Markdown, erb and processed text files live in /content
  * Static site content such as images and javascript live in /static
  * The /lib directory contains nanoc helper files used to process the site
  * Compiled site content exists in /output

#Building the site
  * Run 'nanoc' to compile assemble the static site. files from /static, /content, and /layouts will be combined.
  * You may view the site with 'nanoc view' and then pointing your browser at http://127.0.0.1:3000

You may compile and view the site live as you make changes using the guard module. To do this, run 'guard init' at the root of the site. 
This will create a watch file that will serve as list for what files the guard module will keep an eye on. Changes to these files will trigger an automatic rebuild of the site.
Next run 'nanoc view &', followed by 'guard'
Now in another terminal, you may make changes to the website content, and it will rebuild as you touch files. 


#Deploying the site
Simply run 'nanoc deploy --target=' where the target value is either prod1 or prod2. These targets are defined in the nanoc.yaml file. 
