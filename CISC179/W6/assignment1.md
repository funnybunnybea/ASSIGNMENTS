# Part 1 Word and Character Count Using a List

```python
text = "The quick brown fox jumps over the lazy dog the fox runs"

# split into a list of words
words = text.split()

# count words and characters
word_count = len(words)
char_count = len(text)

print("Word count:", word_count)
print("Character count:", char_count)

# build frequency list using the list
freq = []
for word in words:
    found = False
    for pair in freq:
        if pair[0] == word:
            pair[1] += 1
            found = True
            break
    if not found:
        freq.append([word, 1])

print("Word frequencies:", freq)
```
| Word | Count |
|---|---|
| The | 1 |
| quick | 1 |
| brown | 1 |
| fox | 2 |
| jumps | 1 |
| over | 1 |
| the | 2 |
| lazy | 1 |
| dog | 1 |
| runs | 1 |

# Part 2 Repeat With a Dictionary

```python
text = "The quick brown fox jumps over the lazy dog the fox runs"

words = text.split()

freq = {}
for word in words:
    if word in freq:
        freq[word] += 1
    else:
        freq[word] = 1

print("Word frequencies:", freq)
```

# Part 3 Regular Expressions for Data Extraction

```python
import re

text = "Contact John at john123@gmail.com or 619-321-8858. Reach Mary at mary.jones@hotmail.com or 858-555-1234."

# extract phone numbers
phones = re.findall(r"\d{3}-\d{3}-\d{4}", text)

# extract emails
emails = re.findall(r"[\w.]+@[\w.]+", text)

print("Phones:", phones)
print("Emails:", emails)
```

# Part 4 Email Username Processing

```python
usernames = []
for email in emails:
    username = email.split("@")[0]
    usernames.append(username)

new_emails = []
for username in usernames:
    new_emails.append(username + "@hotmail.com")

print("Usernames:", usernames)
print("New emails:", new_emails)
```
