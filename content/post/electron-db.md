---
title: "Electron Db"
date: 2018-04-29T11:19:59+08:00
draft: false
categories: ["projects"]
tags: ["projects"]
image: "images/electron-db.png"
---
# electron-db
---

> Database-like solution in electron apps

**electron-db** is a module to have a database-like functions to simulate table manipulation on data. The data is saved as a json flat file.

The json file is saved on the application folder.

**Important:** The script that uses this library should be run with electron command first in order to create the direction on the user data folder. The name that will be used for the app directory will be what was indicated in the package.json as <em>productName</em>. If this is not set, the <em>name</em> property will be used.

### **Installation**


```javascript
npm install electron-db
```

### **Creating Table**
Creates a json file [table-name].js inside the application userData folder.

```javascript

const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

db.createTable('customers', (succ, msg) => {
  // succ - boolean, tells if the call is successful
  console.log("Success: " + succ);
  console.log("Message: " + msg);
})

/*
	Output:
    	Success: true
        Message: Success!

	Result file (customers.json):
    {
    	"customers": []
    }
*/
```
### **Inserting Object/Data to Table**
Insert an object into the list of row/data of the table.

```javascript
const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

let obj = new Object();

obj.name = "Alexius Academia";
obj.address = "Paco, Botolan, Zambales";

db.insertTableContent('customers', obj, (succ, msg) => {
  // succ - boolean, tells if the call is successful
  console.log("Success: " + succ);
  console.log("Message: " + msg);
})

/*
	Output:
    	Success: true
        Message: Object written successfully!

    Result file (customers.json):
    {
      "customers": [
        {
          "name": "Alexius Academia",
          "address": "Paco, Botolan, Zambales"
        }
      ]
    }

*/
```
### **Get all rows**
Get all the rows for a given table by using the callback function.
```javascript

const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

db.getAll('customers', (succ, data)) {
  // succ - boolean, tells if the call is successful
  // data - array of objects that represents the rows.
}
```
### **Get Row(s) from the table**
Get row or rows that matched the given condition(s) in WHERE argument

```javascript
const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

db.getRows('customers', {
  address: "Paco, Botolan, Zambales",
  name: 'Alexius Academia'
}, (succ, result) => {
  // succ - boolean, tells if the call is successful
  console.log("Success: " + succ);
  console.log(result);
})

/*
	Output:
    	Success: true
        [ { name: 'Alexius Academia',
    address: 'Paco, Botolan, Zambales',
    id: 1508419374272 } ]
*/
```

### **Update Row**
Updates a specific row or rows from a table/json file using a WHERE clause.

```javascript
const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

let where = {
  "name": "Alexius Academia"
};

let set = {
  "address": "Paco, Botolan, Zambales"
}

db.updateRow('customers', where, set, (succ, msg) => {
  // succ - boolean, tells if the call is successful
  console.log("Success: " + succ);
  console.log("Message: " + msg);
});
```

### **Search Records**
Search a specific record with a given key/field of the table. This method can search part of a string from a value.

In this example, I have a table named 'customers', each row has a 'name' property. We are now trying to search for a name in the rows that has the substring 'oh' in it.

```javascript
const db = require('electron-db');
const electron = require('electron');

const app = electron.app || electron.remote.app;

let term = "oh";

db.search('customers', 'name', term, (succ, data) => {
  if (succ) {
    console.log(data);
  }
});

// Output
/*
[ { name: 'John John Academia',
    address: 'Paco, Botolan, Zambales',
    id: 1508419430491 } ]
*/
```

### **Delete Records**
Delete a scecific record with a given key-value pair from the table.

```javascript

const db = require('electron-db');
const electron = require('electron');

db.deleteRow('customers', {'id': 1508419374272}, (succ, msg) => {
  console.log(msg);
});

```
