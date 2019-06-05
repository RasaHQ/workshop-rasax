## new rasa user
* greet
  - utter_greet
* deny
  - utter_docs

## existing rasa user 1
* greet
  - utter_greet
* affirm
  - utter_ask_name
* name{"name":"Tom"}
  - utter_ask_location
* location{"location":"Berlin"}
  - utter_send_blog
  - utter_ask_feedback
* feedback
  - utter_thanks

## existing rasa user 2
* greet
  - utter_greet
* affirm
  - utter_ask_name
* name{"name":"Tom"}
  - utter_ask_location
* location{"location":"Berlin"}
  - utter_send_blog
  - utter_ask_feedback
* feedback
  - utter_thanks
* goodbye
  - utter_goodbye

