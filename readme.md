# xbuild copy bug

Clone this repo and run the following

`xbuild SlnA.sln /t:Rebuild /p:OutputPath=/Users/jonathan/Projects/Common/buildoutput/outputA /p:Configuration=Release`

Inspect the folder  `buildoutput/outputA` and notice `ProjA.dll` & `Common.dll`. Then run the below:

`xbuild SlnB.sln /t:Rebuild /p:OutputPath=/Users/jonathan/Projects/Common/buildoutput/outputB /p:Configuration=Release`

Inspect the folder `buildoutput/outputB` and notice `ProjB.dll` & `Common.dll`. Then inspect `buildoutput/outputA` and you'll see `Common.dll` has gone.  If you inspect the `xbuild` output from `SlnB` then you'll see an entry showing it delete `/buildoutput/ouputA/Common.dll`