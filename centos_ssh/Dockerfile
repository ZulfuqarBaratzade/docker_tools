# Use the official Red Hat UBI (Universal Base Image) as the base image
FROM registry.access.redhat.com/ubi8/ubi

# Install the required packages, including OpenSSH server
RUN yum install -y openssh-server && \
    yum clean all

# Create a new user for SSH access
RUN useradd -rm -d /home/sshuser -s /bin/bash -G wheel -u 1001 sshuser

# Set the password for the new user (change "password" to your desired password)
RUN echo 'sshuser:password' | chpasswd

# Expose SSH port
EXPOSE 22

# Start the SSH server
CMD ["/usr/sbin/sshd", "-D"]
