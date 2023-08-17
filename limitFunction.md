```php
function limit_text($text, $limit) {
    if (str_word_count($text, 0) > $limit) {
        $words = str_word_count($text, 2);
        $pos   = array_keys($words);
        $text  = substr($text, 0, $pos[$limit]) . '...';
    }
    return $text;
}
```

1.  The function first checks if the word count of the input `$text` is greater than the specified `$limit`. It uses the `str_word_count` function with the second parameter set to 0 to count the number of words in the text. If the word count is already within the limit, the function returns the original text as it is.
    
2.  If the word count exceeds the limit, the function proceeds to shorten the text. It uses the `str_word_count` function again, but this time with the second parameter set to 2. This variant of `str_word_count` returns an array where the keys are the positions of each word in the text.
    
3.  The function stores the keys (positions) of the words in the `$pos` variable.
    
4.  It then uses the `substr` function to extract the portion of the original text starting from the beginning and ending at the position of the word that corresponds to the specified `$limit`. It appends an ellipsis ("...") to indicate that the text has been truncated.
    
5.  Finally, the shortened text is returned as the result of the function.

## Str_word_count() function

```php
str_word_count(string `$string`, int `$format` = 0, ?string `$characters` = `null`): array|int
```

**Format

Specify the return value of this function. The current supported values are:

-   0 - returns the number of words found
-   1 - returns an array containing all the words found inside the `string`
-   2 - returns an associative array, where the key is the numeric position of the word inside the `string` and the value is the actual word itself

### Example 1: Counting the number of words in a string:

```php
$text = "Hello, how are you?";
$wordCount = str_word_count($text);
echo $wordCount; // Output: 4

```

### Example 2: Counting the number of words and returning an array of words:

```php
$text = "The quick brown fox";
$words = str_word_count($text, 1);
print_r($words);
/* Output:
Array
(
    [0] => The
    [1] => quick
    [2] => brown
    [3] => fox
)
*/
```

### Example 3: Counting the number of words and getting the positions of each word:

```php
$text = "I love coding";
$wordPositions = str_word_count($text, 2);
print_r($wordPositions);
/* Output:
Array
(
    [0] => 0
    [1] => 2
    [2] => 7
)
*/
```

```mathematica
Position:  0  1  2  3  4  5  6  7  8  9 10
Character: I     l  o  v  e     c  o  d  i  n  g
```

## substr() function

is used to extract a substring from `$text` starting at position 0 and ending at the position specified by `$pos[$limit]`.

-   ` $text` is the original string from which the substring will be extracted.
-   `0` is the starting position of the substring. In this case, it is set to 0, which means the substring will start from the beginning of the string.
-   `$pos[$limit]` is the ending position of the substring. Here, `$pos` is an array that contains the positions of each word in the string, as obtained from `str_word_count()` with the second parameter set to 2. `$limit` is the specified limit of words. By accessing `$pos[$limit]`, the function retrieves the position of the word that corresponds to the limit. For example, if `$limit` is 3, `$pos[3]` will give the position of the third word in the string.

### Examples

```php
echo substr('abcdef', 1); // bcdef  
echo substr("abcdef", 1, null); // bcdef; prior to PHP 8.0.0, empty string was returned  
echo substr('abcdef', 1, 3); // bcd  
echo substr('abcdef', 0, 4); // abcd  
echo substr('abcdef', 0, 8); // abcdef  
echo substr('abcdef', -1, 1); // f  
  
// Accessing single characters in a string  
// can also be achieved using "square brackets"  
$string = 'abcdef';  
echo $string[0]; // a  
echo $string[3]; // d  
echo $string[strlen($string)-1]; // f  
```