How to Highlight the Searched String Result using JavaScript ?
Given below is an HTML document which is basically about how to highlight the searched string result. In 
this article, we are using HTML, CSS, JavaScript, Bootstrap and mark.js to make our website more 
effective. Moreover, exclusively for highlighting the searched string among a given context or 
paragraph, mark.js plays a vital role in this particular code. Before approaching this problem, 
keep a mark of my words that, the problem can be solved by many other approaches but I think this 
can also be a way better approach towards this given problem.

What is mark.js?

mark.js is a simple JavaScript tool that is used to highlight the text. Which is used to dynamically 
mark search terms or custom regular expression and offer some built-in options like diacritics support, 
separate word search etc.

 

Approach:

	- First thing first when you are entering some string on the search box and press the search button 
	  then a simple JavaScript function will call named as highlight() which has the main role is to 
	  highlight the search text that you had entered in the search box. In this small, we are going to 
	  use mark.js code to highlight the text.
	- There are many built-in functions in mark.js but we are using two functions for our requirement 
	  that is mark() and unmark() function respectively. Here mark() is used to highlight the search 
	  text and unmark() is used to remove highlighting the text that is highlighted before.

Syntax of mark():
```
var context = document.querySelector(".context");
var obj = new Mark(context);
obj.mark(searchkeyword [, options]);
```

	- Let’s understand this code in a bit of technical manner,
		- First we declare a variable which contains context from which it is going to find and highlight 
		  the searched text. 
		- Create an object of the mark and then call the mark() method through the obj that you create 
		  previously.
		- It takes two parameters with it i.e, one is searched keyword and another is optional.

Syntax of unmark():
```
var context = document.querySelector(".context");
var obj = new Mark(context);
obj.unmark(options);
```

	- This is near about same as the above technique but the only minute difference is that unmark() 
	  method takes only one argument with it i.e, optional. Further, if you want to change the color 
	  and padding of highlighter then we need to make slight changes in the CSS code inside mark which 
	  is given below:
```
mark {
    color: black;
    background: green;
    padding: 5px;
}
```
	- Hope you have successfully followed the above steps in order to make changes in the color of the 
	  particular highlighted text. But here make sure that there should not be any string left highlighted 
	  with any particular color if it is so then don’t forget to un-highlight the text which was searched 
	  previously. Thereafter, mark the new string which is to be searched and you can change its color 
	  according to your convenience. 
	- For more information follow <a href="https://markjs.io/">this page</a>.

```
<!DOCTYPE html> 
<html> 

<head> 
	<meta name="viewport" content= 
		"width=device-width, initial-scale=1.0"> 

	<!-- CDN of fontawsome -->
	<link rel="stylesheet" href= 
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"> 

	<!-- CDN of Bootstrap -->
	<link rel="stylesheet" href= 
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css"
		integrity= 
"sha384-rwoIResjU2yc3z8GV/NPeZWAv56rSmLldC3R/AZzGRnGxQQKnKkoFVhFQhNUwEyJ"
		crossorigin="anonymous"> 

	<!-- CDN of mark.js -->
	<script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"
		integrity= 
"sha512-5CYOlHXGh6QpOFA/TeTylKLWfB3ftPsde7AnmhuitiTX4K5SqCLBeKro6sPS8ilsz1Q4NRx3v8Ko2IBiszzdww=="
		crossorigin="anonymous"> 
	</script> 
	
	<!-- CDN of google font -->
	<style> 
		@import url('https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@500&display=swap' 
		); 
	</style> 

	<style> 
		mark.a0 { 
			color: black; 
			padding: 5px; 
			background: greenyellow; 
		} 

		mark.a1 { 
			color: black; 
			padding: 5px; 
			background: cyan; 
		} 

		mark.a2 { 
			color: black; 
			padding: 5px; 
			background: red; 
		} 

		mark.a3 { 
			color: white; 
			padding: 5px; 
			background: green; 
		} 

		mark.a4 { 
			color: black; 
			padding: 5px; 
			background: pink; 
		} 
	</style> 
</head> 

<body style="border:4px solid rgb(0, 128, 28);"> 
	<h1 style="font-family: 'Roboto Slab', 
		serif;text-align: center;color:green;"> 
		GeeksForGeeks 
	</h1> 
	<br><br> 

	<form> 
		<div class="container-fluid" align="center"> 
			<input type="text" size="30"
				placeholder="search..." id="searched"
				style="border: 1px solid green; 
						width:300px;height:30px;"> 

			<button type="button" class="btn-primary btn-sm"
				style="margin-left:-5px;height:32px;width:35px; 
						background-color:rgb(12, 138, 12); 
						border:0px;" onclick="highlight('0');"> 

				<i class="fa fa-search"></i> 
			</button> 
		</div> 
	</form> 
	<br><br> 
	
	<div align="center"> 
		<div> 
			<b><i>Choose the color of highlighter:</i></b> 
		</div> 
		<br> 
		<div style="background-color: cyan; 
			width: 20px; height: 20px; 
			display: inline-block; margin-left: -30px;" 
			onmouseover="highlight('1')"> 
		</div> 

		<div style="background-color: red; 
			width: 20px; height: 20px; 
			display: inline-block; margin-left: 10px;" 
			onmouseover="highlight('2')"> 
		</div> 

		<div style="background-color: green; 
			width: 20px; height: 20px; 
			display: inline-block; margin-left: 10px;" 
			onmouseover="highlight('3')"> 
		</div> 

		<div style="background-color: pink; 
			width: 20px; height: 20px; 
			display: inline-block; margin-left: 10px;" 
			onmouseover="highlight('4')"> 
		</div> 
	</div> 

	<div class="container-fluid" style= 
		"padding-left: 30%; padding-right: 30%; 
		padding-top: 5%;"> 

		<p class="select"> 
			GeeksforGeeks.org was created with a 
			goal in mind to provide well written, 
			well thought and well explained solutions 
			for selected questions.The core team of 
			five super geeks constituting of technology 
			lovers and computer science enthusiasts 
			have been constantly working in this 
			direction. 
		</p> 
	</div> 

	<script> 
		function highlight(param) { 

			// Select the whole paragraph 
			var ob = new Mark(document.querySelector(".select")); 

			// First unmark the highlighted word or letter 
			ob.unmark(); 

			// Highlight letter or word 
			ob.mark( 
				document.getElementById("searched").value, 
				{ className: 'a' + param } 
			); 
		} 
	</script> 
</body> 

</html> 
```

Output:
https://media.geeksforgeeks.org/wp-content/uploads/20201205194654/ezgif367aae8c64afa.gif
