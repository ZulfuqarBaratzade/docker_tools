# Use the official Jenkins base image
FROM jenkins/jenkins:lts

# Skip the initial setup wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# Install necessary plugins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt

# Set up Jenkins user
RUN echo 2.0 > /usr/share/jenkins/ref/jenkins.install.UpgradeWizard.state

# Copy configurations and scripts
COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/executors.groovy
COPY casc.yaml /usr/share/jenkins/ref/casc.yaml

# Expose the HTTP port for Jenkins
EXPOSE 8080

# Expose the agent port for Jenkins
EXPOSE 50000
