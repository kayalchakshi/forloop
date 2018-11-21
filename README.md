# forloop


<html>
<head></head>
<body>
<script>

var list =[4,5,6];


list.forEach(function(element,i) 
{
   console.log(i); // "0", "1", "2",
}
);

list.forEach(function(index,i) 
{
   console.log(i); // "0", "1", "2",
}
);

list.forEach(function(element,index,i) 
{
   console.log(i); // (3) [4, 5, 6],(3) [4, 5, 6],(3) [4, 5, 6]
}
);

list.forEach(function(i) 
{
   console.log(i); // "4", "5", "6",
}
);

for (let i in list) 
{
   console.log(i); // "0", "1", "2"
}

for (let i of list) 
{
   console.log(i); // "4", "5", "6"
}
</script>
</body>
</html>
