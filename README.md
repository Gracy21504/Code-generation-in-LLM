Improving Code Generation in Large Language Models through Parameter-Efficient Fine
Tuning - Transcript 
Task 1 Video Transcript (LLM Fine-Tuning Project) 
Introduction  
In this project, I focus on improving code generation using Large Language Models through 
parameter-efficient fine-tuning techniques. 
The goal is to enhance the performance of a pre-trained model for generating Python code 
while working under limited computational resources. 
Dataset and Problem  
The task is instruction-based code generation, where the model generates Python code from a 
natural language prompt. 
For this, I used the CodeXGLUE dataset, which contains real-world code and corresponding 
descriptions. 
The dataset was formatted into instruction-input-output pairs and split into training, validation, 
and test sets. 
Model Selection 
The base model used is TinyLlama-1.1B, which is a lightweight language model suitable for 
training on limited hardware. 
Initially, I evaluated the baseline model without any fine-tuning. The outputs were often 
incomplete and lacked logical correctness. 
Methodology 
To improve performance, I applied parameter-efficient fine-tuning techniques. 
First, I used LoRA, which updates only a small subset of parameters instead of the full model. 
This reduces memory usage and training cost. 
Then, I implemented QLoRA using the BitsAndBytes library, which further reduces memory 
usage by applying 4-bit quantization. 
Due to hardware limitations—specifically using a Google Colab T4 GPU—full fine-tuning was not 
feasible, as it typically requires more than 100GB of GPU memory. 
Experimental Setup 
The model was trained using PyTorch and the Transformers library from Hugging Face. 
Key parameters include: 
• Batch size of 1 
• Learning rate of 2e-4 
• 1 training epoch 
• Gradient accumulation for efficiency 
Evaluation was done using BLEU and ROUGE-L metrics. 
Results  
The results show clear improvement across models. 
The baseline model produced incorrect or incomplete code. 
The LoRA model improved structure and correctness. 
The QLoRA model performed the best, generating optimized and accurate code. 
For example, when asked to generate a prime-check function: 
• The baseline model produced incorrect logic 
• LoRA improved correctness 
• QLoRA generated an optimized solution using square root logic 
This demonstrates that QLoRA achieves the best balance between performance and efficiency. 
Discussion and Limitations  
Although the results are promising, there are some limitations: 
• Small dataset size 
• Limited training epochs 
• No execution-based evaluation 
Future work could include larger datasets and reinforcement learning-based fine-tuning. 
Ethical Considerations  
This work also considers ethical aspects such as: 
• Risk of generating insecure code 
• Academic misuse 
• Licensing issues 
Therefore, human validation is essential before real-world deployment. 
Conclusion 
In conclusion, parameter-efficient fine-tuning methods like LoRA and QLoRA significantly 
improve code generation while being computationally efficient. 
