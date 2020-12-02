# GIZ NLP Agricultural Keyword Spotter
    
## 🗒<span style='color:green'> Description </span>

The objective of this challenge is to classify agricultural audio keywords in English and Lugandan from Uganda.
For more information about this challenge, have a look on [Zindi](https://zindi.africa/competitions/giz-nlp-agricultural-keyword-spotter).

##  😷<span style='color:green'> The solution </span> 🧠

Our solution consist of a mix of Resnet34 and Resnet50. During the training, we used a single augmentation (SpecAugmentation) strategy from [torchlibrosa](https://github.com/qiuqiangkong/torchlibrosa), which randomly cutout/erase some parts of the spectogram along the frequency and time dimensions.

* Resnet34 was the best scorer with a public leaderboard of **0.84** (Logloss).
* Resnet50 followed with a public LB of **0.88**.
* A simple average of 2 Resnet34 gave us **0.8075** on the public LB.
* Our final solution was a weighted average og the Resnet50 and 2 x Resnet34, for a small boost of **-0.06**.

NB: We tried other architectures like Densenet, Efficienet, but it seemed that they were overfitting (LB of 1.+)


## 🌴<span style='color:green'> Repository structure (tree😎)</span>
You must follow this structure when runing the notebooks.

|----data  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- raw  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- audio_files.zip  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- AdditionalUtterances.zip  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- nlp_keywords_29Oct2020.zip  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- train.csv  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |--- SampleSubmission.csv  
|\
|---- Resnet34_base.ipynb\
|---- Resnet34_with_scheduler.ipynb\
|---- Resnet50_base.ipynb\
|---- blend.ipynb\
|---- Readme.md  


Here is how to run the code:

 ```
 # 1- Run {Resnet34_base, Resnet34_with_scheduler, Resnet50_base}.ipynb
 
 # 2- Run blend.ipynb to generate the final submission file
 
```


## 🏆<span style='color:green'> Final Leaderbord </span>

🏅**Position**: 7th  
🏅**Score**: 0.8019 (LogLoss)   


[See the leaderboard](https://zindi.africa/competitions/giz-nlp-agricultural-keyword-spotter/leaderboard)


## 💻<span style='color:green'> Authors </span>

<div align='center'>

| Name           |                     Zindi ID                     |                  Github ID               |
|----------------|--------------------------------------------------|------------------------------------------|
|Muhamed TUO     |[@Nazario😁](https://zindi.africa/users/Muhamed_Tuo)  |[@NazarioR9](https://github.com/NazarioR9)|
| Cédric MANOUAN |[@Zeus😆](https://zindi.africa/users/I_am_Zeus_AI)        |[@dric2018](https://github.com/dric2018)  |
|Emmanuel KOUPOH |[@eaedk😂](https://zindi.africa/users/eaedk)      |[@eaedk](https://github.com/eaedk)        |

</div>


With 💖 from the Wakanda Team.



```
MIT License

<<<<<<< HEAD
Copyright (c) 2020 TheWakandaTeam.
=======
## Final Leaderboard
>>>>>>> 23c9dbce4e880024d23d8a776913ea4b51727263

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
