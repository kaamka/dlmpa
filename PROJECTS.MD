## Project Guidelines

### Team structure
- Projects should be completed in pairs.  
- In justified cases, individual or three-person teams may be allowed.  
- In multi-person teams, responsibilities should be clearly defined (who worked on what).

### Project scope
Topics are flexible, but must relate to **deep learning and/or CUDA**.

Two main directions are recommended:

- **Deep Learning focus**  
  Extend topics covered in class (e.g., classification, generative models) with significantly deeper analysis, more complex datasets, or more advanced architectures. You may also explore entirely new DL problems.

- **Systems / CUDA focus**  
  Work on performance optimization (e.g., GPU acceleration, CUDA). This may include re-implementing or optimizing known models, or using frameworks beyond standard PyTorch (e.g., PyTorch Lightning or others).

If you do not have a project idea, feel free to contact me or request a list of suggested topics.

### Project directions (more detailed)

These are example directions to help you get started. Your final project should be more specific and clearly defined.

#### 1. Applied Deep Learning
- Train and evaluate models on more realistic datasets (ImageNet subsets, text datasets, time series datasets)
- Compare architectures (e.g., CNN vs Vision Transformer, RNN vs Transformer)
- Investigate failure cases and model interpretability
- Build a robust training pipeline (data augmentation, regularization, hyperparameter tuning)

#### 2. Generative Models
- Implement and compare generative approaches (VAE, GAN, diffusion — simplified versions acceptable)
- Study latent space structure and controllability
- Conditional generation (e.g., class-conditional or text-conditioned models)
- Evaluate generation quality (quantitatively or qualitatively)

#### 3. Systems & Optimization (CUDA-focused)
- Optimize training or inference speed (profiling, batching, mixed precision)
- Implement or analyze GPU acceleration techniques
- Compare performance across frameworks (e.g., PyTorch vs PyTorch Lightning)
- Memory optimization and scaling experiments
- Study and compare multi-gpu Pytorch wrappers (Pytorch Lightning/HuggingFace Accelerate)

#### 4. Edge / Efficient AI
- Deploy a model on constrained hardware (e.g., Raspberry Pi)
- Model compression: pruning, quantization, distillation
- Measure latency vs accuracy trade-offs
- Design lightweight architectures for real-time inference

#### 5. Research / Exploration (optional)
- Apply deep learning to a scientific or technical problem
- Reproduce and analyze a selected research paper
- Explore unconventional or interdisciplinary ideas

### Submission - fill the form:
> [Project Topics](https://forms.office.com/e/JcyP1U5iDj?origin=lprLink)

One person per team should submit:
- Project title  
- Short description  
- Full list of team members (including the submitter)  
- Link to a GitHub repository (it can be empty at this stage)

Repositories should be created early. They will not be monitored during development but will be used for final evaluation.

### Timeline
- Define your project topic by **next week** (21.05.2026)
- I will send you an e-mail with confirmation of the topic until 28.05.2026

Project meetings:
- **Midpoint meeting** - short progress update presentation (11.06.2026)
- **Projects deadline submission** - (22.06.2026) 
- You should deliver code with a detailed documentation and conclusions (repository)

### Final evaluation
- **Documentation** (it can be either README file in your repo or a separate document or even just a Jupyter Notebook if well strucured and documented)
- **Code quality**
- **Conclusions** - important!