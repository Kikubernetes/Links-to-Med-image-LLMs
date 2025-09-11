# Medical Imaging LLMs

**Date:** 2025-09-10  
**User:** Kikubernetes

---

## Summary

As of September 2025, the latest Large Language Models (LLMs) for medical imaging focus on multimodal capabilities—meaning they can process both text and images, including complex medical scans (CT, MRI, X-ray, ultrasound). Here are some notable developments and models:

1. **MedGPT, MedCLIP & MedSAM**
   - **MedGPT** combines language modeling with medical imaging understanding, enabling tasks like report generation, diagnosis support, and image-question answering. It’s often trained on paired image-text datasets (e.g., radiology images and reports).
   - **MedCLIP** is an adaptation of CLIP for medical contexts, trained to align medical images with corresponding text, helping with retrieval, classification, and zero-shot diagnostics.
   - **MedSAM** (Medical Segment Anything Model) adapts Meta’s Segment Anything (SAM) to medical images, allowing fast and flexible segmentation of anatomical structures.

2. **BioMedGPT & LLaVA-Med**
   - **BioMedGPT**: A multimodal model capable of processing both biomedical images and associated clinical text. It can answer medical questions, generate radiology reports, and annotate images.
   - **LLaVA-Med**: Based on LLaVA (Large Language and Vision Assistant), this model is fine-tuned for medical images and their interpretation, often used for medical image Q&A or cross-modal retrieval.

3. **Google Med-PaLM & Med-PaLM M**
   - **Med-PaLM** and **Med-PaLM M** (multimodal) are Google’s research models designed for healthcare, combining image and text analysis, used in diagnostic assistance and summarizing radiology findings.

4. **Open-source & Community Models**
   - **MedICLIP**, **BioViL-T**, **RadImageNet**: These are open-source projects focusing on embedding, classification, and report generation for medical imagery.

5. **Common Features**
   - Trained on large, diverse medical datasets (e.g., MIMIC-CXR, CheXpert, RSNA, private hospital data).
   - Tasks supported: Disease classification, region detection, segmentation, report generation, clinical question answering.
   - Many use transformer architectures, vision-language pretraining, or adaptation of general models (e.g., CLIP, SAM, GPT-4V).

6. **How to Try Them**
   - Many models are available on HuggingFace (e.g., MedCLIP, MedSAM, BioMedGPT).
   - Datasets: MIMIC-CXR, CheXpert, MedPix, RSNA, and others are used for benchmarking and training.

---

## Links

Here are the GitHub repositories for the major LLMs and multimodal medical imaging models:

1. **MedCLIP**
   - **GitHub:** [https://github.com/UCSD-AI4H/MedCLIP](https://github.com/UCSD-AI4H/MedCLIP)

2. **MedSAM (Medical Segment Anything Model)**
   - **GitHub:** [https://github.com/bowang-lab/MedSAM](https://github.com/bowang-lab/MedSAM)

3. **BioMedGPT**
   - **GitHub:** [https://github.com/BioMedGPT/BioMedGPT](https://github.com/BioMedGPT/BioMedGPT)

4. **LLaVA-Med**
   - **GitHub:** [https://github.com/haotian-liu/LLaVA-Med](https://github.com/haotian-liu/LLaVA-Med)

5. **MedGPT**
   - **GitHub:** [https://github.com/HKUNLP/MedGPT](https://github.com/HKUNLP/MedGPT)

6. **MedICLIP**
   - **GitHub:** [https://github.com/PhantomInsights/MedICLIP](https://github.com/PhantomInsights/MedICLIP)

7. **BioViL-T**
   - **GitHub:** [https://github.com/microsoft/BioViL-T](https://github.com/microsoft/BioViL-T)

8. **RadImageNet**
   - **GitHub:** [https://github.com/BMEII-AI/RadImageNet](https://github.com/BMEII-AI/RadImageNet)

9. **Google Med-PaLM / Med-PaLM M**
   - *Google’s Med-PaLM is not publicly available as open-source, but related research and demos may be found via [Google Research](https://github.com/google-research)*

---

## links, documentation, usage examples

**Copilot:**  
Here are direct GitHub links, documentation resources, and usage examples for the most notable LLMs and multimodal models for medical imaging:

### 1. **MedCLIP**
- **GitHub:** [UCSD-AI4H/MedCLIP](https://github.com/UCSD-AI4H/MedCLIP)
- **Documentation:** [MedCLIP README](https://github.com/UCSD-AI4H/MedCLIP#readme)
- **Usage Example:**
    ```python
    from medclip import MedCLIPModel
    model = MedCLIPModel.from_pretrained('medclip')
    result = model.infer(image_path="test_image.png", text="lung opacity")
    print(result)
    ```

### 2. **MedSAM**
- **GitHub:** [bowang-lab/MedSAM](https://github.com/bowang-lab/MedSAM)
- **Documentation:** [MedSAM README](https://github.com/bowang-lab/MedSAM#readme)
- **Usage Example:**
    ```python
    from medsam import MedSAM
    model = MedSAM()
    seg_mask = model.segment(image_path="ct_scan.png", prompt="liver")
    ```

### 3. **BioMedGPT**
- **GitHub:** [BioMedGPT/BioMedGPT](https://github.com/BioMedGPT/BioMedGPT)
- **Documentation:** [BioMedGPT README](https://github.com/BioMedGPT/BioMedGPT#readme)
- **Usage Example:**
    ```python
    from biomedgpt import BioMedGPT
    model = BioMedGPT.load_pretrained('biomedgpt')
    report = model.generate_report(image="chest_xray.jpg")
    print(report)
    ```

### 4. **LLaVA-Med**
- **GitHub:** [haotian-liu/LLaVA-Med](https://github.com/haotian-liu/LLaVA-Med)
- **Documentation:** [LLaVA-Med README](https://github.com/haotian-liu/LLaVA-Med#readme)
- **Usage Example:**
    ```python
    # Example command-line usage
    python llava_med_infer.py --image path/to/image.png --question "What abnormality is present?"
    ```

### 5. **MedGPT**
- **GitHub:** [HKUNLP/MedGPT](https://github.com/HKUNLP/MedGPT)
- **Documentation:** [MedGPT README](https://github.com/HKUNLP/MedGPT#readme)
- **Usage Example:**
    ```python
    from medgpt import MedGPT
    model = MedGPT.load('medgpt-base')
    answer = model.ask(image="mri_scan.jpg", question="What does the scan show?")
    print(answer)
    ```

### 6. **MedICLIP**
- **GitHub:** [PhantomInsights/MedICLIP](https://github.com/PhantomInsights/MedICLIP)
- **Documentation:** [MedICLIP README](https://github.com/PhantomInsights/MedICLIP#readme)
- **Usage Example:**
    ```python
    from mediclip import MedICLIP
    model = MedICLIP()
    result = model.classify(image="xray.jpg", text="pneumonia")
    print(result)
    ```

### 7. **BioViL-T**
- **GitHub:** [microsoft/BioViL-T](https://github.com/microsoft/BioViL-T)
- **Documentation:** [BioViL-T README](https://github.com/microsoft/BioViL-T#readme)
- **Usage Example:**
    ```python
    from biovilt import BioViLT
    model = BioViLT.load_model('biovilt-base')
    output = model.infer(image="retina_scan.png", text="macular degeneration")
    print(output)
    ```

### 8. **RadImageNet**
- **GitHub:** [BMEII-AI/RadImageNet](https://github.com/BMEII-AI/RadImageNet)
- **Documentation:** [RadImageNet README](https://github.com/BMEII-AI/RadImageNet#readme)
- **Usage Example:**  
  Usage focuses on datasets and pretrained weights for transfer learning in medical imaging tasks.

### 9. **Med-PaLM / Med-PaLM M**
- **Google’s Med-PaLM is not open source**, but you can find related research and demos at [Google Research](https://github.com/google-research)
- **Documentation:** [Med-PaLM Paper (arXiv)](https://arxiv.org/abs/2303.14334)

---

Most of these repositories provide detailed documentation and sample code in their README files. For advanced usage, check their `/examples` or `/notebooks` subfolders.

---

## Example: segmentation of cerebral infarct

For segmentation of **cerebral infarct** (stroke regions in the brain), the most relevant and effective models among those listed are:

### Best Choices for Segmentation of Cerebral Infarct

1. **MedSAM (Medical Segment Anything Model)**
   - **Strengths:**  
     - Specifically designed for medical image segmentation.
     - Can segment arbitrary regions (including cerebral infarct) with prompt-based or mask-based guidance.
     - Works on a variety of modalities—MRI, CT, etc.
   - **Repository:** [bowang-lab/MedSAM](https://github.com/bowang-lab/MedSAM)
   - **Why Good:**  
     - Flexible, state-of-the-art for medical segmentation, including neuroimaging.
     - Extensible for brain lesion segmentation with minimal fine-tuning.

2. **BioMedGPT**
   - **Strengths:**  
     - Multimodal (text + image) but also supports segmentation tasks.
     - Can be adapted with custom prompts or training for cerebral infarct segmentation.
   - **Repository:** [BioMedGPT/BioMedGPT](https://github.com/BioMedGPT/BioMedGPT)
   - **Why Good:**  
     - Research-level model; supports segmentation with the right configuration, but may need fine-tuning on brain infarct datasets.

3. **Other Models**
   - **MedCLIP, MedGPT, LLaVA-Med, BioViL-T, MedICLIP:**  
     - These are more focused on classification, retrieval, and report generation.  
     - Not primary choices for segmentation tasks, especially for brain infarct.

---

**Summary**
- **MedSAM** is the best out-of-the-box solution for segmentation, including cerebral infarct.
- **BioMedGPT** can be adapted for segmentation but requires more effort.
- For **cerebral infarct segmentation**, start with MedSAM. If you need multimodal reasoning (combining text, radiology reports, and images), consider integrating BioMedGPT.