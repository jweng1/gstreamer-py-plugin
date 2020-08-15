# gstreamer-py-plugin

# Clone repo
git clone https://github.com/jweng1/gstreamer-py-plugin.git

# Run ubuntu container image 
podman run -ti --privileged --net=host -v `pwd`:/work docker.io/jweng1/gst-base-image:v1


# Set up
cd work
cd gstreamer-py-plugin

python3 -m venv venv
source venv/bin/activate
pip install -U wheel pip setuptools

pip install -r requirements.txt

# Export plugin 
export GST_PLUGIN_PATH=$GST_PLUGIN_PATH:$PWD/venv/lib/gstreamer-1.0/:$PWD/gst/

# Inspect your plugin 
gst-inspect-1.0 python 
