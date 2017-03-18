# evaluateFA
Evaluation script for forced aligned textgrid

- This script evaluates a TextGrid (i.e. prediction; usually of forced alignment) with regard to one reference TextGrid (i.e. target; usually human segmented).

## What we need
- Two **TextGrid files** of an audio file:
	- One by **automatic forced alignment (FA)**
	- One by **human** as a reference

## Input arguments
- 1) Name of .TextGrid file to **evaluate** (usually a forced alignment)
- 2) Name of .TextGrid file to **refer to** (usually by human)
- 3) **Tolerance (ms)** for accuracy calculation (default: 20 ms)

## Output
- **evaluation.csv**
	- includes 5 columns
		- First 3 columns:
			- records of 3 given input arguments
		- Last 2 columns:
	       - 1) **Total Error (ms)**
	       - 2) **Alignment Accuracy (%)**  
	       	= what percentage of the automatically labeled boundaries are within a given time tolerance (threshold) of the manually labeled boundaries.


## Usage
- Evaluate performance of a forced aligned TextGrid, referencing to human alignment:  
	
		$ python evaluateFA.py <FA_textgrid> <human_textgrid> <tolerance>
	
- For example:
	
		$ python evaluateFA.py fa.TextGrid human.TextGrid 30
		

