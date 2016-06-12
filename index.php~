<!DOCTYPE html>
<html>
<meta charset="utf-8" />
<head>
  <title>Veebilehe külastajate loendur</title>
  <link href="style.css" rel="stylesheet">

</head>
<body>
<div id="main">

  <h2>Tere, siin on minu veebilehe külastajate loendur. </h2>
 
 <?php  
 
session_start();


$aadress = $_SERVER['REMOTE_ADDR'];
$servername = "localhost";
$username = "test";
$password = "t3st3r123";

$conn = new mysqli($servername, $username, $password, "test");
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
} 



$sql = "INSERT INTO ppopova_people(visits_ip) VALUES ('$aadress')";


if ($conn->query($sql) === TRUE) {
	
    echo " Uus külastus on registreeritud. <br>";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}



$stat = "SELECT visits_ip, count(*) FROM ppopova_people group by visits_ip";
$result1 = $conn->query($stat);

if($result1) {
	while($row = mysqli_fetch_assoc($result1)) {
		//print_r($row);
		echo "IP: " . $row["visits_ip"] . " - Sellest IP aadressilt on mind külastanud " . $row["count(*)"] .  " korda. <br>";
	}
} else {
	echo "No visits";
	
}


$conn->close();

  
 

$_SESSION = array();
			if (isset($_COOKIE[session_name()])) {
 	 			setcookie(session_name(), '', time()-42000, '/');
			}
			session_destroy();?>




 </div>


 <!-- hitwebcounter Code START -->
<a href="http://www.hitwebcounter.com" target="_blank">
<img src="http://hitwebcounter.com/counter/counter.php?page=6308503&style=0001&nbdigits=5&type=page&initCount=0" title="free hits" Alt="free hits"   border="0" >
</a>                                        <br/>
                                        <!-- hitwebcounter.com --><a href="http://www.hitwebcounter.com" title="Track My Website" 
                                        target="_blank"
</body>
</html>
