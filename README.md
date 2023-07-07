# maintenancePage

## Intro 

- redirecting the site to maintenance page via config settings of web server

## Installation
- repo
  - `cd /var/www/`
  - `git clone https://github.com/tommygood/maintenancePage.git`

## Usage

- insert the content of `webServer.conf` into the site config of web server(ex. apache2)
  - ex. in `/etc/apache2/sites-avaliable/xxx.conf`

      ```conf
      <VirtualHost *:443>
        # original content
        ServerName www.example.com
        DocumentRoot /var/www/{your_site}
        SSLEngine on

        # maintence
        <LocationMatch ".*">
            Alias "/var/www/maintenancePage/index.html"
        </LocationMatch>
        <LocationMatch "/fixed.jpg">
            Alias "/var/www/maintenancePage/fixed.jpg"
        </LocationMatch>
      </VirtualHost>
      ```
