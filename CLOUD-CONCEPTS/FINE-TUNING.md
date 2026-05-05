
Fine tuning is a good alternative to Prompt Engineering.
Doing this can save token in the long run

Example Application
- Chatbot with certain personality
- Training with proprietary data
- Training on most recent data then what the LLM was trained on

In Bedrock it is called "Custom Models"

CUSTOM MODEL TRAINING
Titan, Cohere and Meta models can be fine-tuned. 

TECHNIQUE
Provide labeled pairs of prompts and answers/Q&A. Upload training data to S3
Can also do something similar with image and captions

For sensitive data - Use VPC with PrivateLink. THIS CAN GET EXPENSIVE!

CONTINUED PRE_TRAINING
Feeding raw data, don't need prompts

Popular technique: [[LoRA]]

Addtional
[[RAG vs FINE-TUNING vs PROMPT ENGINEERING vs Long Context]]
