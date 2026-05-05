#ai-concepts 

PARAMETER EFFICENT FINE_TUNING

 ==**What PEFT does:**==

==Freezes most of the model and only trains a **small subset of parameters** — getting similar results at a fraction of the cost.==

**PEFT METHODS**

| Method                                   | How it works                                                    |
| ---------------------------------------- | --------------------------------------------------------------- |
| **LoRA**                                 | Injects small trainable matrices into layers                    |
| **QLoRA**                                | LoRA + quantization for even less memory                        |
| **Prefix Tuning**                        | Adds trainable tokens to the input                              |
| **Prompt Tuning**                        | Learns soft prompts instead of changing weights                 |
| **Adapter Layers**                       | Inserts small trainable modules between layers                  |
| Technique                                | What it does                                                    |
| **Full fine-tuning**                     | Update all model weights on your dataset                        |
| **LoRA**                                 | Train small low-rank adapter matrices, freeze base model        |
| **QLoRA**                                | LoRA on a 4-bit quantized model — very memory efficient         |
| **Instruction tuning**                   | Train on instruction-response pairs to follow directions better |
| **RLHF**                                 | Human feedback shapes model behaviour via reward model          |
| **DPO (Direct Preference Optimisation)** | Simpler alternative to RLHF, no reward model needed             |
| **Prefix tuning**                        | Learn soft prompt tokens prepended to every input               |
| **Adapter layers**                       | Insert small trainable modules between frozen layers            |
| **ORPO**                                 | Fine-tune and align in a single training pass                   |

[[LoRA and QLoRA]]