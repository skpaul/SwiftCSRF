# SwiftCSRF v 0.0.1
Cross-site Request Forgery prevention utility library

## What is it
SwiftCSRF is a tentative, quick & handy php library used to prevent Cross-site Request Forgery (CSRF).

## WARNING
This tool SHOULD NOT BE THE ONLY MECHANISM to prevent CSRF attacks. Use more appropiate functions or other means depending on the context of the output.


## Installation
Import the file in your project-
```sh
require_once("SwiftCSRF.php");
```
## How to use
Create new instance-
```sh
$csrf = new SwiftCSRF();
```
Create a hidden input within your form -
```sh
<form action="test_form_.php" method="post">
    <?php echo $csrf->CreateCsrfInput("hi"); ?>
    <input type="submit">
</form>
```

In the form post page, check the above input -
```sh
 $is_safe = $csrf->IsSafe("hi");
    if($is_safe){
        echo "No CSRF found.";
    }
    else{
        echo "Something suspicous.";
    }
```