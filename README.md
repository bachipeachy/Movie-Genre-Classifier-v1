# Movie-Genre-Classifier-v1
This repository contains multi- label text classifiers developed in Tensorflow 2.1 using custom modules

It is based on a blog post by Zuzanna Deutschman https://towardsdatascience.com/multi-label-text-classification-5c505fdedca8

## Training Dataset
Using "CMU Movie Summary Corpus" open dataset.
You can download the dataset directly from
http://www.cs.cmu.edu/~ark/personas/data/MovieSummaries.tar.gz
This dataset contains multiple files, but we’ll need only two of them:

movie.metadata.tsv: Metadata for 81,741 movies, extracted from the November 4, 2012 dump of Freebase.

The movie genre tags are available in this file

plot_summaries.txt: Plot summaries of 42,306 movies extracted from the November 2, 2012 dump of English-language Wikipedia.

Each line contains the Wikipedia movie ID (which indexes into movie.metadata.tsv) followed by the plot summary

These files are too big to be uploaded here

The dataset has been sliced by 99% to reduce training time to enable quick testing

About 420 samples are used for training the model

## Development Environment
The Jupyter Notebook running on Mac High Sierra in ML development virtual environment
The Python Library Modules in my ML venv "deep" include:
(NOTE: not all modules are required)

(deep) mbp:~ bp$ pip list

Package                       Version   
----------------------------- ----------
absl-py                       0.9.0     
alabaster                     0.7.12    
allennlp                      0.9.0     
appnope                       0.1.0     
astor                         0.8.1     
attrs                         19.3.0    
Babel                         2.8.0     
backcall                      0.1.0     
beautifulsoup4                4.8.2     
bleach                        3.1.1     
blis                          0.4.1     
boto3                         1.12.9    
botocore                      1.15.9    
bs4                           0.0.1     
cachetools                    4.0.0     
catalogue                     1.0.0     
certifi                       2019.11.28
cffi                          1.14.0    
chardet                       3.0.4     
chart-studio                  1.0.0     
Click                         7.0       
cloudpickle                   1.3.0     
colorlover                    0.3.0     
conllu                        1.3.1     
cryptography                  2.8       
cufflinks                     0.17.3    
cycler                        0.10.0    
cymem                         2.0.3     
decorator                     4.4.1     
defusedxml                    0.6.0     
docutils                      0.15.2    
editdistance                  0.5.3     
entrypoints                   0.3       
flaky                         3.6.1     
Flask                         1.1.1     
Flask-Cors                    3.0.8     
ftfy                          5.7       
future                        0.18.2    
gast                          0.2.2     
gevent                        1.4.0     
google-auth                   1.11.2    
google-auth-oauthlib          0.4.1     
google-pasta                  0.1.8     
greenlet                      0.4.15    
grpcio                        1.27.2    
gym                           0.17.0    
h5py                          2.10.0    
html-parser                   0.2       
html5lib                      1.0.1     
idna                          2.9       
imagesize                     1.2.0     
importlib-metadata            1.5.0     
ipykernel                     5.1.4     
ipython                       7.12.0    
ipython-genutils              0.2.0     
ipywidgets                    7.5.1     
itsdangerous                  1.1.0     
jedi                          0.16.0    
Jinja2                        2.11.1    
jmespath                      0.9.5     
joblib                        0.14.1    
jsonnet                       0.15.0    
jsonpickle                    1.3       
jsonschema                    3.2.0     
jupyter-client                6.0.0     
jupyter-core                  4.6.3     
Keras-Applications            1.0.8     
Keras-Preprocessing           1.1.0     
kiwisolver                    1.1.0     
lxml                          4.5.0     
Markdown                      3.2.1     
MarkupSafe                    1.1.1     
matplotlib                    3.1.3     
mistune                       0.8.4     
mitdeeplearning               0.1.2     
more-itertools                8.2.0     
murmurhash                    1.0.2     
nbconvert                     5.6.1     
nbformat                      5.0.4     
nltk                          3.4.5     
notebook                      6.0.3     
numpy                         1.18.1    
numpydoc                      0.9.2     
oauthlib                      3.1.0     
opt-einsum                    3.1.0     
overrides                     2.8.0     
packaging                     20.1      
pandas                        1.0.1     
pandocfilters                 1.4.2     
parsimonious                  0.8.1     
parso                         0.6.2     
pexpect                       4.8.0     
pickleshare                   0.7.5     
pip                           20.0.2    
plac                          0.9.6     
plotly                        4.5.3     
pluggy                        0.13.1    
ply                           3.11      
preshed                       3.0.2     
prometheus-client             0.7.1     
prompt-toolkit                3.0.3     
protobuf                      3.11.3    
ptyprocess                    0.6.0     
py                            1.8.1     
pyasn1                        0.4.8     
pyasn1-modules                0.2.8     
pycparser                     2.19      
pydot                         1.4.1     
pydotplus                     2.0.2     
pyglet                        1.5.0     
Pygments                      2.5.2     
pyOpenSSL                     19.1.0    
pyparsing                     2.4.6     
pyrsistent                    0.15.7    
pytest                        5.3.5     
python-dateutil               2.8.1     
pytorch-pretrained-bert       0.6.2     
pytorch-transformers          1.1.0     
pytz                          2019.3    
pyzmq                         19.0.0    
regex                         2020.2.20 
requests                      2.23.0    
requests-oauthlib             1.3.0     
responses                     0.10.11   
retrying                      1.3.3     
rsa                           4.0       
s3transfer                    0.3.3     
scikit-learn                  0.22.1    
scipy                         1.4.1     
seaborn                       0.10.0    
Send2Trash                    1.5.0     
sentencepiece                 0.1.85    
setuptools                    41.2.0    
six                           1.14.0    
snowballstemmer               2.0.0     
soupsieve                     2.0       
spacy                         2.2.3     
Sphinx                        2.4.3     
sphinxcontrib-applehelp       1.0.1     
sphinxcontrib-devhelp         1.0.1     
sphinxcontrib-htmlhelp        1.0.3     
sphinxcontrib-jsmath          1.0.1     
sphinxcontrib-qthelp          1.0.2     
sphinxcontrib-serializinghtml 1.1.3     
sqlparse                      0.3.0     
srsly                         1.0.1     
tensorboard                   2.1.0     
tensorboardX                  2.0       
tensorflow                    2.1.0     
tensorflow-estimator          2.1.0     
tensorflow-hub                0.7.0     
termcolor                     1.1.0     
terminado                     0.8.3     
testpath                      0.4.4     
thinc                         7.3.1     
torch                         1.4.0     
tornado                       6.0.3     
tqdm                          4.43.0    
traitlets                     4.3.3     
Unidecode                     1.1.1     
urllib3                       1.25.8    
wasabi                        0.6.0     
wcwidth                       0.1.8     
webencodings                  0.5.1     
Werkzeug                      1.0.0     
wheel                         0.34.2    
widgetsnbextension            3.5.1     
word2number                   1.1       
wrapt                         1.12.0    
xlrd                          1.2.0     
zipp                          3.0.0     
