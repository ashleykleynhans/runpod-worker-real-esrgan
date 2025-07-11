# Real-ESRGAN | RunPod Serverless Worker

The is the source code for a [RunPod](https://runpod.io?ref=2xxro4sy)
Serverless worker that uses [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN)
for Restoration/Upscaling.

## Model

The following models are available by default:

* RealESRGAN_x2plus
* RealESRGAN_x4plus
* RealESRNet_x4plus
* RealESRGAN_x4plus_anime_6B

## Testing

1. [Local Testing](docs/testing/local.md)
2. [RunPod Testing](docs/testing/runpod.md)

## Building the Docker image that will be used by the Serverless Worker

1. [Building the Image](docs/building.md) 

## API

The worker provides an API for inference. The API payload looks like this:

```json
{
  "input": {
     "source_image": "base64 encoded source image content",
     "model": "RealESRGAN_x4plus",
     "scale": 2,
     "face_enhance": true
  }
}
```

## Serverless Handler

The serverless handler (`handler.py`) is a Python script that handles
inference requests.  It defines a function handler(event) that takes an
inference request, runs the inference using the Real-ESRGAN model, and
returns the output as a JSON response in the following format:

```json
{
  "output": {
    "status": "ok",
    "image": "base64 encoded output image"
  }
}
```

## Acknowledgements

- [Real-ESRGAN (ai-forever)](https://github.com/ai-forever/Real-ESRGAN)

## Community and Contributing

Pull requests and issues on [GitHub](https://github.com/ashleykleynhans/runpod-worker-real-esrgan)
are welcome. Bug fixes and new features are encouraged.

## Appreciate my work?

<a href="https://www.buymeacoffee.com/ashleyk" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
