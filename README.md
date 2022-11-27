# FastQL
FastQL is wrapper class that allow the developer to create quick and easier way to build and deploy with PHP

<h1>Usage</h1>

<h3> Installation </h3>

<pre>
require_once "Database Connection/Connect.php";
require_once "Database Connection/CRUD.php";
</pre>

<h3> Connecting to Database </h3> 

<pre>
Connect::setHostname("IP Address");
Connect::setDbPort("port");
Connect::setDbUsername("username");
Connect::setDbPassword("password#");
Connect::setDbName("DatabaseName");
</pre>

<h3>Check Connectinon is possible </h3> 

<pre>
$test = new Connect();
$pdo = $test->isConnect();
</pre>

<h4>isConnect() method return true if the connection is possible</h4>

<h3>CRUD Method Usage</h3>

<pre>
 $CRUD =  new CRUD($pdo)
</pre>

<h3>Select Function</h3>

<h5> The First parameter take the TableName and second parameter take the array of columns. <br>

<pre>
$column_array = ["Column1", "Column2"]; 
CRUD::Select("TableName", $column_array); 
</pre> 

<h5> If we want to select all of the table leave it blank or input null to second parameter

<pre>
CRUD::Select("TableName" , null) // select all of the columns in Table
</pre>

<h5> The Third paramter take the condition and based on the condition table will output

<pre>
$column_array = ["Column1", "Column2"]; 

$condtion = ["ID" => 12] or
$condtion = ["ID" => 12, "Name" => "Mg Mg" ]  

CRUD::Select("TableName", $colun_array, $condition) 
</pre>

<h5> The fourth parameter take the integer, you can limit the number of ouput, if we don't want use limit just leave blank or null

<pre>

$column_array = ["Column1", "Column2"]; 

$condtion = ["ID" => 12] or
$condtion = ["ID" => 12, "Name" => "Mg Mg" ]  

CRUD::Select("TableName", $colun_array, $condition,null)
CRUD::Select("TableName", $colun_array, $condition,1) // Only one result 

</pre>

<h5> The fifth parameter take the array when we need to sort the column . 
If we want to sort with ascending order -> just add true otherwise input false</h5>

<pre>

$condtion = ["ID" => 12] or
$condtion = ["ID" => 12, "Name" => "Mg Mg" ]  

$order_column  = ["Id","name"]
CRUD::Select("TableName", $colun_array, $condition,null,$order_column, true); // ascending order
CRUD::Select("TableName", $colun_array, $condition,null,$order_column, false); // descending order

</pre> 

