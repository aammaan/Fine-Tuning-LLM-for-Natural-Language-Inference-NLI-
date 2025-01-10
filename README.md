# README: Fine-Tuning a Large Language Model (LLM) using QLoRA

## Overview
This project focuses on fine-tuning the **Phi2 Model** from Hugging Face using **QLoRA** for the task of **Natural Language Inference (NLI)**. The process involves training the model on the **SNLI dataset**, saving checkpoints after every epoch, and evaluating the model's performance against the pretrained baseline.

---

## Dataset
- **Dataset Name:** SNLI (Available on Hugging Face).  
- **Training Data:** 1,000 samples (every 550th sample from a total of 550k).  
- **Validation Data:** 100 samples (every 100th sample from a total of 10k).  
- **Testing Data:** 100 samples (every 100th sample from a total of 10k).  

---

## Model Details
- **Model Name:** Phi2 (Hugging Face).  
- **Fine-Tuning Technique:** QLoRA (Quantized LoRA).  

---

## Tasks
### **1. Fine-Tuning the Model**
- Train the model for **5 epochs**.  
- Save model checkpoints after each epoch and the final trained model for evaluations.  

### **2. Evaluation Criteria**
Your report must include:  
1. **Accuracy Comparison:** Pretrained vs. fine-tuned model performance on the test set.  
   - Pretrained Accuracy: **29%**  
   - Fine-Tuned Accuracy: **75%**  
2. **Time Taken for Fine-Tuning:** Total time spent across all 5 epochs (**741 seconds**).  
3. **Parameter Count:**  
   - Total Parameters: **1,408,634,880**  
   - Trainable Parameters: **18,357,760**  
4. **Resource Utilization:**  
   - **GPU:** NVIDIA T4  
   - **Memory:**  
     - GPU Utilization: **16.106 GB**  
     - RAM Utilization: **4.303 GB**  
     - Peak CPU: **8%**  
     - Disk Utilization: **56 GB**  
5. **Failure Cases Analysis:**  
   - **Corrected Cases:** Examples where fine-tuning improved contextual understanding.  
   - **Unresolved Cases:** Instances where the fine-tuned model still misclassified due to dataset or architecture limitations.  

---

## Example Failure Cases  
### **Corrected by Fine-Tuned Model**  
- **Example:** Misclassified "The dog chased the cat" as a contradiction with "The cat chased the dog."  
  - **Fine-Tuned Model Result:** Correctly identified as a contradiction.  

### **Not Corrected by Fine-Tuned Model**  
- **Example:** Misclassified "A man is walking a dog" as entailment with "A man is playing with a cat."  
  - **Reason:** Limited exposure to similar examples during training or architecture constraints.  

---


## Notes  
- Always debug on **CPU runtime** before switching to **GPU** in Colab.  
- Save checkpoints after every epoch to ensure reproducibility.  
- Use additional references to understand LoRA and QLoRA concepts better.  

---

## Conclusion  
Fine-tuning the **Phi2 Model** with QLoRA achieved significant improvements, increasing accuracy by **46%** and resolving multiple failure cases. However, unresolved cases highlight the need for further exploration of architecture limitations and training data enhancements.  
