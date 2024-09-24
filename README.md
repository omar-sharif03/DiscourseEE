## 📣 Announcements
* Please access **DiscourseEE** from [this folder](https://github.com/omar-sharif03/DiscourseEE/tree/main/Data). You can also download it from [Huggingface](https://huggingface.co/datasets/omar-sharif03/DiscourseEE).
* All the model predictions are released for reproducibility. Check out [this folder](https://github.com/omar-sharif03/DiscourseEE/tree/main/Predictions-Results) and check the [demo notebook](https://github.com/omar-sharif03/DiscourseEE/blob/main/Predictions-Results/Evaluation.ipynb) to reproduce the results we reported in the paper.
* To facilitate further experimentation, associated codes are released [here](https://github.com/omar-sharif03/DiscourseEE/tree/main/Code).

----

## 📚 *Explicit, Implicit, and Scattered*: Revisiting Event Extraction to Capture Complex Arguments
Prior works formulate the extraction of event-specific arguments as a span extraction problem, where event arguments are **explicit** --- i.e. assumed to be contiguous spans of text in a document. In this study, we revisit this definition of Event Extraction (EE) by introducing two key argument types that cannot be modeled by existing EE frameworks. First, **implicit arguments** are event arguments which are *not* explicitly mentioned in the text, but can be inferred through context. Second, **scattered arguments** are event arguments that are composed of information scattered throughout the text. These two argument types are crucial to elicit the full breadth of information required for proper event modeling. 

To support the extraction of explicit, implicit, and scattered arguments, we develop a novel dataset, **DiscourseEE**,  which includes 7,464 argument annotations from online health discourse. Notably, 51.2% of the arguments are implicit, and 17.4% are scattered, making DiscourseEE a unique corpus for complex event extraction. Additionally, we formulate argument extraction as a *text generation problem* to facilitate the extraction of complex argument types. We provide a comprehensive evaluation of state-of-the-art models and highlight critical open challenges in generative event extraction
