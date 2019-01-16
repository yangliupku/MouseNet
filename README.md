# Docker Environment for MouseNet

This package will allow you to run MouseNet to track the body parts of mouse via tensorflow serving inside a docker container.

## Prerequisites

**(1)** Install Docker. See https://docs.docker.com/install/ & for Ubuntu: https://docs.docker.com/install/linux/docker-ce/ubuntu/

## Starting the docker container
In the terminal start your container with the following command
```
docker run -p 8501:8501  -e MODEL_NAME=dlc -t yangliupku/mousenet
```
If sucessful, you should see output like 
```
2019-01-15 03:45:05.882174: I tensorflow_serving/model_servers/server.cc:82] Building single TensorFlow model file config:  model_name: dlc model_base_path: /models/dlc
2019-01-15 03:45:05.882471: I tensorflow_serving/model_servers/server_core.cc:461] Adding/updating models.
2019-01-15 03:45:05.882521: I tensorflow_serving/model_servers/server_core.cc:558]  (Re-)adding model: dlc
2019-01-15 03:45:05.983368: I tensorflow_serving/core/basic_manager.cc:739] Successfully reserved resources to load servable {name: dlc version: 1030000}
2019-01-15 03:45:05.983500: I tensorflow_serving/core/loader_harness.cc:66] Approving load for servable version {name: dlc version: 1030000}
2019-01-15 03:45:05.983544: I tensorflow_serving/core/loader_harness.cc:74] Loading servable version {name: dlc version: 1030000}
2019-01-15 03:45:05.983594: I external/org_tensorflow/tensorflow/contrib/session_bundle/bundle_shim.cc:363] Attempting to load native SavedModelBundle in bundle-shim from: /models/dlc/1030000
2019-01-15 03:45:05.983636: I external/org_tensorflow/tensorflow/cc/saved_model/reader.cc:31] Reading SavedModel from: /models/dlc/1030000
2019-01-15 03:45:06.000312: I external/org_tensorflow/tensorflow/cc/saved_model/reader.cc:54] Reading meta graph with tags { serve }
2019-01-15 03:45:06.029118: I external/org_tensorflow/tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
2019-01-15 03:45:06.112191: I external/org_tensorflow/tensorflow/cc/saved_model/loader.cc:162] Restoring SavedModel bundle.
2019-01-15 03:45:06.335775: I external/org_tensorflow/tensorflow/cc/saved_model/loader.cc:138] Running MainOp with key legacy_init_op on SavedModel bundle.
2019-01-15 03:45:06.335870: I external/org_tensorflow/tensorflow/cc/saved_model/loader.cc:259] SavedModel load for tags { serve }; Status: success. Took 352225 microseconds.
2019-01-15 03:45:06.335919: I tensorflow_serving/servables/tensorflow/saved_model_warmup.cc:83] No warmup data file found at /models/dlc/1030000/assets.extra/tf_serving_warmup_requests
2019-01-15 03:45:06.336184: I tensorflow_serving/core/loader_harness.cc:86] Successfully loaded servable version {name: dlc version: 1030000}
2019-01-15 03:45:06.338901: I tensorflow_serving/model_servers/server.cc:286] Running gRPC ModelServer at 0.0.0.0:8500 ...
[warn] getaddrinfo: address family for nodename not supported
2019-01-15 03:45:06.340600: I tensorflow_serving/model_servers/server.cc:302] Exporting HTTP/REST API at:localhost:8501 ...
[evhttp_server.cc : 237] RAW: Entering the event loop ...
```
Congrates! You're good to track your mouse. See the jupyter notebook for some examples. 

## Running on GPU: 
coming soon.
