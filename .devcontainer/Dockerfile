FROM mcr.microsoft.com/devcontainers/java:8

# Install Maven 3.6.3 (compatible with Java 8)
RUN curl -fsSL https://archive.apache.org/dist/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz | tar -xz -C /opt \
    && ln -sf /opt/apache-maven-3.6.3/bin/mvn /usr/local/bin/mvn

# Install Java 21 via SDKMAN (Java 8 is already installed)
RUN bash -c "source /usr/local/sdkman/bin/sdkman-init.sh && sdk install java 21.0.5-tem"

# Configure bashrc to initialize SDKMAN for all sessions
RUN echo '\n# SDKMAN initialization\nexport SDKMAN_DIR="/usr/local/sdkman"\n[[ -s "/usr/local/sdkman/bin/sdkman-init.sh" ]] && source "/usr/local/sdkman/bin/sdkman-init.sh"' >> /home/vscode/.bashrc

# Set Java 8 as default
RUN bash -c "source /usr/local/sdkman/bin/sdkman-init.sh && sdk default java 8.0.462-tem"
