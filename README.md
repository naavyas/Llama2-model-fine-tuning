# Llama2-model-fine-tuning
 This projects uses a custom Huggingface data set to fine tune the LLama2 model using LoRA and peft techniques thus training the LLM to answer prompts with increased specificity. 

 The following steps are followed through the process of fine tuning - 
 - Imports and loading the hugging face data set
 - After this the data set is converted to the system input format the LLM would use. This is done with the help of the code mentioned in this collab notebook : [(https://colab.research.google.com/drive/1Ad7a9zMmkxuXTOh1Z7-rNSICA4dybpM2?usp=sharing)]
 - We then start setting up for the LoRA finetuning step. To better understand this concept we can refer to the official documentation released by microsoft. In brief - we know that A good prompt is imp for LLMs, so to specialize them for a task we fine tune them on smaller datasets. The main problem in fine tuning is the size (its way too big and the space is an issue). With LoRA instead of modifying all the models weights we freeze some of the weights. In this way we double the parametrs on our hard drive but not on the GPU. Thus solving the space problem. LoRA reduces the no. of trainable parameters.
 - We then load the tokenizer and model with QLoRA conifiguration
 - After checking with GPU compatibility we can load the base model and set the supervised fine tuning parameters.
 - After training the model we then test it with a custom input to check its precision and then push the model to hugging face hub
