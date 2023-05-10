level: 2
2st time

better one

```javascript
var countStudents = function (students, sandwiches) {
  while (students.length > 0 && students.indexOf(sandwiches[0]) != -1) {
    if (students[0] == sandwiches[0]) {
      students.shift();
      sandwiches.shift();
    } else students.push(students.shift());
  }
  return students.length;
};
```

Mine

```javascript
/**
 * @param {number[]} students
 * @param {number[]} sandwiches
 * @return {number}
 */
var countStudents = function (students, sandwiches) {
  // students in a queue. if he does not like the top sandwitche, he has to go back to the last in the queue
  // sandwitches in a stack
  // only student in students queue moves and is removed from the queue

  // iterate students array using while
  // compare the first value with the first value in sandwitches always
  // if student number is same as first sandwitches, remove student and add 1 to sandwitch pointer
  // else: splice(0,1) and push first value to end
  // if 1st sandwitch is diff from all students value, return the number of the left students
  let sandP = 0;
  let count = 0;
  while (sandP < sandwiches.length) {
    const student = students[0];
    students.splice(0, 1);
    if (student === sandwiches[sandP]) {
      sandP++;
      count = 0;
    } else {
      // add to the end
      students.push(student);
      count++;
    }

    if (count > students.length) return students.length;
    console.log("students :", students);
  }
  return 0;
};
```
