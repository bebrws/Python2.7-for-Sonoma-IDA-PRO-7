To fix IDA and give it python 2.7 on newer OSX which doenst have python 2.7
Cp this dir to /Users/bbarrows/Python27.framework/

install_name_tool -change "/System/Library/Frameworks/Python.framework/Versions/2.7/Python" "/Users/bbarrows/Python27.framework/Versions/2.7/Python" ida.app/Contents/MacOS/Archive/plugins/python64.dylib
install_name_tool -change "/System/Library/Frameworks/Python.framework/Versions/2.7/Python" "/Users/bbarrows/Python27.framework/Versions/2.7/Python" "/Applications/IDA Pro 7.0/ida64.app/Contents/MacOS/plugins/python64.dylib"
