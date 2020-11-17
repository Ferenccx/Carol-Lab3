// 1. Declare a variable named submissions that is initialized to an array with the following
// objects:
var submissions = [
    {name: "Jane", score: 95, date: "2020-01-24", passed: true},
    {name: "Joe", score: 77, date: "2018-05-14", passed: true},
    {name: "Jack", score: 59, date: "2019-07-05", passed: false},
    {name: "Jill", score: 88, date: "2020-04-22", passed: true}
  ];

//2. Declare a function add Submission
// parameters array, newName, newScore, newDate
//Functionality: construct an object and push it into the array. The object must
//have the same properties as the objects already in the array. Use conditional
//statements to set the value for the passed property to true if the score is
//greater than or equal to 60 and false otherwise.

function addSubmission(array, newName, newScore, newDate){

    if(newScore >= 60){
        newPassed = true;
    }else{
        newPassed = false;
    }
    return array.push({name: newName, score: newScore, date: newDate, passed: newPassed});
}


// 3. Declare a function named deleteSubmissionByIndex
// ○ Parameter(s): array, index
// ○ Functionality: remove the object from the array at the specified index using the
// splice method.

function deleteSubmissionByIndex(array, index) {
  array.splice(index, 1);
}

deleteSubmissionByIndex(submissions, 2);
console.log(submissions);


// 4. Declare a function named deleteSubmissionByName
// ○ Parameter(s): array, name
// ○ Functionality: remove the object from the array that has the provided name.
// Incorporate the findIndex method and the splice method.

function deleteSubmissionByName(array, index){


  function deleteSubmissionByName(array, name) {
    let subIndex = array.findIndex(submission => submission.name === name);
    array.splice(subIndex, 1);
}

// deleteSubmissionByName(submissions, 'Jill');
// console.log(submissions);


// 5. Declare a function named editSubmission
// ○ Parameter(s): array, index, score
// ○ Functionality: update an object’s score in the array at the specified index. Use
// conditional statements to set the value for the passed property to true if the
// score is greater than or equal to 60 and false otherwise.
// continued on the next page…
// Grand Circus Detroit 2020

function editSubmission(array, index, score) {
  if (score >= 60) {
      passed = true;
  }
  else {
      passed = false;
  };
  array[index].score = score;
  array[index].passed = passed;
};
 
// editSubmission(submissions, 1, 60);
// editSubmission(submissions, 0, 59);
// console.log(submissions);


// 6. Declare a function named findSubmissionByName
// ○ Parameter(s): array, name
// ○ Functionality: return the object in the array that has the provided name. Use the
// find method.

  function findSubmissionByName(array, name) {
    const found = array.find(array => array.name === name);
    console.log(found);
};

findSubmissionByName(submissions, 'Carol');

// 7. Declare a function named findLowestScore
// ○ Parameter(s): array
// ○ Functionality: return the object in the array that has the lowest score. Use the
// forEach method to loop through the whole array.


  function getLowestScore(array) {
    let lowestScore = 105;
    let lowestStudent = null;
    array.forEach(function (item) {
        if (item.score < lowestScore) {
            lowestScore = item.score;
            lowestStudent = item;
        }
    });
    return lowestStudent;
};
let lowestStudent = getLowestScore(submissions)

console.log(lowestStudent);


// 8. Declare a function named findAverageScore
// ○ Parameter(s): array
// ○ Functionality: return the average quiz score. Use a for...of loop.

function findAverageScore(array) {
  let sum = 0;
  for (let item of array) {
      {
          sum += item.score;
      }
      let avg = sum / array.length;
      return avg; 
  }
};
let avg = findAverageScore(submissions)

console.log(avg);



// 9. Declare a function named filterPassing
// ○ Parameter(s): array
// ○ Functionality: return a new array using the filter method. The filter method
// should find objects in the array that have passing scores.

function filterPassing(array){

  let passingScore = array.filter(submission => submission.score >= 60);
return passingScore;

 }
let passer = filterPassing(submissions);
console.log(passer)



// 10. Declare a function named filter90AndAbove
// ○ Parameter(s): array
// ○ Functionality: return a new array using the filter method. The filter method
// should find objects in the array that have scores greater than or equal to 90.

// function addSubmissionfilter90AndAbove(array){
// 
//function filter90AndAbove(array){

  function filter90AndAbove(array) {
    let filterNum = array.filter(function(submission) {
        return submission.score >= 90;
    });
    console.log(filterNum);
}
filter90AndAbove(submissions);