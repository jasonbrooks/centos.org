
# a test converion of this site to jekyll

## test it in a container

```
sudo podman run -d --name centos-jekyll -p 4000:4000 -v $(pwd):/srv/jekyll:Z jekyll/jekyll jekyll serve --watch
```

## todo

* Need to figure out `media.erb`. 
* Also, the layout is html, the jekyll-haml gem is handling haml conversion for a few haml-based pages, like the download page, but it wasn't working right for the layouts. I don't know if that's a problem.


***



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

## Installing on CentOS 7 as well as F19/20/21:

<pre>
sudo yum install ruby asciidoc rubygem-bundler make gcc ruby-devel zlib-devel zlib gcc-c++
bundle install
</pre>


## Using a built container (all platforms):
Assuming that you have this git repository cloned under /opt/data/git/centos.org : 
```
sudo docker pull registry.centos.org/arrfab/nanoc:latest # Download the container
sudo docker run --rm -v /opt/data/git/centos.org/:/nanoc/:Z registry.centos.org/arrfab/nanoc:latest
```
Please note that it also works with Podman, so no need to install Docker anymore ! :

```
sudo yum install -y podman
sudo podman run --rm -v /opt/data/git/centos.org/:/nanoc/:Z registry.centos.org/arrfab/nanoc:latest
```


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
