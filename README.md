#Spectral Workbench

Copyright 2011-2015 Public Lab
publiclab.org | spectralworkbench.org

Spectral Workbench is an open-source tool to perform low-cost spectral analysis and to share those results online. It consists of a Ruby on Rails web application for publishing, archiving, discussing, and analyzing spectra online -- running at http://spectralworkbench.org

Read about how to build and use your own spectrometer with this software here: http://publiclab.org/wiki/spectrometer

##License

Spectral Workbench is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Spectral Workbench is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with Spectral Workbench.  If not, see <http://www.gnu.org/licenses/>.

##Installation

The app now runs on Ruby 1.9.3 up to Ruby 2.1.2 (preferred), and Rails 3.2.x, and uses Bundler for gem management and Bower for static asset management.  

###Prerequisites:

Recommended; for an Ubuntu/Debian system. Varies slightly for mac/fedora/etc

Install a database, if necessary:

`sudo apt-get install mysql-server`

RMagick dependencies are required for processing uploaded spectrum images: `apt-get install imagemagick ruby-rmagick libmagickwand-dev libmagick++-dev`

* On Fedora/centOs: `yum install ImageMagick-devel`
* On mac, you can use Homebrew: `brew install imagemagick`

Install rvm for Ruby management (http://rvm.io)

`curl -L https://get.rvm.io | bash -s stable`

**Note:** At this point during the process, you may want to log out and log back in, or open a new terminal window; RVM will then properly load in your environment. 

**Ubuntu users:** You may need to enable `Run command as a login shell` in Ubuntu's Terminal, under Profile Preferences > Title and Command. Then close the terminal and reopen it.

Then, use RVM to install version 2.1.2 of Ruby:

`rvm install 2.1.2`

You'll also need **bower** which is available through NPM. To install NPM, you can run:

`sudo apt-get install npm`

However, on Ubuntu, you may need to also install the `nodejs-legacy` package, as due to a naming collision, some versions of Ubuntu already have an unrelated package called `node`. To do this, run:

`sudo apt-get install nodejs-legacy`

Once NPM is installed, you should be able to run:

`sudo npm install -g bower`


###Installation steps:

1. Download a copy of the source with `git clone https://github.com/publiclab/spectral-workbench.git` 
2. Install gems with `bundle install` from the rails root folder. You may need to run `bundle update` if you have older gems in your environment.
3. Copy and configure config/database.yml from config/database.yml.example, using a new empty databse you've created
4. Initialize database with `bundle exec rake db:setup`
5. Install static assets (like external javascript libraries, fonts) with `bower install` 
6. Start rails with `bundle exec passenger start` from the Rails root and open http://localhost:3000 in a web browser. (For some, just `passenger start` will work; adding `bundle exec` ensures you're using the version of passenger you just installed with Bundler.)

Sign in instructions:

*  Create a account at PublicLab.org and use that username to log in.
*  Then you will be redirected to publiclab.org to "approve" a use of the openid identity.
*  Note that this applies for development environment as well. 

##Bugs and support

To report bugs and request features, please use the GitHub issue tracker provided at http://github.com/publiclab/spectral-workbench/issues 

For additional support, join the Public Laboratory website and mailing list at http://publiclab.org/lists or for urgent requests, email web@publiclab.org

For questions related to the use of this software and your open source spectrometer, the same page links to the "plots-spectrometry" group. 

##Developers

Development is occurring at https://github.com/publiclab/spectral-workbench/; please fork and submit pull requests; for more guidelines on contributing to Public Lab projects, see http://publiclab.org/wiki/contributing-to-public-lab-software

If you're a developer, consider joining the Public Lab developer list, also at http://publiclab.org/wiki/developers
