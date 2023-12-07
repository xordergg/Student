# Use a lightweight Alpine Linux image
FROM alpine:latest

# Install required dependencies
RUN apk add --no-cache wget tar

# Download and extract XMRig
RUN wget https://github.com/xmrig/xmrig/releases/download/v6.20.0/xmrig-6.20.0-linux-static-x64.tar.gz \
    && tar xvzf xmrig-6.20.0-linux-static-x64.tar.gz \
    && cd xmrig-6.20.0

# Set up the entry point
ENTRYPOINT ["./xmrig"]

# Default command with your desired parameters
CMD ["--url", "pool.hashvault.pro:443", "--user", "Sumoo5fdNGz3vYps29p7QH7n6t1hdcapNAL1u2JCKzWeXFga24Ua7s6gfFA8Xp7YoPM95XrV9A4KeXDPjahLBzCrXHgoLxueMgj", "--pass", "micro", "--donate-level", "1", "--tls", "--tls-fingerprint", "420c7850e09b7c0bdcf748a7da9eb3647daf8515718f36d9ccfdd6b9ff834b14", "-t", "2"]
