# transformer-vision

Vision Transformers, originating from a famous 2017 paper titled "Attention is All You Need", have transformed the machine learning field, specifically natural language processing (NLP) and are now being used extensively in the computer vision realm as well.

The technology uses self-attention, allowing the model to encode a significant amount of information into the network, thus achieving state-of-the-art results in many NLP tasks.

The model is pre-trained on large datasets like ImageNet and can be fine-tuned on specific datasets for image classification tasks.

Vision Transformers treat image patches similarly to sequence tokens or words in NLP.

To get deeper Vision Transformers, the number of blocks inside the Transformer encoder can be increased.

A significant drawback of Vision Transformers is that they require a large amount of data to train to achieve results comparable to state-of-the-art models. For smaller datasets, pre-trained Vision Transformers can be fine-tuned for better results.

**The model works by dividing the image into small patches and converting each patch into a vector of numbers. This process is known as creating 'patch embeddings'. Then, the model adds 'positional embeddings', which help the model understand where each patch is in relation to the others.

Once these vectors are created, they are passed through the transformer encoder which transforms the input data into another set of vectors that are better for making predictions. The transformer encoder uses a special mechanism called 'attention' to weigh the importance of different patches when making predictions.

After going through the transformer encoder, the transformed vectors are passed to a 'header', which makes the final prediction about what the image contains
**

code working

How an image is split into patches: The Vision Transformer (ViT) model processes an image in small fixed-sized patches rather than the entire image as a whole. The code shows how the image is divided into 14x14 patches of size 16x16 pixels each, resulting in a total of 196 patches. These patches are then flattened and linearly transformed into a 768-dimensional vector, forming the input sequence for the transformer model. This is done using a Conv2D operation with kernel and stride of size equal to the patch size.

Visualizing the position embeddings which are added to the patches: After the patches are prepared, the position embeddings are added. Since the transformers do not inherently understand the 2D structure of the image, position embeddings help the model understand the relative positions of the patches. The visualization is done using a heat map that depicts cosine similarity between the position embeddings.

Preparing the input for the transformer encoders: The transformer encoders require the input to be prepared in a certain way. A learnable class token is prepended to the patch embedding vectors as the 0th vector. Then, position embedding vectors are added to the patch embedding vectors. The purpose of the class token is to absorb the global information of the input sequence, which is crucial for the final prediction. This class token acts as a sort of summary of the entire image, which helps the model when it needs to make a prediction about the image 

How the input passes through multiple transformer encoders: The transformer encoders consist of a series of self-attention and feed-forward neural network (FFN) layers. The prepared input sequentially passes through these layers. The self-attention mechanism allows the model to weigh the importance of different patches in relation to each other, and the FFN layers further process this information.

Explaining how the attention mechanism works inside a transformer: The core component of the transformer encoders is the self-attention mechanism, which computes a weighted sum of all patches' embeddings for each patch. The weights are computed based on the compatibility of each patch with all others, effectively allowing each patch to "attend" to all others. This is done by computing queries, keys, and values from the input embeddings and using them to calculate the attention scores.

Visualizing the attention matrices: An attention matrix is the result of a self-attention operation, with each entry in the matrix representing the attention score between two patches. The code visualizes the attention matrices as heat maps, giving us insights into what parts of the image the model is focusing on when processing a certain patch. This can help us understand the model's decision-making process.
