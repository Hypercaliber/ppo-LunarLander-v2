# PPO on LunarLander-v2

A Proximal Policy Optimization (PPO) agent trained to land a spacecraft in Gymnasium's [LunarLander](https://gymnasium.farama.org/environments/box2d/lunar_lander/) environment, using [Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3). I built it while working through Unit 1 of the [Hugging Face Deep Reinforcement Learning course](https://huggingface.co/learn/deep-rl-course).

**Result:** mean reward of **275.66 ± 17.91** over the evaluation episodes. An episode scoring 200 or more counts as solved, so the agent lands reliably.

## Playback

https://github.com/user-attachments/assets/b7386291-5348-4390-bd51-350cc79d94f5

## The Environment

The agent controls a lander that must touch down on the landing pad, which sits between two flags.

- **Observation:** 8 values (position, velocity, angle, angular velocity, and whether each leg touches the ground)
- **Actions:** 4 discrete actions (do nothing, fire left engine, fire main engine, fire right engine)
- **Rewards:** points for moving toward the pad and landing softly, a bonus for each leg that makes contact, small penalties for firing engines, and a large penalty for crashing

## How It Works

PPO is a policy-gradient method. It improves the agent's policy in small, controlled steps by clipping how far each update is allowed to move the policy from the previous one, which keeps training stable. Stable-Baselines3 provides a tested implementation, so the agent is trained with its `PPO` class and a standard multilayer perceptron policy.

## Links

- Course: https://huggingface.co/learn/deep-rl-course
- Stable-Baselines3: https://github.com/DLR-RM/stable-baselines3
