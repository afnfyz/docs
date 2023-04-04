

    #!/bin/bash

    yum install -y httpd
    systemctl start httpd

    chmod -R 205 /var/www/html

    cat << EOF > /var/www/html/projects.html
    <!DOCTYPE html>
    <html>
    <body>

    <h1>YOUR-NAME's re/Start Project Work</h1>

    <p>EC2 Instance Challenge Lab</p>

    </body>
    </html>

    EOF