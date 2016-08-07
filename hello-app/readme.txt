<<< PORDUTO >>>
id PK
nome
valor

<<< PRODUTO_COMPRA
id_produto PK
id_compra PK
quantidade

<<< COMPRA >>>
id PK
data
valor


Creating
You can execute an insert query against a database, like so:

var employee = { name: 'Winnie', location: 'Australia' };
con.query('INSERT INTO employees SET ?', employee, function(err,res){
  if(err) throw err;

  console.log('Last insert ID:', res.insertId);
});


Updating
Similarly, when executing an update query, the number of rows affected can be retrieved using result.affectedRows:

con.query(
  'UPDATE employees SET location = ? Where ID = ?',
  ["South Africa", 5],
  function (err, result) {
    if (err) throw err;

    console.log('Changed ' + result.changedRows + ' rows');
  }
);


Destroying
Same thing goes for a delete query:

con.query(
  'DELETE FROM employees WHERE id = ?',
  [5],
  function (err, result) {
    if (err) throw err;

    console.log('Deleted ' + result.affectedRows + ' rows');
  }
);
