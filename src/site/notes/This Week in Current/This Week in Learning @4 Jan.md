---
{
  "dg-publish": true,
  "permalink": "/this-week-in-current/this-week-in-learning-4-jan/",
}
---

Date 01/04/2026

In this week mostly I've gone through the whole codebase and it's build process
across different library built over the kernel module and subsystem's, the main reason for this was to
setup the clangd lsp for the codebase, I guess due to cross compilation I faced various issues
on generating indexes for the entire codebase, then I went through understanding how we've created
the makefile how it works also got to learn it's time-stamp based rules,
also take one sample directory btw the compile_commands.json files generated using bear -- make command
was huge consisting of over 11000 of line's
and identify where does it takes library into
account while generating the clangd indexes, identified the problem that the dynamic linking
happening and the compile_commands.json file generated have this issue,
include the files which are linked to linux source code, various
files are linked through it, I just replaces them with the actual file, the augment code
helped me a lot to generated a python program to unlink and replace it's actual file, I also
tried to sed various path's which are relative to the kernel module but actually not accordingly to
the codebase we've defined, so relative path's are giving out the error \[clangd error -320001 invalid ast]
Utilising the sed command's also helped me a lot to solve this issue replacing all the ./ relative path's to
actual path's and also the cross compilation fixes since the driver code's for any open source project
built over the aarch arm based architecture so on x86 64 bit it's not possible to build, due to which many
header file's are giving out the error, actually the build happened with the custom environment on remote
docker
also the platform is also different like abi flag's are there,
I have also got to know the a bit of optimisation happening behind the gcc compilation since the
clangd doesn't support for the gcc compiler flags, like tree optimisation and follow's different way's
since it's a llvm based tools, I guess we've to remove it. Hence I've also added the -sysdir for the custom
gcc
for arm based, the query-driver is also added with the clangd lsp setting in the neovim, gone through the
assigning the thread's associated with the building the lsp for clangd, After revisiting the lsp logs' many
time
I found that the my custom lsp setting is not captured by the mason in nvim, so I added fix for that and
runned the lsp
using -j=40.
I accidently deleted the tmux configuration files.tmux.conf files after created or sourced it. I don't find
anywhere on my machine and unluckily
I don't have a backup for it, so it just missed out from github also due to it's placement in home directory,
so I've
to rewrited it again which was a little painful experience
My Neovim setup also got broken up this week due to major changes in the tree-sitter update from transferring
master branch
to main branch.
