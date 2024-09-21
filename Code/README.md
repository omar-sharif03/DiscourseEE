## 📢 Annoucements
1. For running the transformer-based models, please install required packages and check your environment settings.
2. You need proper access to the models for running large models (e.g., Llama-3-70B) in Hugginface. Such as for Llama models you can get access from here [Meta Llama](https://huggingface.co/meta-llama)
3. For running openai/GPT-4 models, please use your own api key. You can find your key in your [profile](https://platform.openai.com/settings/profile?tab=api-keys)

## Notes for Running Experiments
All of our experiments are very time-consuming. It usually took 13-17 hours to get predictions and evaluate the performance of a single model. Therefore parallelization, we create one notebook for each model, so that we can run and evaluate them concurrently. The notebooks with the same prefix numbers generally have the same content with different model names and settings. Following are the descriptions of the notebooks, 

* `(_1_)_{model-name}_Predictions`: code for getting LLM predictions in *description-guided* and *question-guided* settings.
* `(_2_)_{model-name}_Output_Evaluation_Scores`: code for evaluating LLM predictions in *exact-math* and *relaxed-match* settings.
* `(_3_)_{model-name}_Predictions`: code for getting baseline models *(BERT-QA, Generative-QA)* training and predictions.
* `(_3x_)_{model-name}_Output_Evaluation_Scores`: code for evaluating baseline models.
* `(_4_)_EAE_Result_Print`: code for getting all the results on event-argument extraction.
* 




