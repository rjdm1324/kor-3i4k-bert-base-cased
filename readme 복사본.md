OVERVIEW
===
문장을 입력받아 7개의 의도로 분류합니다.
fragment , statement , question , command , rhetorical question , rhetorical command and intonation-depedent utterance.

## How to use
----
Sentence Textbox에 분류하고 싶은 Sentence를 입력합니다.

## How to make
----
1. [3i4k](https://github.com/warnikchow/3i4k) data set을 준비했습니다.

2. data set을 [bert-base-multilingual-cased](https://huggingface.co/bert-base-multilingual-cased) 모델에 fine-tuning 하였습니다.

## Post Parameter
----
```
sentence = "sentence"

```

## output format
----
```
{
    "0": [
        {
            "label": "fragment",
            "score": 점수
        },
        {
            "label": "statement",
            "score": 점수
        },
        {
            "label": "question",
            "score": 점수
        },
        {
            "label": "command",
            "score": 점수
        },
        {
            "label": "rhetorical question",
            "score": 점수
        },
        {
            "label": "rhetorical command",
            "score": 점수
        },
        {
            "label": "intonation-depedent utterance",
            "score": 점수
        }
    ]
}
```

## API Predict Test
----
```
$ curl -L -X POST 'https://main-kor-3i4k-bert-base-cased-rjdm1324.endpoint.ainize.ai/generate' -F 'sentence="너는 지금 무엇을 하고 있니?"'

{
    "0":
    [
        {"label":"Fragment","score":0.0006364848813973367},
        {"label":"statement","score":0.012324976734817028},
        {"label":"question","score":0.9015094041824341},
        {"label":"command","score":0.009313942864537239},
        {"label":"rhetorical question","score":0.07272904366254807},{"label":"rhetorical command","score":0.0007764914189465344},{"label":"intonation-depedent utterance","score":0.0027097363490611315}
    ]
}

```


## Healthy Check
----
Using curl in the terminal:

```

$ curl -L -X GET 'https://main-kor-3i4k-bert-base-cased-rjdm1324.endpoint.ainize.ai/healthz'
{
    Health
}

```
