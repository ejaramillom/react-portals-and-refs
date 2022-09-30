# react-portals-and-refs
Diving deep in portals and refs with udemy maximilian project

# jsx limitations

when we  have a json that includes two tags outside a div separation

return (
  <h2>hi there! </h2>
  <p>this does not work </p>
);

this does not work in JSX, you cant return more than one "root" JSX element.

This is also not valid javascript code

return (
  React.createElement('h2', {}, 'Hi there!')
  React.createElement('p', {}, 'This does not work ')
);

because you cannot return two things from a function by separate

a workaround is using a div to wrap inside the things you want to return
or then you can use an array [] but you have to add "key" attribute to each object
inependently they are a function or an attribute or a JSX object

it does not have to be a div, but this creates the "div soup"

# new limitation: the <div> soup

many div are created so many unnecessary divs add no semantic meaning or structure

<div>
  <div>
    <div>
      <div>

many elements and its a bad idea if you have a 1000 elements 

# React fragments

this problem is solved using fragments: We wrap the elements we created on the component with a built in class named React.fragment

return (
  <React.Fragment>
    <h2>Hi there! </h2>
    <h2>Now this works! </h2>
  </React.Fragment>
);