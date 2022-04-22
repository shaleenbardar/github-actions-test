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
10) To Store or clone a directory to Github VM -> uses: actions/checkout@v1 under steps


## To Use Enviroment Variables -> For examples
echo "HOME: ${HOME}"
echo "GITHUB_ACTION: ${GITHUB_ACTION}"
echo "WF_ENV: ${WF_ENV}"
echo JOB_ENV: ${JOB_ENV}"
echo STEP_ENV: ${STEP_ENV}"

## To encrypt Enviroment Variables -> Secrets
Go to secret create a key value pair and in code use ${{secrets.Github_secretKey}}


## Context Passing
1) Starts with "$" sign Then have 2 {{ space and variable/function/str/int/float space }}
2) for example {{ toJson(job) }} for logs

## Default Funtion you can use provided by Github
1) contains('hello', 'll') returns bool
2) strartswith ('hello', 'h')
3) endswith ('hello', 'o')
4) format ('Hello {1} {2} {3}', 'World', '!', '!')

## IF Key
1) Not used with curly brackets
2) if we want tot use a function only when there is push or pull request
3) then use if inside a job or steps wherever you want then use ->
  if: github.event_name == 'push'
  if: failure()
4) If you want to specify if any step fails and after failing  a step should have to run then use "always()"-> 
  if: always()
