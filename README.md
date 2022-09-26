# Js-OOP-1-counter

Js OOP 


function getElement(selection) {
  const element = document.querySelector(selection);
  if (element) {
    return element;
  }
  throw new Error(
    `Please check "${selection}" selector, no such element exists`
  );
}
//this מאפשר להוסיף את הערך של המשתנה
function Counter(element, value) {
  this.counter = element;
  this.value = value;
  this.resetBtn = element.querySelector('.reset');
  this.increaseBtn = element.querySelector('.increase');
  this.decreaseBtn = element.querySelector('.decrease');
  this.valueDOM = element.querySelector('.value');
  this.valueDOM.textContent = this.value;
  // bind this to all function -DOM הכוונת כל פונקציה לשינוי ב
  this.increase = this.increase.bind(this);
  this.decrease = this.decrease.bind(this);
  this.reset = this.reset.bind(this);
// הפעלת הכפתורים 
  this.increaseBtn.addEventListener('click', this.increase);
  this.decreaseBtn.addEventListener('click', this.decrease);
  this.resetBtn.addEventListener('click', this.reset);
}

// הפעלת הפונקציה שבכל כפתור
Counter.prototype.increase = function () {
  this.value++;
  this.valueDOM.textContent = this.value;
};
Counter.prototype.decrease = function () {
  this.value--;
  this.valueDOM.textContent = this.value;
};
Counter.prototype.reset = function () {
  this.value = 0;
  this.valueDOM.textContent = this.value;
};
//  פיצול הגדרות מחשבון שני מחשבונים שונים 
const firstCounter = new Counter(getElement('.first-counter'), 100); // מחשבון ראשון
const secondCounter = new Counter(getElement('.second-counter'), 200); // מחשבון שני



Js class oop

אובייקט הוא  תוכנית שבה רשום הנתונים שאותם נמלא במידע. אפשר עם אותה תוכנית אחת ליצור כמה אובייקטים שהמידע שנזין בהם יהיה שונה אבל האובייקט התכונית אותו הדבר

function getElement(selection) {
  const element = document.querySelector(selection);
  if (element) {
    return element;
  }
  throw new Error(
    `Please check "${selection}" selector, no such element exists`
  );
}
// הגדרות מחשבון
class Counter {
  constructor(element, value) {
    this.counter = element;
    this.value = value;
    this.resetBtn = element.querySelector('.reset');
    this.increaseBtn = element.querySelector('.increase');
    this.decreaseBtn = element.querySelector('.decrease');
    this.valueDOM = element.querySelector('.value'); //לערך  DOM השואת ערך המספר ב
    this.valueDOM.textContent = this.value; //לערך התוצאה שיוצאת DOM השוואת הערך ב
    // bind this to all function
    this.increase = this.increase.bind(this);
    this.decrease = this.decrease.bind(this);
    this.reset = this.reset.bind(this);

// הפעלת הכפתורים
    this.increaseBtn.addEventListener('click', this.increase);
    this.decreaseBtn.addEventListener('click', this.decrease);
    this.resetBtn.addEventListener('click', this.reset);
  }
// הפעלת הפונקציה שבכל כפתור
  increase() {
    this.value++;
    this.valueDOM.textContent = this.value;
  }
  decrease() {
    this.value--;
    this.valueDOM.textContent = this.value;
  }
  reset() {
    this.value = 0;
    this.valueDOM.textContent = this.value;
  }
}
//  פיצול הגדרות מחשבון שני מחשבונים שונים 
const firstCounter = new Counter(getElement('.first-counter'), 100); // מחשבון ראשון
const secondCounter = new Counter(getElement('.second-counter'), 200); // מחשבון שני
![image](https://user-images.githubusercontent.com/56929518/192363884-3b1f3a7a-3013-4a02-a5b2-757df28505ed.png)
