# Flask Summary

** PreSumm modules was originally from https://github.com/nlpyang/PreSumm **

Features
--------
 * generate summary on given text

 Train and Use the model generate by BertSum
 -------------------------------------------
 please follow this [documents](https://github.com/Quan25/flask-summary/blob/master/guides.pdf) about how to train and use the model generated by BertSum

Installation In A Nutshell (on localhost)
--------------------------
 1. clone this project to your local disk
 ```
  git clone https://github.com/Quan25/flask-summary.git
 ```
 2. cd into the cloned project and download PreSumm
 ```
  git clone https://github.com/nlpyang/PreSumm.git
 ```
 3. cd into PreSumm folder and change the branch to dev
 ```
  git checkout dev
 ```
 4. Install [Flask](https://flask.palletsprojects.com/en/1.1.x/installation/#installation)
 5. Install [ROUGE-1.5.5](https://drive.google.com/file/d/1RxfZOYyNvzvCf37_vABfJMkohAsEZKtH/view?usp=sharing)
  - Install `libxml-parser-perl`, it is essential for installing ROUGE-1.5.5
  ```
    sudo apt-get install libxml-parser-perl
  ```
  - and make sure you can run this, which means the ROUGE is successfully installed
  ```
    ./runROUGE-test.pl
  ```
 6. Install pyrouge
 ```
  git clone https://github.com/bheinzerling/pyrouge.git
  cd pyrouge
  pip install -e .
 ```
 - Additional information can be found [here](https://github.com/bheinzerling/pyrouge) about how to install pyrouge and running the test

 7. Please install pytorch 1.1.0 with this comand
 - GPU
```
  conda install pytorch==1.1.0 torchvision==0.3.0 cudatoolkit=10.0 -c pytorch
```
 - CPU Only
```
  conda install pytorch-cpu==1.1.0 torchvision-cpu==0.3.0 cpuonly -c pytorch
```
 8. put your model file(i.e. xxxxx.pt) inside ```/PreSumm/models ```
 9. add the following `PYTHONPATH` to bash_profile
 ```
  export PYTHONPATH=$PYTHONPATH:~/Desktop/flask_summary/PreSumm/src

 ```
 10. run `source ~/.bash_profile`
 11. Run `python app.py` in the flask-summary directory.
 12. Start web server by running `python app.py` while in the server_example directory.
 13. Browse the examples at [0.0.0.0:5000](http://0.0.0:5000) using a browser. *(defaults to port `5000`)*