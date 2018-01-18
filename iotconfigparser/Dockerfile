FROM ubuntu:latest
RUN apt-get -y update 
RUN apt-get install -y git python3-dev python3-pip vim zsh curl zlib1g-dev libssl-dev bzip2 libreadline6-dev

# Change shell to zsh
ENV SHELL /bin/zsh
RUN sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
RUN ln -s /usr/bin/python3 /usr/bin/python && ln -s /usr/bin/pip3 /usr/bin/pip

# Install virtualenvwrapper
RUN mkdir ~/.virtualenvs
RUN pip install virtualenv virtualenvwrapper
# RUN echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.zshrc
ENV WORKON_HOME=~/.virtualenvs
RUN echo "export WORKON_HOME=$WORKON_HOME" >> ~/.zshrc
# RUN echo "source /usr/share/virtualenvwrapper/virtualenvwrapper.sh" >> ~/.bashrc
# RUN echo "export WORKON_HOME=$WORKON_HOME" >> ~/.bashrc

#Install pyenv
RUN curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | zsh
RUN echo 'export PATH="/root/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenvwrapper)"' >> ~/.zshrc

# Install pyenv-virtualenvwrapper
RUN git clone https://github.com/pyenv/pyenv-virtualenvwrapper.git $(pyenv root)/plugins/pyenv-virtualenvwrapper
ENV PYENV_VIRTUALENVWRAPPER_PREFER_PYVENV="true"
RUN echo "export PYENV_VIRTUALENVWRAPPER_PREFER_PYVENV="true" >> ~/.zshrc
RUN pyenv virtualenvwrapper

# Switch to python 3.6 default (tool is python 3.6+)
RUN pyenv install 3.6.4

CMD ["/bin/zsh"]


# Commands that don't work
# VOLUME ["/home/alex/workspace/sw_webdev/iot/iotconfigparser/", "/root/iotconfigparser"]
# RUN pip3 install -r ~/iotconfigparser/requirements.txt && pip install --upgrade pip