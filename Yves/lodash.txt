const _ = {
  //clamp
  clamp(number, lower, upper) {
    const lowerClampedValue = Math.max(number, lower);
    const clampedValue = Math.min(lowerClampedValue, upper);
    return clampedValue;
  },
  //inRange
  inRange(number, start, end) {
    if(end === undefined) {
      end = start;
      start = 0;
    };
    if(start > end) {
      const temp = end;
      end = start;
      start = temp;
    };
    const isInRange = start <= number && number < end;
    if(isInRange) {
      return true;
    } else {
      return false;
    };
   return isInRange
  },
//words
 words(string){
   const words = string.split(' ');
   return words;
 },
//pad
pad(string, length)  {
  if(length <= string.length){
    return string;
  }
  const startPaddingLength = Math.floor((length - string.length) / 2);
  const endPaddingLength = (length - string.length - startPaddingLength)
  const paddedString = ' '.repeat(startPaddingLength) + string + ' ' .repeat(endPaddingLength);
  return paddedString;
} ,
 //has
has(object, key) {
  var hasValue = object[key];
  if (hasValue !== undefined) {
    return true;
  }
else {
  return false; 
 }
}, 
//invert  
invert(object) {
  let invertedObject = {};
  for (let key in object) {
  const originalValue = object[key];
  invertedObject = {originalValue: key}
    }
    return invertedObject;
},
//findKey  
findKey(object, predicate){
  for (let key in object){
let value = object[key];
let predicateReturnValue = predicate(value);
if  (predicateReturnValue)  {
  return key;
} 
    else {
      return undefined;
    }
  }
},
//drop  
drop(array, n) {
  if (n === undefined) {
      let n = 1
      return array.slice(n, array.length);
    }
  let droppedArray = array.slice(n, array.length)  
  return droppedArray;
},
//dropwhile
dropWhile(array, predicate) {
  const callback = (element, index) => {
  return !predicate(element, index, array) }
  let dropNumber = array.findIndex(callback);
  let droppedArray = this.drop(array, dropNumber);
  return droppedArray;
}, 
//chunk
chunk(array, size)  {
  if (size === undefined){
    let size = 1
  }
  let arrayChunks = [];
  for (i = 0; i <array.length; i + size ){
    let arrayChunk = array.slice(i, i += size)
    arrayChunks.push(arrayChunk)
  } return arrayChunks;
}

};  
  
  // Do not write or modify code below this line.
module.exports = _;