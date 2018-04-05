FROM alexn34/manjaro:latest
RUN pacman -Syyu
RUN pacman -S zsh i3-manjaro --noconfirm

# Change shell to zsh
ENV SHELL /bin/zsh
RUN sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

