# Distinguishing Games
## Distinguishing Game:
- Distinguisher is given a black box with A or B in it, equally likely
- D follows an algorithm and guesses A or B
- Advantage = Prob guess right - Prob guess wrong
- Pr[guess A | box is A] - Pr[guessA | box is B]


ex: Let f be a black box with either one 12-sided die or two 6-sided dice
Left f be used only once
1. Give an algorithm using f().
```
x = f()
if x == 1
	guess "1x12"
else
	guess "2x6"
```
2. Calculate advantage
$$
\begin{equation}
Pr[guess\;``1x12" |\;f\;is\;``1x12"] - Pr[guess\;``1x12" |\;f\;is\;``2x6"]
\end{equation}
$$
$$
\frac{1}{12} - 0 = \frac{1}{12}
$$

```
x = f()
if x == {1,2,3,11,12}
	guess "1x12"
else
	guess "2x6"
```

$$
\begin{equation}
Pr[guess\;``1x12" |\;f\;is\;``1x12"] - Pr[guess\;``1x12" |\;f\;is\;``2x6"]
\end{equation}
$$
$$
\frac{5}{12} - \frac{4}{12} = \frac{1}{12}
$$
