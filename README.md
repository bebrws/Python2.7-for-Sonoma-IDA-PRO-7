# Run Python 2.7 on OSX Sonoma

I found it impossible ()I am sure with time it would be possible..) to build Python 2.7 for OSX Sonoma. Tried pyenv. Tried the official x86 installer on my M3.
Nothing worked.

I took the official Python 2.7 installer and started decompressing files out of the different pkgs.

I came up with this framework which I fixed up.

If the `Versions/2.7/bin/` dir is in the PATH then pip2.7 will actually install python2.7 packages and python2.7 works great.

A number of these scripts are just python scripts though and have an absolute path hashbang at the top so go a find and replace across all files in `/bin` and make sure that 
`#!/Users/bbarrows/Python27.framework/Versions/2.7/bin/python2.7`
is pointed to where you place this framework

If I cared more I could probably just have a relative path to python2.7 here? You will figure it out if you are trying to use this.

# IDA Pro 7 - Python 2.7 support

I did this all to get Python 2.7 working in Ida Pro 7.0 on OSX Sonoma so...

To fix IDA and give it python 2.7 on newer OSX which doenst have python 2.7
Cp this dir to $HOME/Python27.framework/

install_name_tool -change "/System/Library/Frameworks/Python.framework/Versions/2.7/Python" "$HOME/Python27.framework/Versions/2.7/Python" "/Applications/IDA Pro 7.0/ida.app/Contents/MacOS/Archive/plugins/python64.dylib"
install_name_tool -change "/System/Library/Frameworks/Python.framework/Versions/2.7/Python" "$HOME/Python27.framework/Versions/2.7/Python" "/Applications/IDA Pro 7.0/ida64.app/Contents/MacOS/plugins/python64.dylib"
