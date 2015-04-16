## Module_3: Assignment

For this assignment, you're going to for this repository to your own Github account and clone that repository locally. Inside the repo you'll find a directory called server. Inside that directory you'll find three placeholder files: server.js, enhancedDate.js, and trucks.js. 

1. In enhancedDate.js, use the code you wrote for the Module_2 assignment to export a node module (see the [slides](http://slides.com/kinakuta/deck-6#/2) starting with slide #2 that supports the same methods it did in your original module (enhancedDate.js from Module_2.) Refer to how Node modules are defined. You won't be using the immediately invoked function execution syntax nor will you be using the return keyword, you'll want to use module.exports as demonstrated in class (or additionally explained [here](https://quickleft.com/blog/creating-and-publishing-a-node-js-module/))
2. In trucks.js, you'll find an array of food-truck objects. Each object has a name, a food type, and a schedule of days the food truck is available. Using this data, export another node module with a single method: __filterByDay(day)__ where the "day" parameter should be passed an argument that is the name of a day of the week. Use the [underscore](https://www.npmjs.com/package/underscore) library in that module to [filter](http://underscorejs.org/#filter) the list of trucks by the day name passed in to __filterByDay()__.
3. In server.js, you're going to build an [http server](http://slides.com/kinakuta/deck-5#/13) (refer to the Node slides starting with slide #13.) The server should listen for request events, and handle them by writing to the response the following message:     "Today is [day name], [month name] [date]. The food trucks available are :"    Follow this with a list of food trucks obtained by calling __filterByDay()__. Calling that function will return an array of objects. You'll want to loop through that array, getting the name of each truck from the truck object and adding it to a string that you'll build up. Because you'll just be outputting text, add the newline character to the end of each food-truck name: '\n' (e.g. truckString += trucks[i].name + '\n'; ). Once you're done looping through the list, write the string to the response stream (`response.write(your_string);`), then close the stream (`response.end();`). Again, refer to the [existing code](http://slides.com/kinakuta/deck-5#/13) we looked at for how you write a simple http server in Node.

4. Add a package.json file to your project directory, and include any dependencies necessary for this (hint: you're using underscore in trucks.js). You can use the command: `npm init` to create the file for you, and it will ask you some questions about what should go in the file. The only thing you should actually worry about is the name for now. Everything else you can hit 'enter' or 'return' and take the default values.
