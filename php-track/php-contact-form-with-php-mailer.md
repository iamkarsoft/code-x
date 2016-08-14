### Creating a contact form using php mailer

##### the form

```
<h3 class="page-header">Contact Form</h3>
                            <form action="<?php $_SERVER['PHP_SELF'] ?>" method="post" >

                            <section class="form-group">
                                <p>


                            <?php if($_POST){   
                                include 'functions/contact-sc.php';
                                if(!empty($errors)) :?>
                                    <ul><li class="bg-danger text-danger errors"><?php echo implode('</li><li class="bg-danger text-danger errors"> ', $errors); ?><li>

                                </ul>
                            <?php endif;    
                                } ?>
                        </p>
                            </section>
                                
                                <section class="form-group">
                                        <label for="">Name</label>
                                <input type="text" name="name" placeholder="Kojo Agyemang"  <?php echo isset($fields['name'])? 'value="'.e($fields['name']).'"':'' ?> class="form-control"></section>

                                <section class="form-group">
                                            <label for="">Email</label>
                                <input type="email" name="email" placeholder="kagyemang@example.com" <?php echo isset($fields['email']) ? 'value="'.e($fields['email']).'"':'' ?> class="form-control"></section>

                            <!--    <section class="form-group">
                                    <label for="">subject</label>
                                <input type="text" name="subject" placeholder="Hello!!" class="form-control"></section> -->
                                <section class="form-group">
                                    <label for="">Message</label>
                                <textarea name="message" id="" cols="30" rows="10" class="form-control"><?php echo isset($fields['message']) ? e($fields['message']) : '' ?></textarea></section>
                                    <section class="col-md-12 form-group"></section>
        
            <section class="col-md-12 form-group"> <button class="btn btn-success form-control">Post</button></section>
    



                            </form>
                        </section> <!--/service2 -->

```


### the php script
```
<?php 


require_once 'libs/phpmailer/PHPMailerAUtoload.php';

$errors=[];

//checking if fields set then run mail function

if(isset($_POST['name'], $_POST['email'], $_POST['message'])){

        $fields=[
            'name'=>$_POST['name'],
            'email'=>$_POST['email'],
            'message'=>$_POST['message']

        ];

        foreach($fields as $field => $data){
            if(empty($data)){
                $errors[]= ucfirst($field).' field is required';
            }
        }

            if(empty($errors)){

                $m = new PHPMailer;
                $m ->isSMTP();
                $m->SMTPAuth=true;

                // debugging
                // $m->SMTODebug=1
                // endof debug
                $m->Host="smtp.gmail.com";
                $m->Username="foo@gmail.com";
                $m->Password="foo";
                $m->SMTPSecure='ssl';
                $m->Port=465;
                $m->isHtml();

                $m->Subject = 'Contact Form submitted';
                $m->Body = 'From:'.$fields['name'].'('.$fields["email"].')<p>'.$fields["message"].'</p>';
                $m->FromName="Contact Form Efie";
                $m->AddAddress('karsoft92@gmail.com','Kofi Amoussou');

                if($m->send()){
                        echo '<p class="errors bg-success text-success">Email Received</p>';
                }else{
                    $errors[]="Sorry, We couldn't send email. Please try again later";
                }

            }
        
}else{
    $errors[]="Something went wrong";

}

$_SESSIONS['errors'] = $errors;
$_SESSIONS['fields']=$fields;
 ?>
```

### To hold the data in form in case a field is missing we place the following on top of the contact page

```
require_once 'helpers/security.php';
$errors=isset($_SESSION['errors']) ? $_SESSION['errors'] : [];
$fields=isset($_SESSION['fields']) ? $_SESSION['fields'] : [];
```

Also for security reasons we have to escape the contact form scripts 
```
function e($string){

    return htmlentities($string, ENT_QUOTES, 'UTF-8', false);
}

```


To make sure the data and errors are not kept when the user moves away from the contact page, we unset the error and fields in the footer of the contact page

```
unset($_SESSION['errors']);
unset($_SESSION['fields']);
```

