# Self Doubt in CoT

So I was reading papers on using reasoning models to better express the confidence of their answers. Can we affect this confidence or can improve the confidence at which they answer by injecting self doubt tokens in their reasoning CoT i.e directly injecting prompts like "wait I think I made a mistake in one of the earlier steps" or "There seems to be a mistake in reasoning" inside <think></think> or <reasoning></reasoning> chains based on the models used. I think this is a good starting point for now and first of all now I want to collect more evidence on this kind of intervention in the reasoning CoT

I am thinking of using a small reasoning model which emits the thinking tokens and using a appropriate small dataset that will help me get sufficient evidence for the working of this hypothesis. So in all I want to get the accuracy metric on the dataset and also the self predicted confidence from the model, it would also be better to later do an analysis on the token length of the reasoning trace and the answer trace, so saving the model outputs for all experiments performed in a json file seems be a good idea

We will have to do token forcing to get the final answer doing something like "Final Answer: " and only filling the later part with digits and similarly for the modle estimated confidence using "Confidence: ", the system prompt will also have to be updated appropriately

Some related papers:
Reasoning models can be effective without thinking
Reasoning models don't always say what they think
Reasoning about uncertainty: Do Reasoning models know when they don't know?
Reasoning models better express their confidence
Parallel structure in Pre Training Data yeild In Context Learning