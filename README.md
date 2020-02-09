# php-abtest-cookie-split
Small code snippet to make an AB test in PHP easily :


```
<?php
$cookie_name = "ab_cart";
if(!isset($_COOKIE[$cookie_name])) {
	$group = rand(1,2);
} else {
    $group = $_COOKIE[$cookie_name];
}
setcookie($cookie_name, $group, time()+(3600 * 24)); //Update cookie for one day
?>
<?php if($group == 1) { ?>
	<!-- Variant 1 -->
<?php } else { ?>
	<!-- Variant 2 -->
<?php }?>
```
