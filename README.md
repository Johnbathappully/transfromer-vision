# transformer-vision

Vision Transformers, originating from a famous 2017 paper titled "Attention is All You Need", have transformed the machine learning field, specifically natural language processing (NLP) and are now being used extensively in the computer vision realm as well.

The technology uses self-attention, allowing the model to encode a significant amount of information into the network, thus achieving state-of-the-art results in many NLP tasks.

When applied to images, Vision Transformers require the image to be split into patches, which are then flattened and combined with a positional embedding. This sequence is then fed into a standard transformer encoder.

The model is pre-trained on large datasets like ImageNet and can be fine-tuned on specific datasets for image classification tasks.

Vision Transformers treat image patches similarly to sequence tokens or words in NLP.

To get deeper Vision Transformers, the number of blocks inside the Transformer encoder can be increased.

A significant drawback of Vision Transformers is that they require a large amount of data to train to achieve results comparable to state-of-the-art models. For smaller datasets, pre-trained Vision Transformers can be fine-tuned for better results.

The model works by dividing the image into small patches and converting each patch into a vector of numbers. This process is known as creating 'patch embeddings'. Then, the model adds 'positional embeddings', which help the model understand where each patch is in relation to the others.

Once these vectors are created, they are passed through the transformer encoder which transforms the input data into another set of vectors that are better for making predictions. The transformer encoder uses a special mechanism called 'attention' to weigh the importance of different patches when making predictions.

After going through the transformer encoder, the transformed vectors are passed to a 'header', which makes the final prediction about what the image contains
