# Hackflix

## Basic Idea
Hackflix is a Netflix clone. It will serve some random movies and TV shows. Each movie / tv show contains a random watermark that identifies the user. The user has to upload any video onto thehackbay piracy website. The system will see if the content matches the original content, without the watermark.

## Setup

Install `requirements.txt` and install OpenCV2. Also install `ffmpeg` for imageio. Make sure the binary is in the path.

Place the `config.py` file in the root. The exact secret for the current videos is:

```python
# Server runnning port.
PORT = 5000

# Debug?
DEBUG = True

# App name
APP_NAME = "Hackflix"

# Full domain name.
DOMAIN = 'http://localhost'

# Random Secret.
SECRET = 'shhh'

# Video duration.
DURATION = 5 # 5 second clip.

# Threshold of SSIM to pass.
PASS_THRESHOLD = 0.98
```

Create original videos and follow the directory structure in there to place the mp4 files.

Run development server,

```
python runserver.py
```

And navigate to `localhost:5000/<username>` for Hackflix and `localhost:5000/hackbay/<username>` for Hackbay.

## Adding Distractor Videos

The drive only has one distractor video, we need more. Place more in `hackflix/static/vids`. It _has_ to be an mp4 file. Then place a thumbnail image in the same directory with the name `<file>.mp4.png`.