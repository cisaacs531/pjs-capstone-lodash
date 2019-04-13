const _ = {};

//Implement _.clamp()
function clamp(number, lower, upper) {
  const lowerClampedValue = Math.max(number, lower);
  const clampedValue  = Math.min(lowerClampedValue, upper);
  
  return clampedValue;
}

console.log(clamp(100, 5, 8));


//Implement .inRange()
function inRange(number, start, end){
  if (end === "undefined") {
    return false;
  } else if (end === start) {
    return true;
  } else if (start === 0) {
    return true;
  } else if (start > end) {
    let temp = end;
    end = start;
    start = temp;
   // console.log(temp);
}
const isInRange = (start <= number && number < end);
return isInRange;
}

console.log(inRange(1, 2));  
console.log(inRange(3, 4, 2)); 
console.log(inRange(2, 1, 3)); 
console.log(inRange(0, 1, 3)); 
console.log(inRange(4, 1, 3));
console.log(inRange(1, 1, 33));
console.log(inRange(3, 1, 3));
//console.log(inRange.isInRange); 


  
//Implement .words()
function words(string) {
  const words = string.split(' ');
  return words;
}
console.log(words("hi there you"));



//Implement .pad()
 function pad(string, length) {
  if (string.length >= length) {
    return string;
  }
  const startPaddingLength = Math.floor((length - string.length) / 2);
  const endPaddingLength = (length - string.length - startPaddingLength);
  const paddedString = ' '.repeat(startPaddingLength) + string 
  + ' '.repeat(endPaddingLength);
  return paddedString;
  
  }
  console.log(pad('abc', 10));


//Implement _.has()
function has(object, key) {
  const hasValue = object[key];
  if(hasValue != undefined) {
    return true;
    }return false;
  
    } 
var object = { 'a': { 'b': 2 } };
var other = has({ 'a': has({ 'b': 2 }) });
 
console.log(has(object, 'a'));
console.log(has(other, 'a'));
console.log(has(object, 'c'));


//Implement _.invert()

function invert(object) {
  invertedObject = {};
  for (let key in object) {
    const originalValue = object[key];
    invertedObject = {originalValue : key}
}
  return invertedObject;
}

var object = { 'a': 1, 'b': 2, 'c': 1 };
console.log(invert(object));



//Implement _.findKey()
function findKey(object, predicate) {
  for (let key in object) {
    let value = object[key];
    let predicateReturnValue = predicate(value);
    if(predicateReturnValue) {
      return key;
    } 
  }
      
      return undefined;
    };


const users = {
  'barney':  { 'age': 36, 'active': true },
  'fred':    { 'age': 40, 'active': false },
  'pebbles': { 'age': 1,  'active': true }
};

console.log(findKey(users, function(o) { return o.age < 40; }));


//Implement _.drop()
function drop(array, n) {
  if (n === undefined) {
    n = 1;
  }
    let droppedArray = array.slice(n, array.length);
    return droppedArray;
}

console.log(drop([1, 2, 3]));
console.log(drop([1, 2, 3], 2));
console.log(drop([1, 2, 3], 5));
console.log(drop([1, 2, 3], 0));



//Implement _.dropWhile()
function dropWhile(array, predicate) {
  const callBack = (element, index) => {
    return !predicate(element, index, array);
  };
  let dropNumber = array.findIndex(callBack); 
  let droppedArray = this.drop(array, dropNumber);
    return droppedArray;
  }

console.log(dropWhile);


//Implement _.chunk()
function chunk(array, size) {
  if (size === undefined) {
    size = 1;
  }
    let arrayChunks  = [];
  for (let i = 0; i < array.length; i += size) {
    let arrayChunk = array.slice(i, i + size);
    arrayChunks.push(arrayChunk);
  }
  return arrayChunks;
}
console.log(chunk(['a', 'b', 'c', 'd'], 2));
console.log(chunk(['a', 'b', 'c', 'd'], 3));

// Do not write or modify code below this line.
module.exports = _;