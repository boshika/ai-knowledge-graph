#ai-concepts 

PARAMETER EFFICENT FINE_TUNING

 ==**What PEFT does:**==

==Freezes most of the model and only trains a **small subset of parameters** — getting similar results at a fraction of the cost.==

**PEFT METHODS**

| Method | How it works |
|---|---|
| **LoRA** | Injects small trainable matrices into layers |
| **QLoRA** | LoRA + quantization for even less memory |
| **Prefix Tuning** | Adds trainable tokens to the input |
| **Prompt Tuning** | Learns soft prompts instead of changing weights |
| **Adapter Layers** | Inserts small trainable modules between layers |

[[LoRA and QLoRA]]