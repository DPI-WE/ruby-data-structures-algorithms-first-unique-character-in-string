# First Unique Character in a String 🔠

## The problem
Write a program that:
- takes a string as input
- finds the first non-repeating character in it
- returns the index of this character
- returns -1 if every character repeats

Example: Given the string "discovery", the first non-repeating character is "d", and its index is 0.

## Understand the Problem
Let's warm up by understanding how to approach identifying unique characters.

- Consider the string "stress". Can you identify the first non-repeating character?
- "s"
  - Not quite. While "s" is the first character, it's not non-repeating in the string "stress".
- "t"
  - Correct! The first non-repeating character in "stress" is "t", following the first set of repeating "s" characters.
- "r"
  - Close, but "r" comes after the first non-repeating character we're looking for.
- "e"
  - "e" is a non-repeating character but not the first one in the sequence.
{: .choose_best #identify_unique title="Consider the string 'stress'. Can you identify the first non-repeating character?" points="1" answer="2"}

Remember, the objective is not just to find a non-repeating character but to identify the *first* non-repeating character based on its appearance in the string.

## Think Aloud
In an interview, clearly explaining your thought process is vital. Start by considering how you could track the number of occurrences for each character. Pseudocode can be helpful here.

## Test your code

```ruby
string = [
  "interviewprep",
  "loveprogramming",
  "abcdefghijklmnopqrstuvwxyz",
].sample

def first_uniq_char(string)
  # Your solution goes here
end
```
{: .repl #first_unique_character title="First Unique Character in a String" readonly_lines="[1,2,3,4,5]"}

```ruby
describe "First Unique Character in a String" do
  it "returns 1 for 'interviewprep'" do
    expect(first_uniq_char("interviewprep")).to eq 1
  end
end
```
{: .repl-test #first_unique_character_test_1 for="first_unique_character" title="First Unique Character returns 0 for 'interviewprep'" points="1"}

```ruby
describe "First Unique Character in a String" do
  it "returns 3 for 'iliveilaughicode'" do
    expect(first_uniq_char("iliveilaughicode")).to eq 3
  end
end
```
{: .repl-test #first_unique_character_test_2 for="first_unique_character" title="First Unique Character returns 2 for 'iliveilaughicode'" points="1"}

```ruby
describe "First Unique Character in a String" do
  it "returns -1 for 'aabb'" do
    expect(first_uniq_char("aabb")).to eq -1
  end
end
```
{: .repl-test #first_unique_character_test_3 for="first_unique_character" title="First Unique Character returns -1 for 'aabb'" points="1"}

## Tips and Clues for Solving the Problem
- **Hash**: Utilize a hash to keep track of character counts. This is crucial for efficiently determining if a character is unique.
- **String Iteration**: You will need to iterate over the string at least twice. The first pass to count occurrences, and the second to find the first unique character.
- **Edge Cases**: Consider what should happen if the string is empty. Additionally, consider how your solution behaves with different character cases (e.g., 'A' vs 'a').
- **Efficiency**: While a brute force solution might iterate through the string multiple times for each character, using a hash can significantly reduce the complexity, making it possible to solve the problem with just two passes over the string.

## Quiz

- What is a hash primarily used for in this problem?
- To keep track of the number of times each character appears in the string
  - Correct! This is the key to efficiently solving the problem, allowing for quick lookups of character counts.
- To convert characters into their ASCII values
  - Incorrect. While hashes can store various data types, this is not their primary use in this context.
- To sort the characters in the string
  - Incorrect. Hashes do not sort data; they are used for storing key-value pairs for quick access.
- To find the longest repeating character sequence
  - Incorrect. The focus here is on finding the first unique character, not the longest repeating sequence.
{: .choose_best #hash_use title="What is a hash primarily used for in this problem?" points="1" answer="1"}

- Which method is effective for iterating over each character in a string in Ruby?
- `chars`
  - Correct! The `chars` method splits the string into an array of characters, which can then be iterated over.
- `split`
  - Partially correct. `split` can be used to turn a string into an array, but without parameters, it splits on whitespace, not individual characters.
- `each_char`
  - Correct! `each_char` iterates over each character in the string, which is ideal for this problem.
- All of the above
  - Correct! While `each_char` and `chars` are directly applicable, `split` can be used with parameters to achieve a similar effect.
{: .choose_best #iterating_characters title="Which method is effective for iterating over each character in a string in Ruby?" points="1" answer="4"}

## Conclusion
In this lesson, we've tackled the challenge of finding the first unique character in a string. By employing a hash to track character occurrences and carefully iterating over the string, we've devised an efficient strategy to solve this problem, demonstrating valuable techniques in handling string and hash operations in Ruby.

## Resources
- [leetcode](https://leetcode.com/problems/first-unique-character-in-a-string)
