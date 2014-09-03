---
layout: post
title: "LaTeXTools for sublime"
date: 2014-09-01 21:37:08 +0800
comments: true
categories: 
---

#Install

##Install sublime package control

for sublime 3

>The console is accessed via the ctrl+` shortcut or the View > Show Console menu. Once open, paste the appropriate Python code for your version of Sublime Text into the console.


>import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

##Get LaTeXTools

>use package control (ctrl+shift+p) and look for LaTeXTools.

>If you are installing LaTeXTools for the first time, you need to create a configuration file, LaTeXTools.sublime-settings, in your User directory (off the Packages) directory. To do so, open the command palette from the Tools menu, search for "LaTeXTools: Reconfigure and migrate settings," and hit Return. That's it! See the Settings section for details on configuration options.

##Configuration

>add the SumatraPDF directory to your PATH 

>On Windows, we should set up inverse search in Sumatra PDF. open a command-line console (run cmd.exe), and issue the following command:

>sumatrapdf.exe -inverse-search "\"C:\Program Files\Sublime Text 2\sublime_text.exe\" \"%f:%l\""

>edit the file LaTeX.sublime-settings in the User directory to make sure that the configuration reflects your preferred TeX distribution. Open the file and scroll down to the section titled "Platform settings." Look at the block for your OS, namely windows. Within that block, verify that the texpath setting is correct; for MiKTeX, you can leave this empty, i.e., "". If you do specify a path, note that it must include the system path variable, i.e., $PATH (this syntax seems to be OK). Also verify that the distro setting is correct: the possible values are "miktex" and "texlive".


##Keybindings

>Most LaTeXTools facilities are triggered using Ctrl+l (Windows, Linux)

>Compilation uses the standard ST "build" keybinding, i.e. Ctrl-b on Windows and Linux

>For example: to jump to the point in the PDF file corresponding to the current cursor position, use Ctrl-l, j: that is, hit Ctrl-l, then release both the Ctrl and the l keys, and quickly type the j key (OS X users: replace Ctrl with Cmd). To wrap the selected text in an \emph{} command, use Ctrl-l, Ctrl-e: that is, hit Ctrl-l, release both keys, then hit Ctrl-e

>Ctrl-l (Cmd-l on OS X) is the standard ST keybinding for "expand selection to line"; this is remapped to Ctrl-l,Ctrl-l (Cmd-l,Cmd-l on OS X). This is the only standard ST keybinding that is affected by the plugin---an advantage of new-style keybindings.