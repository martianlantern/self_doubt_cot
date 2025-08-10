# Self Doubt in CoT

So I was reading papers on using reasoning models to better express the confidence of their answers. Can we affect this confidence or can improve the confidence at which they answer by injecting self doubt tokens in their reasoning CoT i.e directly injecting prompts like "wait I think I made a mistake in one of the earlier steps" or "There seems to be a mistake in reasoning" inside <think></think> or <reasoning></reasoning> chains based on the models used. I think this is a good starting point for now and first of all now I want to collect more evidence on this kind of intervention in the reasoning CoT

I am thinking of using a small reasoning model which emits the thinking tokens and using a appropriate small dataset that will help me get sufficient evidence for the working of this hypothesis. So in all I want to get the accuracy metric on the dataset and also the self predicted confidence from the model, it would also be better to later do an analysis on the token length of the reasoning trace and the answer trace, so saving the model outputs for all experiments performed in a json file seems be a good idea

We will have to do token forcing to get the final answer doing something like "Final Answer: " and only filling the later part with digits and similarly for the modle estimated confidence using "Confidence: ", the system prompt will also have to be updated appropriately

Roadmap:
Step 1.
Benchmark deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B on 500 subset of GSM8K dataset, the subset should be fixed so that every other experiment will be on that subset so that we will get clear accuracy and confidence measures, will use hard token constraints for Final answer and confidence. This should do both baseline A (thinking) and baseline B (no thinking). Compute accuracy and confidence and save everything to the json so that further analysis can be done on it later

Some related papers:
Reasoning models can be effective without thinking
Reasoning models don't always say what they think
Reasoning about uncertainty: Do Reasoning models know when they don't know?
Reasoning models better express their confidence
Parallel structure in Pre Training Data yeild In Context Learning