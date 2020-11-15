# Day 4: Work Out Big O Quiz Part 2

In this quiz, we'll calculate the time and space complexity for two of the algorithm challenges from Phase 1. After this quiz, we encourage you to look at your own solutions for the same problems and calculate Big O for them too.

1. Multiple-choice

Calculate the time and space complexity for the following code. We've included both JS and Ruby for the same function.

<h3>JavaScript</h3>
<pre>
<code>
// Assume function is always called with a positive number or 0

function recursiveCount(num = 0) {
  if (num >= 10) {
    return;
  }

  console.log(num);
  recursiveCount(num + 1);
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
# Assume function is always called with a positive number or 0

def recursive_count(num = 0)
  return if num >= 10

  puts num
  recursive_count(num + 1)
end
</code>
</pre>

- Time: O(1), Space: O(1)
  - Look at you answering questions like some kind of brilliant brain wizard! The base case never lets the value of <code>num</code> go over 10. This means that any time this function runs, it'll recurse at most 10 times adding up to 10 frames to the stack in memory. It runs in constant space and constant time!
- Time: O(n), Space: O(1)
  - Almost. It does use constant space since the number of frames has an upper limit of 10. However, it does not use linear time. Since we're assuming the value of <code>num</code> will only be 0 or higher, what is the runtime if <code>num</code> is 100 versus 1?
- Time: O(n), Space: O(n)
  - Not quite. This procedure doesn't use linear time or space. Assuming that <code>num</code> is always 0 or higher, how many frames at most will be on the stack? Think about what happnes when <code>num</code> is 0 versus 100.
- I don't know
  - Don't worry. With time and practice, it'll start to sink in.

2. Multiple-choice

Calculate the time and space complexity for the following code. We've included both JS and Ruby for the same function.

<h3>JavaScript</h3>
<pre>
<code>
function recursiveSearch(arr, target) {
  if (arr.length === 0) {
    return false;
  }

  if (arr[0] === target) {
    return true;
  }

  return recursiveSearch(arr.slice(1), target);
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def recursive_search(arr, target)
  return false if arr.empty?
  return true if arr.first == target

  recursive_search(arr[1..-1], target)
end
</code>
</pre>

- Time: O(n), Space: O(n)
  - Exactly! The number of frames placed on the stack is equal to the length of the array, so this function runs in linear time and space. Remember, in the worst case, this procedure will recurse until the array is empty, and it will then start returning up the stack. The maximum runtime is also linear, because the total number of frames will at most be the length of the array.
- Time: O(n<sup>2</sup>), Space: O(n)
  - Not quite. It will use linear space, but it won't use quadratic time. Think about how many times the algorithm will recurse in the worst case - when the target isn't in the array.
- Time: O(1), Space: O(1)
  - Not really. This algorithm doesn't use constant space or time. Imagine the input array is <code>[1, 2, 3]</code> and the target is <code>4</code>. How many frames will be placed on the stack? How many recursive calls in total will be made? 
- I don't know
  - Don't worry. With time and practice, it'll start to sink in.