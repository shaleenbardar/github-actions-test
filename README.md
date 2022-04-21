# github-actions-test
This Repository is to Learn how github-actions work
1) Use "runs-on" key to specify an operting system
2) If you want to use another operating system you will need to create a new job
3) if you want to serialize many task like one after the other then use "needs array" 
4) If you want to run many commands at once use "|" pipe in run.
5) if you want a different shell then use "shell" key at the end of the run to specify on which shell you want to run
6) To use actions, use "uses" instead of "runs" so that it will take a reference to some repo.
7) To give an input to an action -> We use "with" Key
8) We can also use id in a job. 
9) To use a variable use {{% steps.id.output.variable }}
