# PHP-Database_to_Display_Datashow


<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>


<?php 
    $con = mysqli_connect('localhost','root','','student');
    $query = "SELECT *FROM std_info";
    $result = mysqli_query($con,$query);

    $count = mysqli_num_rows($result);
    ?>
    <table class="table">
        <thead class="thead-dark">

        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
            <th>Password</th>
            <th>Action</th>
        </tr>

        </thead>
    <?php
    if($count>0){
        while($row = mysqli_fetch_assoc($result)){

            $id = $row['id'];
            $username = $row['username'];
            $email = $row['email'];
            $password = $row['password'];

    ?>

            <tbody>           
                <tr>
                    <td><?php echo $id;  ?></td>
                    <td><?php echo $username;  ?></td>
                    <td><?php echo $email;  ?></td>
                    <td><?php echo $password;  ?></td>
                    <td><a href="#">Delete</a></td>
                </tr>
             </tbody>
            
         
         
<?php

        }
?>
</table>
<?php


    }

    


?>

    
    
</body>

