# Client_Tip_Calculator
 This is a Tip Calculator system which used to calculate the bill of consumed service or product

The first appearance of the system before starting working

![image](https://user-images.githubusercontent.com/103323625/185868051-6a551acf-0829-4a25-b215-9062906b8671.png)

Now the put the bill of the service or product as  you see it automatically appear down below for the total amount

![image](https://user-images.githubusercontent.com/103323625/185868223-0f14819b-c6b8-46f4-9bee-491046ef5578.png)


And we are going to set the percentage of the tip because as we know this percentage depends  on the client for how much he/she like your service/product


![image](https://user-images.githubusercontent.com/103323625/185869173-095dbc26-8cf5-4e51-a4ce-e9ad3dc19e8c.png)

After setting the percentage we give you a possibility of specifying the number of persons are going to pay that money 
in order to help you to know how much money every person is going to pay 

![image](https://user-images.githubusercontent.com/103323625/185870241-2df5deca-6f5a-4b9b-b2c8-01324e45d7bb.png)

### This is how our system workkkk!!!!!!!!!!!



``` javascript
// bill input, tip input, number of people div, and per person total div
const billInput = document.getElementById('billTotalInput')
const tipInput = document.getElementById('tipInput')
const numberOfPeopleDiv = document.getElementById('numberOfPeople')
const perPersonTotalDiv = document.getElementById('perPersonTotal')


// Get number of people from number of people div

let numberOfPeople = Number(numberOfPeopleDiv.innerText)


// ** Calculate the total bill per person **
const calculateBill = () => {
    // get bill from user input & convert it into a number
    const bill = Number(billInput.value)  
  
    // get the tip from user & convert it into a percentage (divide by 100)
    const tipPercent = Number(tipInput.value) / 100
  
    // get the total tip amount
    const tipAmount = bill * tipPercent
  
    // calculate the total (tip amount + bill)
    const total = tipAmount + bill
  
    // calculate the per person total (total divided by number of people)
    const perPersonTotal = total / numberOfPeople
  
    // update the perPersonTotal on DOM & show it to user
    perPersonTotalDiv.innerText = `$${perPersonTotal.toFixed(2)}`
  }
  
  // ** Splits the bill between more people **
  const increasePeople = () => {
    // increment the amount of people
    numberOfPeople += 1
  
    // update the DOM with the new number of people
    numberOfPeopleDiv.innerText = numberOfPeople
  
    // calculate the bill based on the new number of people
    calculateBill()
  }
  
  // ** Splits the bill between fewer people **
  const decreasePeople = () => {
    // guard clause
    // if amount is 1 or less simply return
    // (a.k.a you can't decrease the number of people to 0 or negative!)
  
    if (numberOfPeople <= 1) {
        return
      }
    // decrement the amount of people
    numberOfPeople -= 1
  
    // update the DOM with the new number of people
    numberOfPeopleDiv.innerText = numberOfPeople
  
    // calculate the bill based on the new number of people
    calculateBill()
  }



```
