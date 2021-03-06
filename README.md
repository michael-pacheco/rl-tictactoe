
1. [Overview](#overview)			
2. [Tests and Results](#results)
3. [Requirements](#requirements)

<a name="overview"></a>
<h1>Overview</h1>
<h1>
	A reinforcement learning agent that learns to play tic tac toe.
</h1>
<p>
	Tic Tac Toe has many actions that are equivalent because of the symmetric properties of the board being a square. There are several ways to manipulate the board to reach states that would be a result of other sets of actions performed throughout the game. Another way to achieve this same idea is to limit the actions of the agent. The actions under my consideration require the board to possess one of the following two properties:
</p>
	<ol>
		<li>
			Board is empty
		</li>
		<li>
			The first action of the first player is in the middle of the board, (1, 1).
		</li>
	</ol>
<p>
	If one of those properties hold, the following actions in each set can be thought of as equivalent, as the board can be rotated to achieve any of the other states as a result of any of the equivalent actions:
	<br>
	<ol>
		<li>
			([0, 0], [0, 2], [2, 0], [2, 2])
		</li>
		<li>
			([0, 1], [1, 0], [1, 2], [2, 1])
		</li>
	</ol>
</p>
<p>
	Using this idea we can remove a considerable amount from the state space, as we can actually limit the set of possible actions for the first player's first move to 3, and potentially the second player's set of possible actions for their first move to 2. We can only limit the second player's first set of actions if the first player chose to mark the middle of the board with their first move, as the second property stated above would hold.
</p>
<p>
	The main goal of this was to compare two agents (time of execution, size of state space, win rate, number of draws, etc): one where its action/state space was minimized using this idea, and another agent where it was not - to see how impactful this minimization could potentially be on the agent's performance. 
</p>
<p>
	There are more states that can be taken under consideration using the same idea, though it is arguable that continuing to limit the action space of the agent would begin to change the game entirely, and would most likely result in the loss of major aspects of the core game (eg. losing the chance for the agent to learn possible strategies that humans may actively be using in their gameplay).
</p>
<a name="results"></a>
<h1>
	Results:
</h1>
<p>
	For each of these trials, the two agents learned to play Tic Tac Toe from scratch each iteration. They both played 500,000 games each iteration, for 10 iterations (except average reward over time, where they played 1,000,000 games for one iteration). Agent 1 using the minimized action space. It seems most of the time (7/10 in most cases), the first agent outperforms the second. The differences in performance might be even more drastic if there were more games played per iteration, as once the agents learn to play optimally, there will be more games to win.
</p>
<br>
<ol>
  <li> 
    Average Reward Over Time (1,000,000 games, 1 iteration):
    <img src="Avg Reward Over Time.png">
  </li>
  <li>
    Execution Time Per Iteration (500,000 games, 10 iterations):
    <img src="Execution Time Per Iteration.png">
  </li>
  <li>
    Win Rate Per Iteration (Excluding Draws) (500,000 games, 10 iterations):
    <img src="Win Rate Per Iteration (Excluding Draws).png">
  </li>
  <li>
    Win Rate Per Iteration (Excluding Draws) (500,000 games, 10 iterations):
    <img src="Win Rate Per Iteration (Including Draws).png">
  </li>
  <li>
    Draws Per Iteration (500,000 games, 10 iterations):
    <img src="Draws Per Iteration.png">
  </li>
  <li>
    States Per Iteration (500,000 games, 10 iterations):
    <img src="States Per Iteration.png">
  </li>
</ol>
	  

<a name="requirements"></a>
<h1>Requirements: (Python 3x)</h1>
<ul>
  <li>
    Numpy 
  </li>
  <li>
	Plotly (if you would like to graph)
  </li>
</ul>
