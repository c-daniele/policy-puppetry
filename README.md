# Policy Puppetry Prompt Injection
I started from an article from HiddenLayer, published a few weeks ago, in which their research team described a rather creative and ingenious jailbreaking technique to bypass the safety guardrails and alignment of frontier models. The technique appears to be universal and applicable with a single prompt to multiple models, capable of displaying typically non-safe content or even showing portions of the native system prompt.

# What it consists of
The attack method is based on 3 components:

 1. The syntactic structure of the prompt
 2. The "roleplaying" style narration technique
 3. The use of encoding or obfuscation techniques in the style of "leetspeak"

## The prompt structure
It is essentially based on a JSON, XML, or YAML format, which attempts to bypass the model's alignment by making the prompt interpreted as a real "policy".

## The narration technique
A situation is staged with actors, lines, and a kind of script to be completed. The article often uses the context of the TV series Dr. House, referencing the protagonists and their peculiar characteristics (e.g., the contrast between House and his boss, Dr. Cuddy).

## Encoding techniques
For those unfamiliar, leetspeak (also known as l33t speak or 1337 speak) is a form of writing that replaces letters of the alphabet with numbers, symbols, or other characters. The article specifies that this technique is necessary for more powerful models like Gemini 2.5 or Gpt-o3, but I have experimentally noticed that it is also necessary with Claude 3.5. In some cases, I even had to complicate the prompt by adding a Base64 output encoding, and I was quite surprised that more or less all models are able to generate output tokens in Base64 format without problems.

# Enjoy the code