<?php
function send_location_email(\$location) {
    \$to = 'admin@teacars.com'; // Имейл адресът, на който да се изпрати
    \$subject = 'Споделено местоположение';
    \$message = 'Местоположение: ' . \$location;
    \$headers = 'From: admin@teacars.com'; // Вашият имейл адрес

    wp_mail(\$to, \$subject, \$message, \$headers);
}
add_action('simple_location_save_post', 'send_location_email', 10, 1);
