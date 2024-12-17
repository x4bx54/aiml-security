# AIML Threats & Mitigations
This page will cover the common threats and mitigation recommendations that can better aid in the secure design of your AIML system. 

![Threat_Overview](https://github.com/user-attachments/assets/9ea4a8ae-142f-4020-8abc-e2b0cdfb854f)

From a secure design perpsective, it is best to apply a zero-trust principle on the AIML model - Always validate and sanitize all inputs to the model and outputs from the model. 

### 1. Poisoned Model & Poor Model Selection
**Issue 1**: A model taken from public source (e.g., HuggingFace) may contain backdoor or malicious code. Attackers often target such public sources as it offers a greater reach to end users globally, thus increasing their chance of successful exploitation. 

Solution:
1. Obtain and validate information on the development of the model (i.e., Model Cards - Training data used, Model fingerprint/watermark, Adversarial defence capabilities). 
2. Undergo the necessary code/model scanning in your security pipeline
3. Implement observability measures to monitor all inputs and outputs to/from the model, anomalies in returned results from the model or user behaviour activities.

**Issue 2**: Even if a model was developed internally, a malicious insider may manipulate the behaviour of the AI/ML model itself or its input and/or output logic by altering the AI/ML models parameter. The attacker does this in order to disrupt the capability of the model - either to implant bypass methods or instructing the model to return inaccurate results back to the end users.

Solution:
1. Similar solution to issue 1.
2. Ensure that the necessary authorisation (e.g., RBAC) is configured for all users of the system.
3. Ensure there is version control for codes, model and data versioning / backup mechanisms to track all changes and revert when necessary
4. Set alert triggers and monitor anomalies. 

**Issue 3**: Teams may be inclined to train or/and use big models with a wealth of knowledge and information that are (pre) trained to the model. However, with more information intact, it presents a higher likelihood of information being disclosed to the end users. 

Solution: 
1. Limit the domain - Where possible, start with a smaller, less general purpose foundational model.
2. Use Benchmarked Foundation Model - Prefer the usage of supplier/vendor furnished foundation models that have undergone academic or industry benchmarking, demonstrating its robustness and securiy to mitigate the risk of security vulnerabilities exploitation.


### 2. Data Poisoning
Data poisoning applies to the data used for training the model or fine-tuning the model

### 3. Prompt Injection, Hallucinations, Model Denial-of-Service, Denial-of-Wallet

### 4. Output Handling

### 5. Excessive Agency 

## Useful Resources
+ https://atlas.mitre.org/
+ https://owasp.org/www-project-top-10-for-large-language-model-applications/
+ https://owasp.org/www-project-machine-learning-security-top-10/
  
