# Rad-VLSM

**Semantic-to-Spatial Prompt Reliability Learning**

Official repository for **Rad-VLSM: A Cross-Modal Framework with Semantics-Assisted Prompting for Medical Segmentation and Diagnosis**.

📄 Paper: [arXiv:2605.18130](https://arxiv.org/abs/2605.18130)

---

## 🔓 Data & Code Availability

* **Code Release:** The complete PyTorch implementation of Rad-VLSM is currently being cleaned, organized, and anonymized for public release.

* **Dataset Release:** The de-identified ultrasound dataset, lesion masks, diagnostic labels, and official experimental splits are being prepared for academic open-source release.

* **Reproducibility Commitment:** To support transparent and reproducible research, we will release the core model architecture, training and inference routines, evaluation protocols, and necessary configuration files once the repository is fully organized.

---

## 📢 News & Status

* **[2026/06]** 🚀 **The Rad-VLSM code and dataset are currently being organized for open-source release. They will be fully uploaded very soon! Stay tuned and welcome to Star this repository.**

---

## 📌 About

Medical ultrasound images are often affected by weak lesion boundaries, low contrast, speckle noise, acoustic shadows, and surrounding tissue interference, making reliable lesion localization and diagnosis highly challenging. Existing methods either rely on manually specified prompts, unstable single visual responses, or direct text-conditioned prediction, which may lead to unreliable localization or diagnosis based on non-lesion evidence.

To address these limitations, this project introduces **Rad-VLSM**, a cross-modal medical segmentation and diagnosis framework with semantics-assisted prompting. The core idea is **Semantic-to-Spatial Prompt Reliability Learning**: clinical semantics are first used to guide lesion-aware spatial prompt generation, and then multiple candidate prompts are evaluated and aggregated according to their reliability.

* **Semantic-to-Spatial Prompting:** Rad-VLSM aligns clinical morphology semantics with lesion visual patterns and uses the learned semantic prior to guide automatic spatial prompt generation.

* **Automatic Prompt Generation:** During inference, Rad-VLSM does not require manually annotated boxes, points, contours, class-specific text, or image-specific reports. A fixed class-agnostic prompt is used to generate lesion-aware candidate prompts automatically.

* **Prompt Reliability Learning:** To avoid the instability of single-response localization, Rad-VLSM generates multiple candidate lesion regions and evaluates their reliability using CAM-response strength, cross-modal semantic consistency, and self-distilled mask consistency.

* **SAM-Based Multi-Task Learning:** The refined candidate prompts are fed into a SAM-based multi-task framework for fine-grained lesion segmentation and benign/malignant diagnostic prediction.

* **Mask-Grounded Visual-Radiomics Fusion:** Rad-VLSM extracts radiomics descriptors from the predicted lesion mask and fuses them with lesion-level visual evidence, improving the interpretability and clinical relevance of diagnosis.

* **Generalizable Medical Lesion Segmentation:** Beyond breast ultrasound diagnosis, Rad-VLSM is designed to support broader medical lesion segmentation scenarios and will be evaluated on multiple public medical image benchmarks.

---

## 🧠 Core Idea

The central idea of Rad-VLSM is to shift medical image diagnosis from **global image-level recognition** to **lesion-grounded evidence learning**.

Rather than directly classifying the whole ultrasound image, Rad-VLSM first focuses on where the lesion is, then determines which candidate prompts are reliable, and finally performs diagnosis based on localized visual evidence and explicit radiomics features.

In short:

```text
Clinical morphology semantics
        ↓
Semantic-guided lesion focusing
        ↓
Automatic multi-candidate prompt generation
        ↓
Prompt reliability learning
        ↓
MCRA-based reliable prompt aggregation
        ↓
SAM-based fine-grained lesion segmentation
        ↓
Mask-grounded visual-radiomics diagnosis
```

---

## 🧩 Main Contributions

* We propose a **semantic-to-spatial prompt learning framework** that converts clinical semantics into lesion-level spatial evidence without requiring manual prompts at inference time.

* We design a **prompt reliability learning strategy** to suppress unreliable candidate prompts caused by speckle noise, acoustic shadows, and surrounding tissue interference.

* We introduce a **multi-candidate region aggregation mechanism** that fuses candidate-level masks, diagnostic logits, and region embeddings according to reliability weights.

* We develop a **mask-grounded visual-radiomics fusion mechanism**, enabling the final diagnosis to be supported by both deep visual representations and explicit medical descriptors.

* We will release the **de-identified dataset, source code, and reproducibility files** to facilitate future research on medical lesion segmentation and ultrasound diagnosis.

---

## 📄 Citation

If you find this project useful for your research, please consider citing our paper:

```bibtex
@article{zhang2026radvlsm,
  title={Rad-VLSM: A Cross-Modal Framework with Semantics-Assisted Prompting for Medical Segmentation and Diagnosis},
  author={Zhang, Fengyi and Zeng, Xujie and Liu, Mohan and Wang, Zengyi and Jiang, Yalong},
  journal={arXiv preprint arXiv:2605.18130},
  year={2026}
}
```

---

## 📬 Contact

For questions, suggestions, or collaboration, please contact the authors through GitHub Issues or email.

More details will be released soon.
