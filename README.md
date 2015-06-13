# *Just Sub It*

Status: Early alpha, still a few rough edges.

A one click VLC extension based around VLSub. ( Well, two clicks for now, working on it. )
The extension would once activated automagically search for subtitles, pick the best four, download and load them into vlc
and then close itself. If the first selected doesn't fit, just press 'S' and try the next already loaded subtitle.

###TODO:
* Currently searches for subtitles in all languages, should only use ones defined in VLC subtitles lang preferences, 
or english if none were defined. 
* Make UI more lean, 90% of it is useless now. However, it is a little fun seeing the work you are spared. 
Consider if there are any significant speed benefits.
* If we keep the UI, we should fix the annoying ui bug where an extra row is added to the subtitles after a download, 
we inherited this bug from the original extension. 
* Haven't finished one important heuristic of word similarity. Simple strategy would be to :
** Replace non alphanumeric with whitespaces, split by whitespaces, and intersect the two resulting set, form 
subtitle name and file name. This would give advantages to group names/
* The names of the different subtitles loaded into VLC are currently the same, no reason for that, easy fix.
  This will however, probably, affect how many files are being saved to disk. Do we want all of them or just one ? 
* Load the best subtitle in the cyclically correct order. Prefably make sure the first time I try to switch the subtitle, 
I don't reach the disable subtitles mode, but go to next one in priority.
I'm guessing that can be done by loading them from highest to lowest priority, and then simply selecting the first. 


##Possible improvements:
* Extra subtitle sources
* Auto-update - If not, we can just implement update notification. 
* Activate with keypress - ( The DREAM ) - disgustingly non-trivial because of VLC Lua extesnion api. 
