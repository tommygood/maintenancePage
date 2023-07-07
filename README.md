# maintenancePage

## Intro 

- redirect site to maintenance page via config settings of web server

## Usage

- insert the content of `webServer.conf` into sites config of web server
  - ex. in `/etc/apache2/sites-avaliable/xxx.conf`

      ```conf
      <VirtualHost *:443>
        # original content
        ServerName www.example.com
        DocumentRoot /var/www/{your_site}
        SSLEngine on

        # maintence
        <LocationMatch ".*">
            Alias "/var/www/fixed/index.html"
        </LocationMatch>
        <LocationMatch "/fixed.jpg">
            Alias "/var/www/fixed/fixed.jpg"
        </LocationMatch>
      </VirtualHost>
      ```
