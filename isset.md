# isset vs !empty
#isset #empty 
-if you want to check if a variable has been set or not, use `isset()`. If you want to check if a variable has a non-empty value, use `!empty()`. 
変数が設定されているかどうかを確認したい場合は、`isset()`を使用してください。変数に空でない値があるかどうかを確認したい場合は、`!empty()`を使用してください。
-isset is usually used for text. radio button is not text, so !empty is used.

# intval()
#intvalMethod
`intval()` is used to convert it to an integer.
If the input parameter is not a string, `intval()` will try to convert it to an integer directly. If the parameter cannot be converted to an integer, `intval()` will return 0.

$num = "42";
$int_num = intval($num);
echo $int_num; // Output: 42