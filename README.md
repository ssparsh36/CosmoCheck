# CosmoCheck
CosmoCheck is a system for detecting real vs. LLM-manipulated space research summaries. It uses NLI with Chain-of-Thought prompting and structured form-filling via the Groq API, combined with entity, numeric, and factual consistency checks for robust pairwise classification.


CosmoCheck

Detecting Real vs. LLM-Manipulated Space Research Summaries

CosmoCheck is a system designed to classify authentic vs. manipulated summaries in space-domain documents. It uses a combination of Natural Language Inference (NLI) via the Groq API, Chain-of-Thought (CoT) reasoning, and structured form-filling to detect factual inconsistencies and hallucinations in LLM outputs.

Features

Pairwise Classification: Identifies the real summary in a document pair.

NLI + CoT Reasoning: Uses entailment and contradiction signals to detect manipulation.

Structured Form-Filling: Extracts entity, numeric, and technical consistency features.

Robust Detection: Handles noisy, adversarial, or partially corrupted summaries.

High Accuracy: Achieved 0.91 pairwise accuracy on evaluation sets.

Installation
git clone https://github.com/yourusername/CosmoCheck.git
cd CosmoCheck
pip install -r requirements.txt

Usage
from cosmocheck import CosmoCheck

# Initialize CosmoCheck
model = CosmoCheck(api_key="YOUR_GROQ_API_KEY")

# Classify a document pair
label, confidence, explanation = model.predict(file1="summary1.txt", file2="summary2.txt")

print(f"Real Summary: {label}, Confidence: {confidence}")
print("Explanation:", explanation)

How it Works

Input: Two summaries of the same source document.

NLI Evaluation: Each pair is processed using Groq API with Chain-of-Thought prompts.

Feature Extraction: Entity, numeric, factual, and technical checks are performed.

Classification: Combines NLI outputs and features to select the authentic summary.

Output: Real summary label, confidence score, and reasoning explanation.
