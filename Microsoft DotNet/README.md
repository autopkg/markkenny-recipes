# NOTES
Building on [DataJars DotNEt download recipes](https://github.com/autopkg/dataJAR-recipes/tree/8582a63e32d5f4f875e6eaeaf4e237c2ffbc860a/DotNet%209%20SDK) I've 'yaml-ised' them and added a PKG policy as we don't run Munki. Also made it a Universal PKG to reduce smartgroups on our servers as we're fine with an 800MB PKG for the few folks that want it.


# The Main One!
Once I got my head around the options, then I could pull together a single download and PKG recipe that can be dialed in with your override. Testing now with 11! 
