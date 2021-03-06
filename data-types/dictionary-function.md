# ডিকশনারি ফাংশন

পাইথনের লিস্টে যেমন নির্দিষ্ট কোন ইনডেক্সে নতুন একটি ভ্যালু সেট করা যেত, তেমনি ডিকশনারির ক্ষেত্রেও একটি key তে থাকা কোন ভ্যালুকে আপডেট করে নতুন একটি ভ্যালু সেট করা যায়। যেমন -

লিস্টের ক্ষেত্রে উদাহরণ -

```python
my_list = [2, 4, 6, 7]
my_list[3] = 8

print(my_list)
```

আউটপুট,

```python
[2, 4, 6, 8]
```

ডিকশনারির ক্ষেত্রে -

```python
my_nums = {1 : 1, 2 : 4, 3 : 9, 4 : "What?"}
my_nums[4] = 16

print(my_nums)
```

আউটপুট,

```python
{1: 1, 2: 4, 3: 9, 4: 16}
```

অর্থাৎ এ ক্ষেত্রে লিস্ট এবং ডিকশনারি একই আচরণ করে। কিন্তু লিস্টের ক্ষেত্রে ম্যানুয়ালি নতুন একটি ইনডেক্স এবং তার ভ্যালু যুক্ত করা যায় না। যেমন -

```python
my_list = [2, 4, 6, 8]
my_list[4] = 10
```

আউটপুট,

```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list assignment index out of range
```

অর্থাৎ, যদিও `my_list = [2, 4, 6, 8]` এর ইনডেক্স `3` পর্যন্ত এবং আমরা চেষ্টা করেছি ম্যানুয়ালি একটি চতুর্থ ইনডেক্সে নতুন একটি ভ্যালু যুক্ত করতে, কিন্তু তা সম্ভব হয় নি। কারন লিস্টের ইনডেক্স স্বয়ংক্রিয়ভাবে একবার তৈরি হয়ে যায় এবং এভাবে ম্যানুয়ালি ইন্ডেক্সিং করা যায় না। বরং `append` ব্যবহার করা হয়।

কিন্তু চাইলে ডিকশনারির ক্ষেত্রে ম্যানুয়ালি নতুন key এবং সাথে এর জন্য একটি ভ্যালু সহ আরেকটি লিস্টে যুক্ত করা যায়। যেমন -

```python
my_nums = {1 : 1, 2 : 4, 3 : 9, 4 : 16}
my_nums[5] = 25

print(my_nums)
```

আউটপুট,

```text
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

অর্থাৎ নতুন key `5` এবং এর ভ্যালু `25` দুটোই `my_nums` ডিকশনারিতে ম্যানুয়ালি যুক্ত করা হয়েছে।

**key খোঁজা**  
যদি আমরা চেক করতে চাই যে একটি ডিকশনারিতে নির্দিষ্ট কোন একটি key আছে কিনা তার জন্য `in` এবং `not in` ব্যবহার করা যায়। বলে রাখা ভালো, এভাবে কিন্তু লিস্টের ক্ষেত্রেও চেক করা যায়। উদাহরণ -

```python
nums = {1: "one", 2: "two", 3: "three",}

print(1 in nums)
print("three" in nums)
print(4 not in nums)
```

আউটপুট,

```python
True
False
True
```

**get এর ব্যবহার**  
উপরে আমরা দেখেছি যে ডিকশনারি থেকে ডাটা অ্যাক্সেস এর জন্য লিস্টের মতই ইনডেক্স দিয়ে তথা key ব্যবহার করা যায়। কিন্তু এভাবে ডাটা অ্যাক্সেসের একটু অসুবিধা আছে। যেমন -

```python
my_nums = {1 : 1, 2 : 4, 3 : 9, 4 : 16}
print(my_nums[5])
```

আউটপুট,

```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 5
```

অর্থাৎ যে key আলোচ্য ডিকশনারিতে নাই সেরকম key দিয়ে ডাটা অ্যাক্সেসের চেষ্টা করলে অনাকাঙ্ক্ষিত এরর তৈরি হবে যা প্রোগ্রাম বন্ধ করতে পারে। তাই ভালো প্র্যাকটিস হচ্ছে `get` মেথডের ব্যবহার করা। নিচের মত করে -

```python
my_nums = {1 : 1, 2 : 4, 3 : 9, 4 : 16}
print(my_nums.get(5))
```

আউটপুট,

```text
None
```

অর্থাৎ এরর না তৈরি হয়ে বরং `None` রিটার্ন হবে। এমনকি চাইলে ডিফল্ট কোন ভ্যালুও পাওয়া যাবে যদি উক্ত key ওই ডিকশনারিতে না থাকে। যেমন -

```python
my_nums = {1 : 1, 2 : 4, 3 : 9, 4 : 16}
print(my_nums.get(5, "5 not in my numbers!"))
```

আউটপুট,

```python
5 not in my numbers!
```

> সংকলন - [নুহিল মেহেদী](https://nuhil.net)

