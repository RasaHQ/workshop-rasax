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

## say goodbye
* goodbye
  - utter_goodbye

## Story from conversation with ea16abf2-0f58-41ff-8677-5d43556bf40e on May 23rd 2019

* greet
    - utter_greet
* affirm
    - utter_ask_name
* name{"name":"Juste"}
    - slot{"name":"Juste"}
    - utter_ask_location
* location
    - utter_send_blog
* thanks

## Story from conversation with ae4661b5-b89d-4908-9d2d-bf19d2426646 on May 23rd 2019

* greet
    - utter_greet
* affirm
    - utter_ask_name
* name{"name":"Sam"}
    - utter_ask_location
* location
    - utter_send_blog
