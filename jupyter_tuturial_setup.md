# Jupyter Tutorial Setup

There are a number of Jupyter notebook tutorials in the Caffe2 github repository. They are located [here](https://github.com/caffe2/caffe2/tree/master/caffe2/python/tutorials)

The following instructions describe the required setup before you can run the tutorials. It is based on MacOS. For other OS, you may need to modify the steps accordingly.

* Set up a new virtual environment
```
virtualenv caffe2_tutorials
source caffe2_tutorials/bin/activate
```
* Install brew and required modules
```
brew install protobuf@3.1 lmdb
```
* [Install Caffe2](https://caffe2.ai/docs/getting-started.html?platform=mac&configuration=compile)
  * Remember to install matching protobuf using brew and python
```
pip install \
flask \
future \
glog \
jupyter \
matplotlib \
numpy \
protobuf==3.1.0 \
pydot \
python-gflags \
pyyaml \
scikit-image \
scipy \
setuptools \
six \
tornado

USE_HOST_PROTOC=1 ./scripts/build_local.sh -DBUILD_BINARY=ON -DBUILD_SHARE_DIR=ON
cd build
sudo make install
```
* Run Jupyter notebook
```
cd <caffe2 directory>
./scripts/start_ipython_notebook.sh
```
  * If ipython notebook kernel error, need to reset the kernel.json
```
jupyter kernelspec install-self --user
```
