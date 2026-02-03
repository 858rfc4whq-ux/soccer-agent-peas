# Soccer Agent using PEAS Framework

class SoccerAgent:
    def __init__(self):
        self.has_ball = False

    def sense(self, ball_near, goal_near):
        self.ball_near = ball_near
        self.goal_near = goal_near

    def act(self):
        if self.has_ball:
            if self.goal_near:
                return "Shoot the ball towards goal"
            else:
                return "Move towards the goal"
        else:
            if self.ball_near:
                self.has_ball = True
                return "Get the ball"
            else:
                return "Move towards the ball"

# Simulation
agent = SoccerAgent()

print(agent.act())
agent.sense(ball_near=True, goal_near=False)
print(agent.act())
agent.sense(ball_near=True, goal_near=True)
print(agent.act())
