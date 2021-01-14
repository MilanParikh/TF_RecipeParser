# TF_RecipeParser

This is a tensorflow model created to parse recipe ingredients using named entity recognition. Served via the tensorflow/serving docker image, the "1" folder must be mounted to "/models/my_model/1" within the container.

Model was created with this implementation: https://github.com/guillaumegenthial/tf_ner

Some example inputs are listed in the sample_input.txt file, however batched inputs do not work with different "nwords" values per input.
