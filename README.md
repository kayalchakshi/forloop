# forloop
The difference between foreach, for of and for in loops.

A collection is an object which contains a group of elements. For example: arrays, set, list, custom collections etc.

foreach is an method that is available only in Array objects. It allows you to iterate through elements of an array. When invoked it takes a callback function and invokes the callback once for every array element. The callback can access both index and value of the array elements. foreach is available only for looping arrays.

for in is used to loop through properties of an object. It can be any object. for in allows you to access the keys of the object but doesn’t provide reference to the values. In JavaScript object properties themselves have internal properties. One of the internal properties is [[Enumerable]]. for in will only walkthrough a property if it has [[Enumerbale]] set to true. It not used to iterate elements of an collection rather used to iterate properties of objects.

for of is a new way for iterating collections. Its introduced in ES6. Earlier you had to use for or while loop to iterate through elements of an collection. For for of to work on an collection, the collection must have an [Symbol.iterator] property.

A Comparison
                  for..in	               for..of
Applies to	      Enumerable Properties	Iterable Collections
Use with Objects?	Yes	                  No
Use with Arrays?	Yes, but not advised	Yes
Use with Strings?	Yes, but not advised	Yes

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
