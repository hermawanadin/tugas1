# tugas1
<?php
 
$server = "localhost" ;
$username = "root" ;
$password = "" ;
$database = "tugas1";
 
//Koneksi dan memilih database di server
mysql_connect($server,$username,$password) or die ("Koneksi database gagal");
mysql_select_db($database) or die ("Database tidak tersedia");
 
echo '<h3>Data User</h3>
<table>
<tr>
<th>nim</th>
<th>nama</th>
<th>alamat</th>
<th>progdi</th>
</tr>
<tr>';
 
$i=0; //inisialisasi untuk penomoran data
//perintah untuk menampilkan data, id_brg terbesar ke kecil
$tampil = "SELECT * FROM user ORDER BY id_user DESC";
//perintah menampilkan data dikerjakan
$sql = mysql_query($tampil);
 
//tampilkan seluruh data yang ada pada tabel user
while($data = mysql_fetch_array($sql))
 {
 $i++;
 
echo "
 <td>".$i."</td>
 <td>".$data[nim]."</td>
 <td>".$data[nama]."</td>
 <td>".$data[alamat]."</td>
 <td>".$data[progdi]."</td>
 </tr>";
 }
echo '</table>';
 
?>
