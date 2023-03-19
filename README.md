# GPT-2 Text Generation API
This is a Python project that uses the GPT-2 model from Hugging Face to generate text based on a given prompt. It includes two parts: fine-tuning the GPT-2 model on a specific dataset, and building a FastAPI app to generate text using the fine-tuned model.
## Fine-tuning the GPT-2 model
The code for fine-tuning the GPT-2 model is in the train_model.py file. It uses the TextDataset and DataCollatorForLanguageModeling classes from the Hugging Face transformers library to load and prepare the training data. The TrainingArguments and Trainer classes are used to specify and run the training process. The resulting fine-tuned model is saved to disk using the save_pretrained method.
## Generating text using the fine-tuned model
The code for generating text using the fine-tuned model is in the app.py file. It uses the FastAPI web framework to create a web server that listens for requests and returns generated text. The GPT2LMHeadModel and GPT2Tokenizer classes from the Hugging Face transformers library are used to load the fine-tuned model and tokenizer from disk. The GenerateTextRequest and GenerateTextResponse classes are used to define the request and response body schemas. The generate_text function is the endpoint that handles POST requests to generate text based on a given prompt.

## Usage
To use this project, you can follow these steps:

Install the required Python packages listed in the requirements.txt file.

Run the train_model.py file to fine-tune the GPT-2 model on your own dataset.

After the fine-tuning is complete, run the app.py file to start the web server.

Send a POST request to the /generate_text endpoint with a JSON body containing a prompt field to generate text based on the prompt.

The generated text will be returned in the response body. You can customize the max_length and temperature parameters in the app.py file to control the length and creativity of the generated text.

Note: Make sure to specify the correct paths for the fine-tuned model and tokenizer in the app.py file before running it.

