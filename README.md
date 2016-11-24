# Karnaugh-s-detonating-timer-a-k-map-primer-
var segments = [
  function segment1(b2, b1, b0) { return 1},
  function segment2(b2, b1, b0) { return 1},
  function segment3(b2, b1, b0) { return (!b2&!b1&!b0)|(b0&!b2)},
  function segment4(b2, b1, b0) { return b2|!b1},
  function segment5(b2, b1, b0) { return 1},
  function segment6(b2, b1, b0) { return (!b2&!b1&!b0)|(b0&!b2)},
  function segment7(b2, b1, b0) { return  (b2|b1|b0)&(!b2|b1|!b0)}
  ];

function segment7(b2, b1, b0) { return  b1 | !b2&!b1&b0 | b2&!b1&!b0; }  	//initial

function segment7(b2, b1, b0) { return  !b0&!b2&b1 | !b0&b2&!b1 | b0&b2 } 	//wrong

function segment7(b2, b1, b0) { return  (b2|b1|b0)&(!b2|b1|!b0) }		//taking negative K-map values and applying De Morgan's laws

function segment3(b2, b1, b0) { return (!b2&!b1&!b0)|(b0&!b2)} 			//segment6 and segment 3 are the same

function segment4(b2, b1, b0) { return b2|!b1 }  				//...that could be replaced with just !b1

function check(fun) {								//to keep heads up the truth table
	
	var b2 = 0;
	var b1 = 0;
	var b0 = 0;
	
	console.log(fun(b2,b1,b0));

	var b2 = 0;
	var b1 = 0;
	var b0 = 1;
	
	console.log(fun(b2,b1,b0));
	
	var b2 = 0;
	var b1 = 1;
	var b0 = 0;
	
	console.log(fun(b2,b1,b0));

	var b2 = 0;
	var b1 = 1;
	var b0 = 1;
	
	console.log(fun(b2,b1,b0));

	var b2 = 1;
	var b1 = 0;
	var b0 = 0;
	
	console.log(fun(b2,b1,b0));

	var b2 = 1;
	var b1 = 0;
	var b0 = 1;
	
	console.log(fun(b2,b1,b0));

}
