# Docker files and Docker compose explorations

Learning to containerise stuff as I move machines & operating system often between work/home.

## TODO list:
- Filesystem (zsh)
- i3wm
- Spacemacs
- Compose all the above
- Make them work on windows with XMing/MobaXTerm


## Environment

Files in this folder will assume the following environment variables:
- `HOME`: path to user's home directory i.e. `/home/user/`
- `WORKSPACE`: path to general development workspace 
- `IDEA_WORKSPACE`: path to workspace for Intellij IDEA (Community)
- `ANDROID_WORKSPACE`: path to workspace for Android Studio
# Program Specific details
## Jetbrains IDEs
### IDEA
- Specify and symlink in `.Idea/config`, `.Idea.java`, `.Idea.maven`, `.Idea.gradle` to home flder
## Android Studio
- Android Studio uses same set up as IDEA but doesn't have a .maven folder
- Android SDK specific files installed at `~/.android` 
- For device debugging, mount local `/dev/bus/usb` to give container access to usb devices 
