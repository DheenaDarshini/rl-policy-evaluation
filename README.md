# POLICY EVALUATION

## AIM
To develop a Python program to create our own policy, evaluate and compare it with the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION
```
Reg no: 212223240030
Developed By: Dheena Darshini Karthik Dheepan

```
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy

    while True:
        delta = 0
        for s in range(len(P)):
            a = pi[s] if isinstance(pi, dict) else pi(s)
            v = 0
            for prob, next_state, reward, done in P[s][a]:
                v += prob * (reward + gamma * prev_V[next_state])
            delta = max(delta, abs(v - V[s]))
            prev_V[s] = v
        if delta < theta:
            break
    
    return prev_V
```

## OUTPUT:
<img width="1269" height="1013" alt="Screenshot 2025-09-20 085741" src="https://github.com/user-attachments/assets/36a06ee0-c400-41fc-8569-95dbf40f3d83" />

<img width="1220" height="1154" alt="Screenshot 2025-09-20 085929" src="https://github.com/user-attachments/assets/a984b817-5f4e-4328-b0af-118bb101f559" />

<img width="1547" height="257" alt="Screenshot 2025-09-20 091102" src="https://github.com/user-attachments/assets/6f7f3452-b988-4f74-aa59-1136dfe003d7" />

<img width="1149" height="365" alt="Screenshot 2025-09-20 091223" src="https://github.com/user-attachments/assets/c670f49f-2e37-4d38-a097-72e650992a8b" />

<img width="1097" height="463" alt="Screenshot 2025-09-20 091233" src="https://github.com/user-attachments/assets/21a70257-58f6-4361-b812-6ec3cb1025b3" />

<img width="1362" height="191" alt="Screenshot 2025-09-20 091243" src="https://github.com/user-attachments/assets/67e73535-9fd5-40fa-b6a9-7c2158edf5a0" />

<img width="1089" height="339" alt="Screenshot 2025-09-20 091250" src="https://github.com/user-attachments/assets/b649b364-5b2c-437b-bdfc-9f8c2e8ce146" />


## RESULT:
Thus, The Python program to evaluate the given policy is successfully executed.
