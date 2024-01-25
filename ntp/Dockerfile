# Use a lightweight base image
FROM alpine:latest

# Install chrony
RUN apk --no-cache add chrony

# Expose NTP port
EXPOSE 123/udp

# Copy custom chrony configuration file
COPY chrony.conf /etc/chrony/chrony.conf

# Run chrony in the foreground
CMD ["chronyd", "-d", "-s"]
