# Individual Inputs

{"inputs": {"words": [["1/2", "cup", "softened", "butter"]], "nwords": [4]}}

curl -d '{"inputs": {"words": [["1/2", "cup", "softened", "butter"]], "nwords": [4]}}' -X POST http://localhost/v1/models/my_model:predict

# Batched Inputs
Unfortunately using different nwords values results in an error, so batched inputs are essentially useless right now. 

This works: {"instances": [{"words": ["1/2", "cup", "softened", "butter"], "nwords": 4}, {"words": ["2", "cups", "blueberries", "washed"], "nwords": 4}]}

This does not: {"instances": [{"words": ["1/2", "cup", "softened", "butter"], "nwords": 4}, {"words": ["2", "cups", "blueberries", "washed", "and", "dried"], "nwords": 6}]}

curl -d '{"instances": [{"words": ["1/2", "cup", "softened", "butter"], "nwords": 4}, {"words": ["2", "cups", "blueberries", "washed", "and", "drained"], "nwords": 6}]}' -X POST http://localhost/v1/models/my_model:predict
