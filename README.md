import gym

# Create the Gym environment
env = gym.make('CartPole-v1')

# Reset the environment to its initial state
state = env.reset()

# Define the number of episodes you want to run
num_episodes = 10

for episode in range(num_episodes):
    total_reward = 0
    done = False

    while not done:
        # Render the environment (optional, for visualization)
        env.render()

        # Take a random action
        action = env.action_space.sample()

        # Step the environment by taking the chosen action
        next_state, reward, done, _ = env.step(action)

        # Update the total reward
        total_reward += reward

        state = next_state

    print(f"Episode {episode + 1}, Total Reward: {total_reward}")

# Close the environment
env.close()
