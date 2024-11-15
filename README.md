# Long-form Answers to Visual Questions from Blind and Low Vision People


## Introduction
This is the repository for annotated data and model for this paper: </br>

> Mina Huh, Fangyuan Xu, Yi-Hao Peng, Chongyan Chen, Hansika Murugu, Danna Gurari, Eunsol Choi, Amy Pavel
>
> [Long-form Answers to Visual Questions from Blind and Low Vision People](). In: Conference on Language Modeling (COLM 2024)

✨ Check out our [website](https://minahuh.com/lfvqa) for sample annotations and demo!


## Data

Each example is a json with the following field:
* `model`: The source of long-form answer, one of [`Expert`, `GPT-4V`, `Gemini`, `LLaVA`, `QWEN`, `BLIP2`, `InstructBLIP`]. 
* `answerability`: The answerability label annotated by crowd workers from the original VizWiz dataset.
* `question`: The original question asked by blind and low vision individuals.
* `question_type`: The type of information asked in the question, one of [`Identification`, `Description`, `Reading`, `Others`]. Evenly distributed among question types.
* `answer_paragraph`: The answer paragraph.
* `answer_sentences`: The list of answer sentences, tokenized from the answer paragraph.
* `functional_roles`: The list of functional roles (1-3) for each sentence in `answer_sentences`. 
* `information_types`: The list of information types for each sentence in `answer_sentences`.
* `crowd_answers`: 10 short answers provided by crowd workers from the original VizWiz dataset.
* `crowd_majority`: Majority-voted answer among `crowd_answers`.

Here is an example of validity annotation: 

```
{
        "model": "GPT-4V",
        "answerability": "unanswerable",
        "question": "What is the item name? Thank you.",
        "question_type": "Identification",
        "image_url": "https://vizwiz.cs.colorado.edu/VizWiz_visualization_img/VizWiz_train_00018439.jpg",
        "answer_paragraph": "The item in the image is called \"Chicken Hot Pot,\" which appears to be a ready meal or a convenience food product. The packaging shows a picture of the meal, which includes sliced potatoes and pieces of chicken in a sauce, likely with vegetables. The label also indicates nutritional information and the weight of the product, which is 400 grams.",
        "answer_sentences": [
            "The item in the image is called \"Chicken Hot Pot,\" which appears to be a ready meal or a convenience food product",
            "The packaging shows a picture of the meal, which includes sliced potatoes and pieces of chicken in a sauce, likely with vegetables",
            "The label also indicates nutritional information and the weight of the product, which is 400 grams"
        ],
        "functional_roles": [
            [
                "Confirmation of Photo",
                "Answer"
            ],
            [
                "Auxiliary"
            ],
            [
                "Auxiliary"
            ]
        ],
        "information_types": [
            [
                "image_content",
                "external_information"
            ],
            [
                "image_content"
            ],
            [
                "image_content"
            ]
        ],
        "crowd_answers": [
            "potatoes",
            "pot",
            "unsuitable",
            "unsuitable",
            "chicken pot",
            "unsuitable",
            "potatoes",
            "unanswerable",
            "chicken crockpot",
            "chicken pot"
        ],
        "crowd_majority": "unsuitable"
    },
```


## Citation and contact
If you find our work helpful, please cite us as

```
@article{huh2024long,
  title={Long-Form Answers to Visual Questions from Blind and Low Vision People},
  author={Huh, Mina and Xu, Fangyuan and Peng, Yi-Hao and Chen, Chongyan and Murugu, Hansika and Gurari, Danna and Choi, Eunsol and Pavel, Amy},
  journal={arXiv preprint arXiv:2408.06303},
  year={2024}
}
```

📧 Please contact Mina Huh at `minahuh[at]cs.utexas.edu` if you have any questions or suggestions.
