---
source: https://youtu.be/RcNhY3vMcpY
tags:
  - ml-ai
  - mlops
---

# Data Science Design Pattern
---
## Software Engineering
---
- design after the fact 
	- refactoring is part of the job 
	- don't over engineering 
- design for people's cognitive capacity
	- limit to 5 specific concepts
	- use meaning variable naming
- design for testability
	- bring confidence for making changes 
	- how can I design for easy to test code?

## Workflow pipeline pattern
---
- goal: isolate different steps
- benefits: portability and scalability and maintainability 
- implement pipeline using:
	- Airflow
	- MLflow
	- TFX
- need to use "transform design pattern"

![[transform-pattern-example.png]]
- feature store design pattern
![[feature-store-concept.png]]