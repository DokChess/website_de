+++
title = "Playing Strength"
menuTitle = "11.3 Playing Strength"
weight = 3
url="11_risks/03_playingstrength"
+++

## 11.3 Risk: Reaching the Playing Strength

The quality goals demand both an acceptable playing strength and a simple, accessible solution.
In addition, there are requirements with respect to efficiency.
It is uncertain whether the planned Java solution with an object-oriented domain model and simple move selection  can achieve these competing goals.

The risk manifests itself through too bad playing strength, too long waiting times or both.
This would be particularly unpleasant for live performances in lectures, as the solution is not perceived as such by the listeners (but as a toy).

It is unclear at what point a playing strength is considered to be unreasonably weak.

### Eventuality Planning

In conference talks, parts of the live demonstration could be omitted. If necessary, we could show games played before.


### Risk Minimization

Suitable scenarios (examples [→ 10. "Quality Scenarios"](/en/10_qualityscenarios/)) concretize the quality goals.
With the help of chess literature (chess problems to be precise) we develop test cases (unit testing), which specify what playing strength can be expected.
Thus at least we detect early where the engine stands.