# HW 6 - {GifTastic}


## Description on how to use the app

-Click the add sport button to add your favorite sports on dash and click your sport button the load gifs about it.

## Requirements
1. Before you can make any part of our site work, you need to create an array of strings, each one related to a topic that interests you. Save it to a variable called `topics`. 

   * We chose animals for our theme, but you can make a list to your own liking.

2. Your app should take the topics in this array and create buttons in your HTML.

   * Try using a loop that appends a button for each string in the array.

3. When the user clicks on a button, the page should grab 10 static, non-animated gif images from the GIPHY API and place them on the page. 

4. When the user clicks one of the still GIPHY images, the gif should animate. If the user clicks the gif again, it should stop playing.

5. Under every gif, display its rating (PG, G, so on). 

   * This data is provided by the GIPHY API.
   * Only once you get images displaying with button presses should you move on to the next step.

6. Add a form to your page takes the value from a user input box and adds it into your `topics` array. Then make a function call that takes each topic in the array remakes the buttons on the page. are understandable

## Technologies Used

- Jquery for Dom Manipulation
- AJAX for API GET requests

## Code Explaination



### AJAX Request to Giphy (Example)
I created a function that allowed me to make an AJAX request to the Giphy API and then allowed me to pass through a callback function in order to further process the JSON object that was returned. 

```
var sport = $(this).attr("data-name");
	 			
	  


	 var queryURL = "http://api.giphy.com/v1/gifs/search?q=" +
	        sport + "&api_key=dc6zaTOxFJmzC&limit=10";


 $.ajax({
          url: queryURL,
          method: "GET"
        })

		.done(function(response){
          console.log(queryURL);