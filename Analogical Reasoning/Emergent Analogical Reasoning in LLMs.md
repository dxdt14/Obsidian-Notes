[Emergent Analogical Reasoning in Large Language Models](https://arxiv.org/abs/2212.09196)
## Abstract
- The ability for solving novel-problems *zero-shot* is heavily tied to analogical reasoning in humans
- Thus, a direct comparison b/t human reasoners and LLMs on analogical tasks is performed
- GPT-3 displayed surprisingly strong capacity for abstract pattern induction, matching or surpassing humans in most settings
	- GPT-4 even better
- results $\implies$ emergent ability for zero-shot solutions to analogy problems
## Intro
- In humans, solutions to unfamiliar problems are often found by comparison to familiar situations
- LLM's seem capable of few-shot or even zero-shot problem solving
- Paper evaluated GPT-3 on a bunch of zero-shot analogy tasks
- GPT-3 performed better than college students in matrix reasoning (task specified in paper), letter string analogies, verbal analogies, and similar in story analogies
## Results
### Matrix Reasoning Problems
- data structued into a matrix where there is some sort of structure/pattern present in the data
- Matrix has all cells except for 1 filled in and LLM has to either generate answer to the blank cell or select from choices (multiple choice)
- GPT-3 (on average) performed better than the average human level (UCLA undergrads) on both answer generation and answer selection
	- The average performance for humans varied greatly,
		- best participant answered every problem correctly
- GPT-3's pattern of performance across problem subtypes was similar to human participants
- Author's argue that the success on this problem type can be taken as evidence that GPT-3 has acquired core capabilities underlying analogy
	- human performance on this task is heavily correlated to other analogical reasoning tasks
### Letter string analogies
- Given a source string and a result string where some transformation is applied to the source string
- Test subject (human/LLM) must determine the transformation rule and apply it to a given string to get the answer
- GPT-3 performed (on average) better than the human participants
	- Also showed similar error patterns across transformation types to humans
- GPT-3's performance was sensitive to the way in which problems were formatted
	- performance suffered when no prompt was given, problems were presented in a complete sentence
		- was still within one std dev on human performance
- Also tested GPT-3's performance on a generalization from letter string analogies to real-world concepts
	- e.g. a b c $\to$ a b d, cold cool warm $\to$ ?
### Four-term verbal analogies
- Dataset contains a series of four-term verbal analogy problems of the form 'A:B::C:?' together with answer choices
- GPT-3's choice was the option of the highest log probability
- The problem and GPT-3's choice were then appended to context window for next problem
	- Simulates contextual effects that may arise from continuous problem solving
- GPT-3 performed as well or better than human participats
- GPT-3 was sensitive to semantic content similar to that observed in human participants
### Story analogies
- 