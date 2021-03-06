Sublime Text: x86 Assembly Syntax Definition (AT&T/GAS)
==========================

**This is the greatest syntax definition of All Time**

Sublime Text syntax definition for x86 assembly (GAS/AT&T syntax)

**I do not have plans to support any other syntax type (such as Intel). Sufficient packages already exist.**

Covers a lot of instructions for a lot of different cpuid flags, even if you don't have them.

Purpose:  I couldn't find any good ones online, so I made one myself for my ECE391 class at UIUC. None of the ones I did find did a good job highlighting the right instructions. This is not to say that this definition is perfect, but for the purposes of your college level systems programming class, it will do just fine.

I have included some test files in the 'test/' directory of this package. Look around if you like. I even included a gdb disas dump, which I think is a good test for efficacy.

**Ports to other editors**

This has become somewhat of a parent-project for various ports, so here's a list of links to ports I've made:
- [Atom](https://github.com/calculuswhiz/atom-GAS-x86_64-highlighter). Same highlighting features. It was a direct JSON->CSON conversion. No snippets.
- [Vim](https://github.com/calculuswhiz/vim-GAS-x86_64-highlighter). Probably same highlighting features. Regex syntax was kind of hard to nail down. Might extend with snippet-like features later.
- [Gedit](https://github.com/calculuswhiz/gedit-GAS-x86_64-highlighter). It's a bit of a weaker port, but it should look reasonably close. It was a bit frustrating to write, with so little documentation around.
- More perhaps to come later. I currently have no plans to port to emacs. Writing major modes seems like a major pain compared to how easy it is for vim. In fact, porting to vim pretty much converted me over to vim as my favorite command line editor. Let's also not speak about Notepad++, which is even less capable.

**Installation (Any platform):**
- Get sublime_text.
- Install "Package Control" : https://sublime.wbond.net/installation#st2
    - Pay ye mind to the 2 or 3. Follow the directions closely! `` ` `` is a backtick, not an apostrophe.
- In your sublime window menu, go to Preferences>Package Control and type "Install".
- Type "gasx" to find the package.
- This has the advantage of automatic updates if a bug is caught.

Masochistic method (manual install):
- Download the contents of this repo.
- Extract/copy/Whatever-I-Don't-Care all files into your 'Packages' directory.
    - This is easily accessible from Preferences>Browse Packages...
    - You *could* always just `git pull` in the 'Packages' directory.
- This method is not for people new to ST. Trust me. I know from experience. The reason there are so many words here is because people can't figure out how to install Package Control.
- If all this has failed, you're on your own. Good luck.

Sublime should automatically take care of the syntax highlighting, so there's no need to restart.

If you feel the directions are unclear, please tell me. Or tell Dennis, so we can make fun of you later.

Pull requests and/or bug reports are always welcome.

Features (Secret Q/A):
=========
- Can't remember a system call number? Start with your architecture (`32`/`64`) and type the call you want (e.g. `mmap`, `read`), press tab/enter, and let the autocomplete do the rest.
    - E.g. I want to use mmap on x64. I type `64mmap`, enter, and it expands to `#define SYS_MMAP    $9`.
- Can't remember displacement syntax? Just start typing "displace" and select the helper option in autocomplete. Then tab through the arguments.
- How do I start a standalone assembly program? Type `skel32` or `skel64`, autocomplete. Compiles with `gcc -nostdlib`.
- How do I set up a stack frame for calling a function? Type `newframe32` or `newframe64`.

Demo on gdb disassembly log:
![Demo](https://raw.githubusercontent.com/calculuswhiz/Assembly-Syntax-Definition/master/screencap/gdb_demo.png)
