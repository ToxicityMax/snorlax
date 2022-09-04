# Snorlax - Thapar admission bot using Rasa

## 👷‍ Installation

To install Sara, please clone the repo and run:

```sh
cd rasa-demo
make install
```

This will install the bot and all of its requirements.
Note that this bot should be used with python 3.6 or 3.7.


## 🤖 To run Sara:

Use `rasa train` to train a model (this will take a significant amount of memory to train,
if you want to train it faster, try the training command with
`--augmentation 0`).

Then, to run, first set up your action server in one terminal window:
```bash
rasa run actions --actions actions.actions
```

## 👩‍💻 Overview of the files

`data/core/` - contains stories 

`data/nlu` - contains NLU training data

`actions` - contains custom action code

`domain.yml` - the domain file, including bot response templates

`config.yml` - training configurations for the NLU pipeline and policy ensemble


## Development

To install requirements for development, run:

```sh
make install-dev
```

To run custom actions locally, put a file called .env in the root of your local directory with values
for the following environment variables. Most actions will work without them, but if you are working on actions
connecting to external APIs you will need credentials.


```
GDRIVE_CREDENTIALS=#json access key for Google Drive API for action_submit_sales_form
MAILCHIMP_LIST=#id of mailchimp list for action_submit_subscribe_newsletter_form
MAILCHIMP_API_KEY=#api key for mailchimp
ALGOLIA_APP_ID=#algolia app ID for action_docs_search 
ALGOLIA_SEARCH_KEY=#algolia search key
ALGOLIA_DOCS_INDEX=#algolia search index
RASA_X_HOST=#Rasa X domain e.g. localhost:5002
RASA_X_PASSWORD=#password for authenticating into Rasa X
RASA_X_USERNAME=#username for authenticating into Rasa X
RASA_X_HOST_SCHEMA=#Rasa X address schema (http/https)
```
