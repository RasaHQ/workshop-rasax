# Exercise

This file contains the walkthrough of the exercise to be completed using this repository.

## 1. Natural language understanding with Rasa 1.0

To train a NLU model with Rasa, you will need two things - training data and model configuration.

#### Create NLU training data

You can find some training data inside the `./data/nlu.md` file. NLU training data follows the format:

```
## intent:intent_name
 - example1
 - example2
 ...
```
Add a new intent `name` with a few training examples (don't forget to annotate entities). 

#### Create NLU model configuration pipeline

`config.yml` file contains a sample configuration of the model pipeline. You can modify the pipeline if you
like by adding new [pipeline components](http://rasa.com/docs/rasa/nlu/choosing-a-pipeline/). 

#### Train the NLU model
Once you update the training data and model configuration, train the NLU model by running:

`rasa train nlu`

Once mode is trained, it will be saved in a `./models` directory of you project. Test the model by running:

`rasa shell nlu`

## 2. Dialogue management with Rasa 1.0

Dialogue management system is responsible of predicting how an assistant should respond based on the 
state of the conversation as well as context. To train a dialogue management model you will need
some training stories, domain file and model configuration. You can also create custom actions which,
when predicted, can call an API, retrieve data from the database or perform some other integrations.

#### Create training stories
The file `./data/stories.md` already contains some training stories. Add a new example story to cover
new dialogue turn.

#### Update the domain
A file called `domain.yml` contains the domain configuration of your assistant. It contains all the 
information an assistant needs to know to operate. Update the domain with your previously created `intents`
and `entities` as well as `slots`. Also, if you like, you can add new example responses to the templates. 

#### Create model configuration
A file `config.yml` also contains the configuration of the dialogue model. You can test the performance
of [different policies](http://rasa.com/docs/rasa/core/policies/) too. 

#### Train the dialogue model
Train the dialogue model by running:

`rasa train core`

Once the model is trained you can talk to your bot by running:

`rasa shell`

Rasa also comes with handy functions which allow to visualize training stories. To do that, run:

`rasa visualize`

## 3. Close the feedback loop with Rasa X
After you build and test a simple version of your assistant, it's important to give it to the
actual users, collect the feedback from them and improve your assistant continuously. 

#### Use Rasa X to improve your assistant
The best way to improve your assistant using real conversational data is using Rasa X. In this repository,
you will find files called `rasa.db` and `tracked.db` which already contain a few real-world conversations
between our bot and the users. We will reuse them to improve the assistant using the Rasa X. Start your 
assistant with Rasa X using:

`rasa x`

In the `Conversations` tab of the Rasa X you will find existing conversations between users and your assistant.
Correct them using interactive learning and add them to the training data.

Hit the button `Train` to retrain the model and select a newly trained one inside the `Models` tab of the Rasa X UI.

Test the improved assistant by talking to it inside the `Talk to your bot` tab of the Rasa X UI or share it with 
your friends by generating and sharing a link to your bot inside the `Conversations` tab. All conversations that new
generate with your assistant will end up in `Conversations` tab for you to look into and reuse to improve your assistant.

#### Expose your assistant to the outside world 
To share your assistant with friends, you will have to expose your locally running assistant to the outside world.
To do that, you can deploy your assistant on a server, or use ngrok (recommended for non-production environments only).
To do that, start ngrok by running:

`ngrok http 5002`

Copy the ngrok URL and run:

`export RASA_X_HOSTNAME=https://xxxxxx.ngrok.io; rasa x`

Once the Rasa X launches, you should be able to share your assistant with your friends around the world!

## Next steps

There is so much you can do to take this assistant to the next level (or build your own from scratch). Here are
some ideas for you of what you can do:

- Implement backend integrations using [custom actions](http://rasa.com/docs/rasa/core/actions/#custom-actions)
- Create new intents, entities and write new training stories to handle more advanced use cases.
- Connect your assistant to the most popular [messaging platforms](http://rasa.com/docs/rasa-x/get-feedback-from-test-users/#testing-channel-integrations).

