## Dependencies
- Python >= 3.5
- Keras >= 2.24 (Earlier versions probably work)
- numpy

## How to Run
You can train an agent from scratch with ```python train.py```. 

In constants.json you can change hyperparameters including "save_weights_file_path" and "load_weights_file_path" (both relative paths) to save and load weights respectively. For example, to use the pretrained weights in the weights folder, set the value of  "load_weights_file_path" to "weights/model.h5". Weights for both target (tar) and behavior (beh) keras models are saved every time the current success rate is at a new high. 

You can also test an agent with ```python test.py```. But make sure to load weights by setting "load_weights_file_path" in constants.json to a relative path with both behavior and target weights. 

All the constants are pretty self explanatory other than "vanilla" under agent which means DQN (true) or Double DQN (false). Defualt is vanilla DQN. 

Note: If you get an unpickling error in [train](https://github.com/maxbren/GO-Bot-DRL/blob/master/train.py#L46) or [test](https://github.com/maxbren/GO-Bot-DRL/blob/master/test.py#L43) then run ```python pickle_converter.py``` and that should fix it
