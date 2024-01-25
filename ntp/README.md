docker build -t my-ntp-image .
docker run -p 123:123/udp --name my-ntp-container -d my-ntp-image
