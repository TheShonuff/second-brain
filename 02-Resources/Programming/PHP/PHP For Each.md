---
title: PHP For Each
Created: 2024-01-13 22:33
tags:
  - php
aliases:
---
# PHP For Each
- used for iterating over an array.

```PHP
$counting_array = [1,2,3,4,5,6,7,8,9,10];

foreach($counting_aray as $count){
	echo "The count is: " . $count . "\n";
}
```

- The sytanx can be adjust to access key / value pairs

```PHP
$details_array = ["color" => "blue", "shape" => "square"];

foreach ($details_array as $detail) {
  echo "The detail is: " . $detail . "\n";
}
```





