# NewsClassification-Chinese
This is for Chinese News Classify program. 

It can know witch the input News is for witch classification like Art, Economy, Military, Sport etc...

## Data Pre-process
- Load all the data and change the answer text to number.

  | 計算機(ComputerScience) | 環境(Environment) | 醫藥(Medicine) | 藝術(Art) | 軍事(Military) | 體育(Sport) | 經濟(Economy) | 教育(Education) | 政治(Politics) | 交通(Traffic) |
 |---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
 | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |

- Cancel all the Newline, Punctuation and transfer the Chinese sentence to many single words as like English(The English sentence is be combined many of single words).

  Before Pre-process
  
  ![alt text](https://raw.githubusercontent.com/ahoucbvtw/NewsClassification-Chinese/main/Picture/448788.jpg "Before Pre-process")
  
  After Pre-process
  
  ![alt text](https://raw.githubusercontent.com/ahoucbvtw/NewsClassification-Chinese/main/Picture/888786.jpg "After Pre-process")
  
- CountVectorizer

  Training Data：fit(Show all of labels) / transform(Calculate how many of labels)
  Testing Data：transform(Calculate how many of labels)
  *Testing Data should not do fit, because of Training Data was done. The new label can be ignore.*
