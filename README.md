```shell
# 1️⃣ Install QEMU to run ARM64 containers on your host
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes

# 2️⃣ Remove old container if it exists
docker rm -f verifier

# 3️⃣ Run the ARM64 container with automatic restart
docker run -d --platform linux/arm64 \
  --restart always \
  -e TOKEN="..." \
  --name verifier \
  nebulaicli/verifier:1.0

# 4️⃣ Follow the container logs
docker logs -f verifier
```
