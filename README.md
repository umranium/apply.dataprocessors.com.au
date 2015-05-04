# apply.dataprocessors.com.au
Solution to http://apply.dataprocessors.com.au/

	(function() {
		// Load the script
		var script = document.createElement("SCRIPT");
		script.src = 'https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js';
		script.type = 'text/javascript';
		document.getElementsByTagName("head")[0].appendChild(script);

		// Poll for jQuery to come into existence
		var checkReady = function(callback) {
			if (window.jQuery) {
				callback(jQuery);
			}
			else {
				window.setTimeout(function() { checkReady(callback); }, 100);
			}
		};

		// Start polling...
		checkReady(function($) {
			//	Find the text 'Question'
			v = $('*:contains("Question")');
			//	Get the last (looks like the deepest element also) result
			v = v.last();
			//	The element is a paragraph element, obtain it's text.
			v = v.text();
			//	Get string after the colon, evaluate it, and store the result in v
			v = eval(v.substring(v.indexOf(':')+1))

			//	Find the input element with the name 'value'
			inpt = $( "input[name='value']" )
			//	Assign the value v, to the input
			inpt.val(v);

			//	Find the input element with the name 'jobref' and assign the value 'PO44'
			jbref = $( "input[name='jobref']" )
			jbref.val('PO44');

			//	Find the element 'Submit' and simulate a click
			submt = $( "input[value='Submit']" )
			submt.click();
		
			//	Now wait and see results...
		});
	})();


1. Copy the javascript above into a text editor and change the value 'PO44' to the job reference number given in the advertisement.
2. Copy the edited script.
3. Using Google Chrome, open the javascript console.
4. Load the apply.dataprocessors.com.au webpage.
5. Immediately the page finishes loading, paste the edited script and press enter.
6. Wait for results. If the results say something like, "You need to submit within 1 second", try again and perhaps you'll be faster this time.

Script for the latest puzzle (as of 4 May 2015):

	(function() {
	    // Load the script
	    var script = document.createElement("SCRIPT");
	    script.src = 'https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js';
	    script.type = 'text/javascript';
	    document.getElementsByTagName("head")[0].appendChild(script);
	
	    // Poll for jQuery to come into existence
	    var checkReady = function(callback) {
	        if (window.jQuery) {
	            callback(jQuery);
	        }
	        else {
	            window.setTimeout(function() { checkReady(callback); }, 100);
	        }
	    };
	
	    // Start polling...
	    checkReady(function($) {
	    	v = $('img[src="filled_O.gif"]');
	        
	        //  Find the input element with the name 'value'
	        inpt = $( "input[name='value']" )
	        //  Assign the value v, to the input
	        inpt.val(v.length);
	
	        //  Find the input element with the name 'jobref' and assign the value 'PO44'
	        jbref = $( "input[name='jobref']" )
	        jbref.val('PO57');
	
	        //  Find the element 'Submit' and simulate a click
	        submt = $( "input[value='Submit']" )
	        submt.click();
	
	        //  Now wait and see results...
	    });
	})();

