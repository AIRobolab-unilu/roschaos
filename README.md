# roschaos
Audit and test security vulnerabilities or simply wreak chaos upon your ROS system

## Installation

Navigate to `<catkin_ws>/src`

```
git clone https://github.com/AIRobolab-unilu/roschaos
cd ..
catkin_make
. devel/setup.bash
```
Now we need to build the package:
```
cd src/roschaos

python setup.py build
```

And we have to intall it:
```
sudo python setup.py install
```
This might need root priviledges, therefore the "sudo"

## Usage

In `<catkin_ws>/src/roschaos/scripts`, run one of the following commands, while the nodes to be tested are also running.

### Master:

`roschaos master unregister <node, service, topic> [--options]`

Options are:
node:
  ```
  --node_name <NODE_NAME>
  --node_uri <NODE_URI>
  --all
  ```
service:
  ```
  --service_name <SERVICE_NAME>
  ```
topic:
  ```
  --topic_name <TOPIC_NAME>
  --topic_type <TOPIY_TYPE>
  --subscribers 
  --publishers
  ```
  
### Slave

`roschaos slave <backtrace, service, logger, shutdown> [--options]`

Options are:

backtrace:
 ```
 master [--uri <URI>]
 ```
logger:
  ```
  --node_name <NODE_NAME>
  --node_uri <NODE_URI>
  --logger_name <LOGGER_NAME>
  --logger_level <LOGGER_LEVEL>
  ```
shutdown
  ```
  node [--node_name <NODE_NAME>, --node_uri <NODE_URI>]
  ```
The "service" option doesn't seem to have any suboptions.

### Param

`roschaos param server unsubscribe [--options]`

Options are:
  ```
  --node_name <NODE_NAME>
  --node_uri <NODE_URI>
  --param_key <PARAM_KEY> #required
  ```
  
