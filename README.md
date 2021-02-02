# edupham_bcrypt_php
Bcrypt in PHP for Codeigniter 2x,3x. It can be used to synchronize passwords in Laravel.

## Installation
* Place ``Bcrypt.php`` in your ``application/libraries`` folder.
* Place ``bcrypt.php`` in your ``application/config`` folder.
* Adjust options in the config file as neccessary.

## Usage
### Config
* Case 1: Autoload it in ``config/autoload.php`` file
```
$autoload['libraries'] = array(
    ...,
    'bcrypt'
);
```
* Case 2: Load the Bcrypt library (if necessary)
```
$this->load->library('bcrypt');
```
### Hashing
To hash a password, simply pass the string to ``hash_password()``.
```
$password = 'P7g2zd';
$hash = $this->bcrypt->hash_password($password);
// $hash = $2y$10$DV4jdLVebUX1ishuSSRJF.BDqWKgcvTrbpve0DkPxr.f0rO8ST8Ea
```
The function will return the hashed password or ``*`` on error.

### Checking
To check a hash password, simply pass the string and stored password to ``check_password()``.
```
$password = 'P7g2zd';    
if ($this->bcrypt->check_password($password, $hash)) {
    // Password does match stored password.
} else {
    // Password does not match stored password.
}
```
The function will return ``TRUE`` or ``FALSE`` dependant on success.

### Checking in Laravel Framework
```
if (Hash::check('plain-text', $hashedPassword)) {
    // The password match...
} else {
    // Password does not match
}
```



Refer to [codeigniter-bcrypt](https://github.com/dwightwatson/codeigniter-bcrypt)
