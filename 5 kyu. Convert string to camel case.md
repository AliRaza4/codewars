###Description:

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized.

Examples:

```javascript
// returns "theStealthWarrior"
toCamelCase("the-stealth-warrior") 

// returns "TheStealthWarrior"
toCamelCase("The_Stealth_Warrior")
```

###Test Cases:

```javascript
Test.assertEquals(toCamelCase(''), '', "An empty string was provided but not returned")
Test.assertEquals(toCamelCase("the_stealth_warrior"), "theStealthWarrior", "toCamelCase('the_stealth_warrior') did not return correct value")
Test.assertEquals(toCamelCase("The-Stealth-Warrior"), "TheStealthWarrior", "toCamelCase('The-Stealth-Warrior') did not return correct value")
Test.assertEquals(toCamelCase("A-B-C"), "ABC", "toCamelCase('A-B-C') did not return correct value")
```

###My solution

```javascript
function toCamelCase(str){
  str = str.split('');
  return str.map(function(el, i){
    if(el == '-' || el == '_'){
      el = str[i+1].toUpperCase();
      str.splice(i+1, 1);
    }
    return el;
  }).join('');
}
```
###solution in php

function toCamelCase($str){

 if(preg_match('/^[a-z]+-[a-z]+-[a-z]+$/i', $str)){
		$t = explode("-", $str);
		$comb = "";
		foreach ($t as $key => $value) {
			if($key==0 ){
				continue;
			}
			// echo(ucwords($value));
			$capitalize = ucwords($value);
			$comb .= $capitalize;
		}
		$concat = $t[0].$comb;
		return $concat;
	}
	else{
		$t = explode("_", $str);
		$comb = "";
		foreach ($t as $key => $value) {
			if($key==0 ){
				continue;
			}
			// echo(ucwords($value));
			$capitalize = ucwords($value);
			$comb .= $capitalize;
		}
		$concat = $t[0].$comb;
		return $concat;
	} 

}
