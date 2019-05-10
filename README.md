##Wrapper Class around ibm_db (IBM-DB2)
*	In IBM-DB2 after every read, the data needs to be fetched and after evey write, the data needs to be committed. But this class eliminates these requirements and make it simple to read and write to the database.

##Files:
*	ibmdb2/__init__.py

##Usage Examples:
*	import ibmdb2
*	db = ibmdb2.db(conn_str)  ##-connect to the database using the connection string for example conn_str = "DATABASE=BLUDB;HOSTNAME=dashdb-txn-sbox-yp-dal09-04.services.dal.bluemix.net;PORT=50000;PROTOCOL=TCPIP;UID=username;PWD=password;"
*	Note: In the SQL statements all columns should be enclosed with " double quotes and text be enclosed with ' single quotes.
*	db.read('select "column1","column2" from mytable where "column1" like \'myword\' ')  ##-returns column1 & 2 from table where column = myword
*	db.read('select "column" from table", flat=False)  ##-returns the raw read data 
*	db.read(f'select "item" from table where "item" = \'{Variable}\'')  ##-read with string substitution
*	db.read1('sql statement')  ##-returns the first read data similar to fetchone
*	db.write('sql statement')  ##-writes the data and commits to the database
	
##For other connection commands use the connection class
*	db.conn....
