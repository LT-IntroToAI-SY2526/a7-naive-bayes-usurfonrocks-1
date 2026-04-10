import wikipedia
import re, time
from typing import List

def tokenize(text: str) -> List[str]:
    """Splits given text into a list of the individual tokens in order

    Args:
        text - text to tokenize

    Returns:
        tokens of given text in order
    """
    tokens = []
    token = ""
    for c in text:
        if (
            re.match("[a-zA-Z0-9]", str(c)) != None
            or c == "'"
            or c == "_"
            or c == "-"
        ):
            token += c
        else:
            if token != "":
                tokens.append(token.lower())
                token = ""

    return tokens

article = wikipedia.page("Artemis II", auto_suggest=False).content
# print(article)
words = tokenize(article)

with open("sorted_stoplist.txt", "r", encoding='utf8') as f:
    stoplist = f.read()
    tokenize_stoplist = tokenize(stoplist)

freqs = {}

for word in words:
    if word not in tokenize(stoplist)
        if word in freqs:
            freqs[word] += 1
        else:
            freqs[word] = 1

total_unique_words = len(freqs)
print (f"Unique words: {total_unique_words}")
total_words = sum(freqs.values)
top_words = sorted(freqs.items(), key=lambda x: x[1], reverse=True)
for words,count in top_words[:20]:
    print(f"{words}{count}")