# MultiLingual Llama for Indian Languages 

The goal of this project is to fine tune LLAMA for Indian Languages as it is originally trained on 90% English Language and 10% Mathematical equations

## Data Used for Training 

### We use WIKIMatrix to fine tune the model which contains the following : 

* 85 different languages, 1620 language pairs
* 134M parallel sentences, out of which 34M are aligned with English
* this [*table shows the amount of mined parallel sentences for most of the language pairs*](WikiMatrix-sizes.pdf)
* the mined bitext are stored on AWS and can de downloaded with the following command:
```bash
wget https://dl.fbaipublicfiles.com/laser/WikiMatrix/v1/WikiMatrix.en-fr.tsv.gz
```
Replace "en-fr" with the ISO codes of the desired language pair.
The language pair must be in alphabetical order, e.g. "de-en" and not "en-de".
The list of available bitexts and their sizes are given in the file [*list_of_bitexts.txt*](list_of_bitexts.txt).
Please do **not loop over all files** since AWs implements some [*limitations*](https://dl.fbaipublicfiles.com/README) to avoid abuse.

Use this command if you want to download all 1620 language pairs in one tar file (but this is 65GB!):
```bash
wget https://dl.fbaipublicfiles.com/laser/WikiMatrix/WikiMatrix.v1.1620_language_pairs.tar
```

### References 

```bibtext
@misc {schwenk2019wikimatrix,
      title={WikiMatrix: Mining 135M Parallel Sentences in 1620 Language Pairs from Wikipedia}, 
      author={Holger Schwenk and Vishrav Chaudhary and Shuo Sun and Hongyu Gong and Francisco Guzmán},
      year={2019},
      eprint={1907.05791},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

```bibtext
@misc {touvron2023llama,
      title={LLaMA: Open and Efficient Foundation Language Models}, 
      author={Hugo Touvron and Thibaut Lavril and Gautier Izacard and Xavier Martinet and Marie-Anne Lachaux and Timothée Lacroix and Baptiste Rozière and Naman Goyal and Eric Hambro and Faisal Azhar and Aurelien Rodriguez and Armand Joulin and Edouard Grave and Guillaume Lample},
      year={2023},
      eprint={2302.13971},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

```bibtex
@misc {beeching2023stackllama,
    author       = { Edward Beeching and
                     Younes Belkada and
                     Kashif Rasul and
                     Lewis Tunstall and
                     Leandro von Werra and
                     Nazneen Rajani and
                     Nathan Lambert
                   },
    title        = { StackLLaMA: An RL Fine-tuned LLaMA Model for Stack Exchange Question and Answering },
    year         = 2023,
    url          = { https://huggingface.co/blog/stackllama },
    doi          = { 10.57967/hf/0513 },
    publisher    = { Hugging Face Blog }
}
```
