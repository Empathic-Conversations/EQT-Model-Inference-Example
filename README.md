# __Empathetic Question Taxonomy Inference Example__

## __Introduction__
Showing how to predict the question type and intention using models from the [EQT paper](https://aclanthology.org/2022.acl-long.211/). The [official GitHub repository](https://github.com/Sea94/EQT) provide the source code but,

1. The code is not easily understandable.
2. The authors did not provide pre-trained model weights in the repository.

Therefore, we provide a short [example notebook](inference.ipynb) that demonstrates how to leverage their pre-trained models to predict question types and question intents for arbitrary dialogues.

## __Getting Started__
It is recommended to directly clone this repository. Source code under the folder [`src`](src) is directly copied from the official repository with slight reorganization. The notebook [`inference.ipynb`](inference.ipynb) mainly demonstrates how to use the functions provided by the EQT repository. So, it is possible to read the notebook and copy source code necessary for inference only.

## __Dependencies__
One can directly create a conda environment from `environment.yml` or install the dependencies manually. Specifically, one should consult the official `tensorflow-gpu` [installation documentation](https://www.tensorflow.org/install) if one choose the later approach.

## __Model Weights__
We contact the authors and they are willing to share the trained model weights, stored in [the Google Drive](https://drive.google.com/drive/folders/1H0bAh-NDPZKDBN6U1JV3o896G1Eo4ldr?usp=drive_link). There should be a `models.7z` compressed file containing weights for two models, i.e., the intent predictor and question type predictor. Please open an issue if the link does not work. After downloading the model weights, please place the weights in `models/type` and `models/intent` respectively.

## __Folder Structure__
You should have a folder structure similar to the plot below,
```
PROJECT_HOME
├── data
│   └── two_dialogues.json
├── environment.yml
├── inference.ipynb
├── models
│   ├── intent
│   │   ├── checkpoint
│   │   ├── ckpt-3.data-00000-of-00001
│   │   └── ckpt-3.index
│   └── type
│       ├── checkpoint
│       ├── ckpt-4.data-00000-of-00001
│       └── ckpt-4.index
├── README.md
└── src
    ├── datasets.py
    ├── model_qbert.py
    └── model_utils.py
```
Then, one should be able to run the notebook.

## __Citation__
```
@inproceedings{svikhnushina-etal-2022-taxonomy,
    title = "A Taxonomy of Empathetic Questions in Social Dialogs",
    author = "Svikhnushina, Ekaterina  and
      Voinea, Iuliana  and
      Welivita, Anuradha  and
      Pu, Pearl",
    booktitle = "Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = may,
    year = "2022",
    address = "Dublin, Ireland",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.acl-long.211",
    doi = "10.18653/v1/2022.acl-long.211",
    pages = "2952--2973",
    abstract = "Effective question-asking is a crucial component of a successful conversational chatbot. It could help the bots manifest empathy and render the interaction more engaging by demonstrating attention to the speaker{'}s emotions. However, current dialog generation approaches do not model this subtle emotion regulation technique due to the lack of a taxonomy of questions and their purpose in social chitchat. To address this gap, we have developed an empathetic question taxonomy (EQT), with special attention paid to questions{'} ability to capture communicative acts and their emotion-regulation intents. We further design a crowd-sourcing task to annotate a large subset of the EmpatheticDialogues dataset with the established labels. We use the crowd-annotated data to develop automatic labeling tools and produce labels for the whole dataset. Finally, we employ information visualization techniques to summarize co-occurrences of question acts and intents and their role in regulating interlocutor{'}s emotion. These results reveal important question-asking strategies in social dialogs. The EQT classification scheme can facilitate computational analysis of questions in datasets. More importantly, it can inform future efforts in empathetic question generation using neural or hybrid methods.",
}
```
