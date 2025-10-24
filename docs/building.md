## Building the Worker Image

The entire application will be stored within the Docker image
but will obviously create a more bulky Docker image as a result.

You can either use my pre-built Docker image:
```
ghcr.io/ashleykleynhans/runpod-worker-real-esrgan:2.0.3
```

Or alternatively, you can build it yourself following the
instructions below.

### Clone the repo

```bash
git clone https://github.com/ashleykleynhans/runpod-worker-real-esrgan.git
```

### Build the Docker image

```bash
cd runpod-worker-real-esrgan
docker build -t dockerhub-username/runpod-worker-real-esrgan:1.0.0 .
docker login
docker push dockerhub-username/runpod-worker-real-esrgan:1.0.0
```
