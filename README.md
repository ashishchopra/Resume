# Resume  

This started as just a simple place to store a markdown format of my resume,
and now it's turned into an easy way to host your resume using sinatra and
Heroku.  
  
It was then extended as a way to server your resume in multiple formats (LaTex, MarkDown, HTML, and soon PDF).
It also became a way to easily update and manager your github user page (user.github.com). Since this is powered by
MarkDown it also integrates well with GitHubs jobs search (http://github.com/blog/553-looking-for-a-job-let-github-help).
  
Lastly, it packages up your resume and info into an installable Rubygem. This was just a clever idea I saw suggested by
 Eric Davis and figured it would be cool to implement (http://groups.google.com/group/rails-business/msg/68cf8a890c0d4fc8?pli=1).
This focuses on making it as simple and easy to update and publish your resume as possible, while offering it in a variety of formats.  

Currently it is best to fork the project and override a few of the data files to customize the project for yourself.  
At the moment you need to override resume.yml and resume.md in the root directory with your own info.  

Contributions and ideas for the resume app are welcome, anything that makes the process simpler would be encouraged.  

# Authors

* Nathaniel "Nat" Welch (icco)
* Dan Mayer (danmayer)

## Installation

Basic resume in multiple formats on Heroku  
 1. Fork this project
 2. Install the gems (see the .gems file)
 3. To deploy to Heroku, also install the heroku gem, and intialize a heroku project
   * Run ` rake heroku:create name=batman-resume`
 4. type `rake run` or `ruby ./resume.rb` to run sinatra locally (http://localhost:4567). 
 5. Edit views/style.less to make your resume look pretty.
 6. Edit everything until it looks exactly how you like it. I suggest using Dingus for testing your Markdown (http://daringfireball.net/projects/markdown/dingus)
 7. `rake deploy:heroku` to push your resume to the internet on heroku (http://batman-resume.heroku.com).

OPTIONAL (GitHub Personal Page Deploy)  

* Deploy to github personal page (http://username.github.com)
  1. Add the github remote repo for your pages (like so `git remote add github git@github.com:user/user.github.com.git`)
  2. run `rake render_for_github`, which will render a index.html and style.css to your root directory
  3. run `git add index.html` and `git add style.css` and `git commit -a -m "adding github pages files"
  4. `rake deploy:github`
  5. Visit http://user.github.com

OPTIONAL (Publish personal resume gem)  
  1. Edit resume.yml to include your information. 
  1. Wait cause this is currently in progress.

## TODOs

* Make tests generic from resume
* Make the resume file not included in the git repo
* gem binary and assocatiated commands (http://groups.google.com/group/rails-business/msg/68cf8a890c0d4fc8?pli=1)
* fork me on github corner banner, can be displayed on html, but not rendered to other formats
* automatic conversion to various formats HTML, LaTeX, PDF, and allow downloading in any of the formats
  * http://github.com/rtomayko/rdiscount (current)
  * http://kramdown.rubyforge.org/
  * http://maruku.rubyforge.org/ (pdf support)
  * http://github.com/alphabetum/pandoc-ruby (many formats RTF docbook man ODF slides etc)
    * http://railsforum.com/viewtopic.php?id=35844
  * http://rtomayko.github.com/ronn/ (markdown to man page)
* simpler automated deploy to heroku (possibly with staging server)
* possibly merge with a resume generator which after filling out some info via forms or yaml can generate varios resumes in all formats
  * Users could submit templates / stylesheets allowing for differently formatted resumes
* standardize gem paths lib/resume/etc
* rake task that generates proper single use gemfile and executable
* make sinatra app depend on the gem
* move the configurable files to some more explainitory path than root. 
* better filenames for the downloaded resume in various formats (currently saves as latex and markdown)
* update readme to reflect changes, updates, and new goals of the project
* change render options to disable formats if not a sinatra version of the page, render static as an option perhaps
  * or you could have the resume root which is used for opening the site via the gem be used as the root url for all the formats

## License

resume.md is property of Nathaniel "Nat" Welch. You are welcome to use it as a
base structure for your resume, but don't forget, you are not him.

The rest of the code is licensed CC-GPL. Remember sharing is caring.
