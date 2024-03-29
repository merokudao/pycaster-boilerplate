# PyCaster Boilerplate

PyCaster is a python lib that makes it easy to build apps on Farcaster. It can be
used to create Farcaster Frames. This boilerplate provides a demo of it's usage.

Using PyCaster to build your frames backend is easy. I wrote a blog post about it at [https://pranavprakash.in/2024/02/12/building-a-farcaster-frame-in-python-with-flask/](https://pranavprakash.in/2024/02/12/building-a-farcaster-frame-in-python-with-flask/)

If you have any questions, open an issue in this repo or [cast to me on Farcaster](https://warpcast.com/pranav)

# Getting Started

## Install

1. Clone this repo

```shell
git clone git@github.com:merokudao/pycaster-boilerplate.git
```

2. Optional

Create a virtual environment using `python -m venv venv` and
activate it using `source venv/bin/activate`

3. Install Dependencies

```shell
pip install -r requirements.txt
```

## Environment Variables

Depending on your use case, you may need to set one or more of the
following env variables that are needed by PyCaster.

| Var  | Required  | Description  |
|:----------|:----------|:----------|
| NEYNAR_API_KEY    | Recommended    | Used to perform various crucial calls related to user. If your app does user related functions (ex: check if the user follows a channel or has casted something), this will be needed.   |
| REDIS_HOST    | Yes    | Highly recommended to increase speed of frame response. Without this, the `pycaster` lib has to be changed significantly to bypass.   |
| MEROKU_API_KEY    | Optional    | Required if you're building on Meroku dApp Store Kit APIs    |
| OPENAI_API_KEY    | Optional    | Required if you're using OpenAI    |
| AWS_ACCESS_KEY_ID    | Optional    | If your frame needs to upload media to S3, this is needed.    |
| AWS_SECRET_ACCESS_KEY    | Optional    | If your frame needs to upload media to S3, this is needed.    |


Create your own `.env` by copying from `.env.example`.

```shell
cp .env.example .env
```

Set env variables in terminal by

```shell
set -a; source .env; set +a
```
## Run


### Local

RUN using

```shell
flask run --host 0.0.0.0 --port 9091
```


### Docker

#### Build

`docker build -t pycasterdemo .`

#### Run

`docker run -p 9091:5000 --env-file .env pycasterdemo`

## Check

`ruff .`
# Contributing

We'd love to accept contriutions. Please open an issue with what you'd like to build and we'll discuss and take it from there.


