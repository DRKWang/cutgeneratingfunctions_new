# Target
- fix the "you are missing the cgal library" issue.

# Progression
- This reason of it is the setup.py program did not find the ```libCGAL_Core.dylib``` and some other cgal library under the location of ```file:///usr/local/lib```.
  This problem might be caused by that I installed cgal package twice by using source code and homebrew, and therefore it has been created incorrectly. 
  Some commands have been tried to relink the lib by using brew, but did not work yet.
- Not quite sure whether the cgal is installed in the correct way because there does not include ```libCGAL_Core.dylib```, which should be included according to 
  [this](https://github.com/cdcseacave/openMVS/issues/359).
