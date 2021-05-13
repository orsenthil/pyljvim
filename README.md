pyljvim: LiveJournal Plugin for VIM using Python.
=================================================

Historic
--------

This project is for *historic* interest only.

* This was Senthil Kumaran (author's) first open source code. Published a [vim plugin](https://www.vim.org/scripts/script.php?script_id=1724)
* Presented this plugin at a Thoughtwork's meetup attended by one person.
* The plugin and the experiment led to author contributing to [CPython Summer Of Code](https://mail.python.org/pipermail/python-dev/2007-June/073620.html).
* Overtime author became a [CPython Core Developer](https://github.com/python/cpython/commits?author=orsenthil) and maintainer of urllib module, involved more with Open Source Software and Community.

_Also, if you know how to read history, the above story is only a single thread. A lot happens._

Photos
------

![Presentation](art/presentation.jpg?raw=true "Presentation")

![Demo](art/demo.jpg?raw=true)

Project
-------

pyljvim helps to post to LiveJournal from vim itself. Users of vim having
python installed in their machines should find this facility useful.

Requirements:
-------------

Python, vim. It uses python's distutils for installation.

Installation:
-------------

Run: [sudo] python setup.py install.

Usage:
------

	0)Open Configfile.txt and provide the appropriate values.
	1)Open vim and type :LJTemplate extended or standard.
	2)Type :LJPost to post to the journal.

ChangeLog
=========

2010-11-20 O.R.Senthil Kumaran <orsenthil@gmail.com>
  * cleanup installation mechanism.
  * use distutils for installation.

2006-12-02  O.R.Senthil Kumaran <orsenthil@gmail.com>
  * Added Support for Windows.
  * Added Support for Proxy.
  * Added Support for ConfigFile.
2003-03-13  Wartan Hachaturow <wart@tepkom.ru>

	* Revision 0.0.1
	* Initial release

Manual Install and Configuration 
================================
	
	cd pyljvim
	cp syntax/lj.vim ~/.vim/syntax/
	cp macros/pyljpost.vim ~/.vim/macros/
	cp src/pyljpost.py /usr/local/bin/
	mkdir ~/.pyljvim
	mkdir ~/.pyljvim/templates
	cp templates/* ~/.pyljvim/templates
	echo "source ~/.vim/macros/pyljpost.vim" >> ~/.vimrc
	echo 'let g:pyljpost_path = "/usr/local/bin/pyljpost.py"' >> ~/.vimrc

Configuration variables
-----------------------

	g:pyljpost_path 	-- path to pyljpost.py, include the "pyljpost.py"
						itself.
	g:pyljpost_templates_path -- path to templates
	g:pyljpost_encoding -- your terminal encoding, from which to encode to utf-8

	g:pyljpost_username -- LJ Username
	g:pyljpost_password -- LJ Password
	^^^^^
	These two, if not setted, would be asked upon the post.

Usage
-----

Once the macros is sourced, two new functions become available,
LJTemplate and LJPost.

	LJTemplate [template-name]
		This function creates a new buffer, load template <template-name>
		(standart, if not given), creates the Date: field (if present in
		template), and goes to append mode.

Once you're ready with your immortal thoughts, goes 

	LJPost
		This function does the actual posting and deletes the buffer and the
		temporary file.

Of course, both functions can be mapped to Your-Beloved-Key.
You can easily create new templates (by writing new files at template_path),
with your own parameters. Full list of available parameters is in "extended"
template. Please note that "Subject" header is required in order to
post.

Authors
-------

* Senthil Kumaran <orsenthil@gmail.com>
* Wartan Hachaturow (Original Author) - <wart@tepkom.ru> 
