# Comparing Vision Transformers to Traditional Deep Learning Object Classification Architectures for Automotive Make and Model Recognition

<img width="1117" alt="image" src="https://github.com/user-attachments/assets/c602fd9d-b18f-4529-9979-3dd55cb1cb25" />

## Abstract
The Transformer architecture has recently taken over the domain of natural language processing and is
now quickly gaining popularity in computer vision, achieving state-of-the-art results on image classifi-
cation benchmarks like ImageNet. Vision Transformers (ViT) work by dividing an image into fixed-size
patches that can be processed as a sequence of tokens. Self-attention is used to compute the importance
of these tokens in relation to each other, allowing the model to attend to different regions of the image
and model long-range dependencies. This architecture has proven to work well on large datasets and
shows better scaling performance than comparable convolutional neural networks (CNN). However, its
performance on medium-sized datasets remains unclear.

This thesis set out to study the performance potential and limitations of the Vision Transformer architec-
ture compared to the dominant convolutional architecture on a medium-sized dataset for vehicle model
classification. For reference, an Inception ResNet v2 model provides a baseline for accuracy on this task.
After a review of the basic concepts and building blocks of both architectures, a selection of promising,
improved architectures is assembled, with each tackling one of the most prominent weaknesses of the
Transformer: DeiT solves the reliance of ViT on large datasets for pertaining by introducing a distil-
lation strategy that can utilise pre-trained CNNs to inject some inductive biases that Transformers are
naturally lacking. Next, Swin introduces an approach using shifted windows and a hierarchical design,
inspired by convolutional networks, solving the issue of quadratic scaling with input resolution. Finally,
FlexiViT shows how fixed-sized patch embeddings can be made dynamic, making ViTs easy to adapt to
specific computational budgets by allowing dynamic patch sizes as inputs. A similar selection was made
for top-performing convolutional networks as well as hybrid networks, which have been evaluated on a
dataset of 42.000 Mercedes-Benz vehicle images.

The evaluation results show very competitive results for nearly all tested architectures, with the Swin-T/8
v2 network achieving the highest accuracy with 96,3%, closely followed by ConvNeXt-Base, a convolu-
tional model, with an accuracy of 95,6%. Both models are able to outperform the previous Inception
ResNet v2 baseline, with the largest improvements seen in the representation of minority classes in this
imbalanced dataset, manifesting in an 8,6% improvement in the F1-score over the baseline model (81,6%
to 90,2%). In terms of inference speed, convolutional models are faster (48,1ms for Swin-T/8 v2 versus
29,1ms for ConvNeXt-Base), but trade-offs can be made to bring inference times down, resulting in only
slightly reduced accuracy. Training times are also generally slower but more sample-efficient.

In conclusion, Transformers have demonstrated competitive performance by offering slightly superior
accuracy at the cost of slower image throughput and slower training times. Both the best-performing
CNN and Transformer easily surpass the previous baseline model, especially for minority classes. Since
the real-world performance of these models has proven to be near-identical, a final decision would slightly
favour the convolutional model for its faster inference speed.

<img width="1282" alt="image" src="https://github.com/user-attachments/assets/22a47ce7-8c48-4d0d-8bae-0e4a78f208c9" />

This thesis was submitted to the University of Applied Sciences Berlin on 03.04.2023.


