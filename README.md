# React: Mapping Data Components
Created with [CodeSandbox](https://codesandbox.io/)      
Notes from: React module    
[The Complete 2021 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)  
Instructor: Dr. Angela Yu      

## Description
This app renders a heading "My contacts"        
and 3 cards with information of 3 humans: their name, a picture, their (fake) telephone and their (fake) email

## Notes
Mapping Components is a technique that        
makes easy to map all the individual custom pieces of data to each of the custom Components     
eg: using a form on our website or some input elements.

Map function is a Javascript function that's really useful for handling data such as arrays      
instead of passing values around our code, you're passing functions into functions (even into functions, different levels).     
eg: Card Component

Instead of passing values around our code and repeat for each component:
```
<Card
    name={contacts[0].name}
    img={contacts[0].imgURL}
    tel={contacts[0].phone}
    email={contacts[0].email}
/> 
// Repeat for each Card [1], [2], ....
```

We are going to create a function:  ```createCard```      
Warning: Each child in a list should have a unique ```key``` prop.
```
function createCard(contact) {
  return <Card 
      key={contact.id}
      name = {contact.name}
      img={contact.imgURL}
      tel={contact.phone}
      email={contact.email}
  />
}
```
This function ```createCard``` will be pass in our ```App``` function to create Cards there:
```
function App(props) {
  return (
    <div>
      <h1 className="heading">My Contacts</h1>
      {contacts.map(createCard)}
    </div>
  );
}

```
The map function loops through this array of contacts ( ```contacts.map(*)``` )        
and for every single item that exists in the contacts array , it calls the createCard function ( ```(*createCard)``` )      
and it passes over each of the objects inside the array ( ```contacts[0] [1] [2]... ``` )

The objects in contacts.js in this example must have a JS Object; id: x      
We include this as a prop      ```<Card key={contact.id} .... />```       
The value of ```key``` can be strings , numbers ... but it must be unique across all of the repeated components.       

## What I have learned with this project:    
* How to use the Mapping Function.
* Convert hard coded Components into Functions that can be used inside the Map Function.
* Using unique key props neccessary for the map function.
* How to apply styles to the new created components.
* Import modules (from contacts.js) to create Card Componets using the data there as values in the props.
