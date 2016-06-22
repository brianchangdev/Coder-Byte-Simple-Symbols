# Coder-Byte-Simple-Symbols

/* Using the JavaScript language, have the function SimpleSymbols(str) take the str 
parameter being passed and determine if it is an acceptable sequence by either 
returning the string true or false. The str parameter will be composed of + and = 
symbols with several letters between them (ie. ++d+===+c++==a) and for the string 
to be true each letter must be surrounded by a + symbol. So the string to the left
would be false. The string will not be empty and will have at least one letter. */

RegEx solution:


    function SimpleSymbols(str){
    // takes a string, extracts its letters using regex
    var letters = str.match(/[a-z]/ig);
    // takes a string, extracts acceptable 'true' sequence of: "+letter+"
    var matches = str.match(/\+[a-z]\+/ig);
    // If the string is empty or there are no matches, return false
    // "!" indicates whether a statement can evaluate to false
    if (! str.length || ! matches){
	    return false;
      }
      // if there are as many letters as matches, return true, else return false.
	  if (letters.length == matches.length){
	      return true;
      }else{
      return false;
      }
    }
      console.log(SimpleSymbols("++d+===+c++==a"));
      // should return true

