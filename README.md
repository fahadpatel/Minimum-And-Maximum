# Minimum-And-Maximum
Minimum and Maximum Sum of 4 HackerRank Solution
<?php

/*
 * Complete the 'miniMaxSum' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function miniMaxSum($arr) {
    // Write your code here
$count_no= count($arr);

sort($arr);
$sum_array=array();
$prevIndex=-1;

for($i=0;$i<$count_no; $i++){
  
  $sum=0;
  $num2array=array();
  $count_1=0;
  for($j=0; $j<$count_no;$j++){
    
    
    
   if($j!=$prevIndex ){
     
     if($count_1 !=4){
          $num2array[$j]=$arr[$j];
          $count_1++;
          $prevIndex=$i;
      }  
     } 
  }
   
  $sum =array_sum($num2array);
  $sum_array[$i]=$sum;
 
}

print(min($sum_array).' '.max($sum_array));

}

$arr_temp = rtrim(fgets(STDIN));

$arr = array_map('intval', preg_split('/ /', $arr_temp, -1, PREG_SPLIT_NO_EMPTY));

miniMaxSum($arr);
