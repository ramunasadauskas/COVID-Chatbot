## Dependencies
- Python >= 3.5
- Keras >= 2.24 (Earlier versions probably work)
- numpy

## How to Run
You can train an agent from scratch with ```python train.py```. 

In constants.json you can change hyperparameters including "save_weights_file_path" and "load_weights_file_path" (both relative paths) to save and load weights respectively. For example, to use the pretrained weights in the weights folder, set the value of  "load_weights_file_path" to "weights/model.h5". Weights for both target (tar) and behavior (beh) keras models are saved every time the current success rate is at a new high. 

You can also test an agent with ```python test.py```. But make sure to load weights by setting "load_weights_file_path" in constants.json to a relative path with both behavior and target weights. 

All the constants are pretty self explanatory other than "vanilla" under agent which means DQN (true) or Double DQN (false). Defualt is vanilla DQN.

## Test (or Train) with an Actual User
You can test the agent by inputing your own actions as the user (instead of using a user sim) by setting "usersim" under run in constants.json to false. You input an action and a success indicator every step of an episode/conversation in console. The format for the action input is: intent/inform slots/request slots.

Example action inputs:
- inform/age: 30/
- inform/gender: male/
- inform/fever: mild/
- inform/sorethroat: none/
- inform/runnynose: no/
- inform/rapidbreathing: no/
- inform/blueinface: no/
- thanks//
- done//

In addition the console will ask for an indicator on whether the agent succeeded yet (other than after the initial action input of an episode). Allowed inputs are -1 for loss, 0 for no outcome yet, 1 for success. 

