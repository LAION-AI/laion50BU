# laion50BU
Un-*** 50 billions multimodality dataset 

## Reasoning

We previously discovered more than 300 Billion different images on Common Crawl dumps. Our initial approach was to use CLIP for filtering samples with enough similarity between the image and text, to create both LAION-400m and LAION-5B datasets. This might have introduced certain biases into the filtered datasets. As we have used a pre-trained openAI CLIP model of certain scale (ViT B/32), the biases may also depend on the particular choice of the scale. 

We also took other design decisions that we aim now to correct in order to better capture the available data and offer researchers a base dataset of un-CLIPped samples, we estimate at some 50 billions for image-text modalities. Researchers will be able then to identify and measure CLIP biases and come up with different methods of sampling the unfiltered base dataset for future models needs. Specifically, it will also become possible to see the effect of model scale (eg, CLIP B/32, B/16, L/14, etc) selected for filtering on the biases and quality of the resulting subsets.

Here is a list of topics we want to touch in extracting these large datasets from Common Crawl dumps:
1. apply minimal, heuristic ruleset, to remove illegal or technically unwanted samples such as transparent dot images, sprites, etc.
1. introduce new extractions for modalities such as audio and video
1. deduplicate by url+text so we can capture data from multilanguage websites

In addition we want to use random sampling techniques to properly analyze the resulting dataset and discover what else needs to be removed before releasing this unprocessed large dataset for further research.
