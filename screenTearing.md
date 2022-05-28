1. X11 or Wayland?

Depending on the distribution and desktop environment one of those protocols is in use. You can check this for example with the environment variable $XDG_SESSION_TYPE. Run “echo $XDG_SESSION_TYPE” in your terminal/console and it should return the current type of the session.

Wayland:
foo@linux:~> echo $XDG_SESSION_TYPE
wayland
foo@linux:~>

X11:
foo@linux:~> echo $XDG_SESSION_TYPE
x11
foo@linux:~>

Right there we may already have a possible solution to our problem. With Wayland tearing is actually a very rare issue compared to the X11 days. I only encountered it because of bad drivers. So if you are on X11 and you are using a more common desktop environment like Gnome or KDE Plasma, you should be able to select the session type on the login screen. There is a good chance this will already fix the problem.
2. X11 with Intel, AMD or Nvidia graphics

Please be careful, only edit configuration files in your system if you know what those options do! Back them up beforehand to be able to revert changes you did!

You are stuck on X11 because Wayland is not supported with the distro or desktop environment your currently using? For X11 there is an option in the xorg configuration file called “Tearfree” which should be set.
Intel:

/etc/X11/xorg.conf.d/20-intel.conf

Section "Device"
  Identifier "Intel Graphics"
  Driver "intel"
  Option "TearFree" "true"
EndSection

see https://wiki.archlinux.org/index.php/intel_graphics#Tearing

For AMD the configuration looks almost the same:

/etc/X11/xorg.conf.d/20-amdgpu.conf

Section "Device"
     Identifier "AMD"
     Driver "amdgpu"
     Option "TearFree" "true"
EndSection

see https://wiki.archlinux.org/index.php/AMDGPU#Tear_free_rendering

For Nvidia the configuration is a little bit more complicated. Please read the details in the arch wiki about this topic! https://wiki.archlinux.org/index.php/NVIDIA/Troubleshooting#Avoid_screen_tearing

/etc/X11/xorg.conf.d/20-nvidia.conf

Section "Device"
        Identifier "Nvidia Card"
        Driver     "nvidia"
        VendorName "NVIDIA Corporation"
        BoardName  "GeForce GTX 1050 Ti"
EndSection

Section "Screen"
    Identifier     "Screen0"
    Device         "Device0"
    Monitor        "Monitor0"
    Option         "metamodes" "nvidia-auto-select +0+0 {ForceFullCompositionPipeline=On}"
    Option         "AllowIndirectGLXProtocol" "off"
    Option         "TripleBuffer" "on"
EndSection
