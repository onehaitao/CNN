# CNN-relation-extraction
Implementation of [Relation Classification via Convolutional Deep Neural Network](https://www.aclweb.org/anthology/C14-1220.pdf)

## Environment Requirements
* python 3.6
* pytorch 1.3.0

## Data
* [SemEval2010 Task8](https://drive.google.com/file/d/0B_jQiLugGTAkMDQ5ZjZiMTUtMzQ1Yy00YWNmLWJlZDYtOWY1ZDMwY2U4YjFk/view?sort=name&layout=list&num=50) \[[paper](https://www.aclweb.org/anthology/S10-1006.pdf)\]
* [Embedding - Turian et
al.(2010)](http://metaoptimize.s3.amazonaws.com/hlbl-embeddings-ACL2010/hlbl-embeddings-scaled.EMBEDDING_SIZE=50.txt.gz) \[[paper](http://www.aclweb.org/anthology/P10-1040)\]

## Usage
1. Download the embedding and decompress it into the `embedding` folder.
2. Run the following the commands to start the program.
```shell
python run.py
```
More details can be seen by `python run.py -h`.

3. You can use the official scorer to check the final predicted result.
```shell
perl semeval2010_task8_scorer-v1.2.pl proposed_answer.txt predicted_result.txt >> result.txt
```

## Result
The result of my version and that in paper are present as follows:
| paper | my version |
| :------: | :------: |
| 0.789 | 0.7625 |

The training log can be seen in `train.log` and the official evaluation results is available in `result.txt`.

*Note*:
* Some settings are different from those mentioned in the paper.
* Do not use validation when training.
* Just complete the part without lexical level features. More detail is available in Section 5.3 in this paper.
