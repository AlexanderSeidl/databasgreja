<?php
              define('DB_SERVER','localhost');
              define('DB_USER','root');
              define('DB_PASSWORD','');
              define('DB_NAME','bilar');
              
              $dbh = new PDO('mysql:dbname='.DB_NAME.';host='.DB_SERVER.';charset=utf8',DB_USER, DB_PASSWORD);
              
              
              $sql_insert = "INSERT INTO garage(id, namn, motortyp, drivlina, chassityp) VALUES ('','Saab 9-5 Aero','I4 Turbo','FWD','Kombi')";
              $stmt = $dbh->prepare($sql_insert);
              $stmt->execute();
              
              $sql = "SELECT * FROM garage";
              $stmt = $dbh->prepare($sql);
              $stmt->execute();
              
              $bilar = $stmt->fetchAll();
              
              
              for($n=0;$n<count($bilar);$n++){
                  
              for($i=1;$i<5;$i++){
              echo $bilar[$n][$i];
              echo '<br>';
              }
              echo '<br>';
              }
        ?>    
