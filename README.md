# SteeleyeAssignment
List Compontent :
  Lists are used to display data in an ordered format ,basically lists are one type of array. The map() function is used for traversing the lists.
 
Problems in Code:

1) useState()->It returns a pair of values: the current state and a function that updates it. but here we are doing wrong because  in first we write function and then we write current state that is wrong .
in wrong code it written as : const [setSelectedIndex, selectedIndex] = useState();
right one is : const [selectedIndex, setSelectedIndex] = useState();

2) In props , we set the isselected value to be boolean, but we are passing here a string or a number , so make sure to convert it into boolean
wrong one:  onClick={() => onClickHandler(index)}
right one:  onClick={() => onClickHandler(Boolean(index))

3) While mapping over the array of items, we should have given the key to each item to identify it uniquely.

4) in place of array we have to use arrayOf and instead of shapOf we have to use shape . it is the predefined syntax.
wrong one: 
WrappedListComponent.propTypes = {
  items: PropTypes.array(PropTypes.shapeOf({
  text: PropTypes.string.isRequired,
  })),
    };
Right One:
WrappedListComponent.propTypes = {
  items: PropTypes.arrayOf(
    PropTypes.shape({
      text: PropTypes.string.isRequired,
    })
  ),
};

5) the default items array was null, and it is not possible to map over null, so we need to initialize it with some value.
wrong way:
WrappedListComponent.defaultProps = {
   items: null,
   };
Right Way:
WrappedListComponent.defaultProps = {
  items: [
    { text: "Nitesh", index: false },
    { text: "Kumar", index: false },
    { text: "Jain", index: false },
  ],
};

          
