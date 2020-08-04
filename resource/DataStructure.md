### CyanTeacup dict data structure



### Google translate data structure

```
{
  sentences: array obj -> { // 当翻译内容比较多的时候，会自动分隔为数个句子
    trans: string,  // 翻译结果
    orig: string,   // 原句
    backend: int,   // 未发现作用
  },
  dict: array obj -> {      // 字典，当翻译内容为单词时有效
    pos: string,            // 词性，如形容词、名词等
    terms: arrsy string,    // 其他释义列表
    entry: array obj -> {   // 某个释义对应的英文翻译
      word: string,         // 释义
      reverse_translation: array string,    // 对应的英文翻译列表
      score: float,                         // 该释义对应请求单词的匹配度，最大值为 1，最小值为 0
    },
    base_form: string,      // 当前字典列表释义的英文
    pos_enum: int,          // 第几个字典序列
  },
  src: string,              // 翻译源，如中文、英文、日文等
},
```

### Bing dict data structure

```
{
  word: string,                   // 原文
  symbols: obj -> {               // 读音
    prUS: string,                 // 美式音标
    prUStts: string,              // 美式发音
    prUK: string,                 // 英式音标
    prUKtts: string,              // 英式发音
  },
  trans: array obj -> {           // 翻译
    pos: string,                  // 单词词性
    tran: string,                 // 翻译结果
  },
  phrases: array obj -> {         // 词组
    pos: string,                  // 词组词性
    phrase: array string,         // 该词性下的词组列表
  },
  synonyms: array obj -> {        // 同义词
    pos: string,                  // 词性
    synonym: array string,        // 该词性下的同义词
  },
  antonyms: array obj -> {        // 反义词
    pos: string,                  // 词性
    antonym: array string,        // 该词性下的反义词
  },
  explains: array obj -> {        // 英汉双解
    pos: string,                  // 词性
    sentences: array obj -> {     // 解释
      explain: string,            // 双解
      sentence: array obj -> {    // 例句
        src: string,              // 英文例句
        tran: string,             // 中文翻译
      },
    },
  },
},
```

### Iciba dict data structure

```
{
  baesInfo: {
    symbols: arrsy obj -> {
      parts: array obj -> {
        means: array string,
        part: string,
      }],
      ph_am: string,
      ph_am_mp3: string,
      ph_en: string,
      ph_en_mp3: string,
    }],
    exchange: {
      word_er: string,
      word_est: string,
      word_pl: string,
    }
  },

}
```