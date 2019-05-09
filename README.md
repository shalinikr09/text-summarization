# tensorflow-text-summarization
Simple Tensorflow implementation of text summarization


## Requirements
- Python 3
- Tensorflow (>=1.8.0)
- pip install -r requirements.txt


## Usage
### Prepare data
Dataset is available at [harvardnlp/sent-summary](https://github.com/harvardnlp/sent-summary). Locate the summary.tar.gz file in project root directory. Then,
```
$ python prep_data.py
```
To use Glove pre-trained embedding, download it via
```
$ python prep_data.py --glove
```

### Train
Used ```sumdata/train/train.article.txt``` and ```sumdata/train/train.title.txt``` for training data. To train the model, use
```
$ python train.py
```
To use Glove pre-trained vectors as initial embedding, use
```
$ python train.py --glove
```

### Test
Generate summary of each article in ```sumdata/train/valid.article.filter.txt``` by
```
$ python test.py
```
It will generate result summary file ```result.txt```. 

#### Sample Summary Output
```

"the dollar regained some lost ground in asian trade thursday in what was seen as a largely technical rebound after weakness prompted by expectations of a shift in us interest rate policy , dealers said ."
> Model output: dollar stable in asian trade
> Actual title: dollar regains ground in asian trade
```