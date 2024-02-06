FROM condaforge/mambaforge

# Create user name and home directory variables.
# The variables are later used as $USER and $HOME.
ENV USER=smsreg
ENV HOME=/home/$USER

# Add user to system
RUN useradd -m -u 1000 $USER

# Set working directory (this is where the code should go)
WORKDIR $HOME/app

SHELL ["/bin/bash", "-c"]

RUN apt-get update && apt-get upgrade -y && apt install gcc -y && apt install build-essential -y

# Install environment
COPY environment.yml ./
RUN mamba env create -f environment.yml -n webmspredict && \
    mamba clean -a

# Set mrsa-workflow environment as active at start-up
RUN echo "source activate webmspredict" >> ~/.bashrc

# Add environment to PATH
ENV PATH /opt/conda/envs/webmspredict/bin:${PATH}

COPY ./main.py $HOME/app/main.py
COPY ./start-script.sh $HOME/app/start-script.sh
COPY ./assets $HOME/app/assets

# Give access to appripriate files and folders to the created user
RUN chmod +x start-script.sh \
    && chown -R $USER:$USER $HOME \
    && rm -rf /var/lib/apt/lists/*

# Open up port 8080
USER $USER
EXPOSE 8080

ENTRYPOINT ["./start-script.sh"]
