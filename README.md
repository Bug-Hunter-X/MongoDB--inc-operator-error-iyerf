# MongoDB $inc operator error

This repository contains a simple example of an incorrect use of the `$inc` operator in a MongoDB update operation. The `$inc` operator is used to increment or decrement a numeric field in a document. However, in this example, a string is used instead of a number, which results in an error.

## Bug

The bug is in the following line of code:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: '1' } });
```
The value for `field` should be a number, not a string. This results in the following error:
```
MongoError: The $inc operator requires a number. 
```
## Solution

The solution is to change the value of `field` to a number.
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: 1 } });
```