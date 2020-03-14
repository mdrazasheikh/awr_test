<h2>Installation</h2>
This is a manual installation version. Please refer to the docker repo for docker instructions.

[Go to the docker repo](https://github.com/mdrazasheikh/awr_test_docker).

PS: This version was created because of slowness issues with the docker version
 
### Requirements:
* PHP - 7.1.x, 7.2.x, 7.3.x
* Nginx
* Mysql - 5.7.x
* composer

[Detailed Magento System Requirements here](https://devdocs.magento.com/guides/v2.3/install-gde/system-requirements.html)

### Instructions
* Checkout the code to/your/local/path
* Create a database by name <code>magento</code> in mysql
* Import the database script in the root by the name <code>magento_sql_script.sql</code>
* Run <code>composer install</code>
* Copy the <code>nginx.conf</code> to the ngnix configs and restart the webserver
* Update the db credentials in <code>app/etc/env.php</code> for any changes
* Default db config : <code>user:root; password:''; database:magento; host:localhost; port:3306</code>
* <code>base_url</code> is : <code>http://mage.local.mine</code>. Change this in the database if necessary to support your local environment. <code>core-config-data -> base_url & secure_base_url</code>
* Flush the magento cache on db changes either from admin control panel or CLI. <code>($ bin/magento cache:clean)</code>

PS: It is assumed that the following is run from within the root folder of the app

### Assumptions
* Vehicles are loaded via cron job once a day at 1AM
* Vehicles can be pulled manually via front API : <code>{domain}:{port}/autotrustimporter/index</code>
* Only non reserved vehicle are shown in the listing
* Not all the options available with the APIs are shown to Customer
* Products are taken into account as simple products
 
## License

Each Magento source file included in this distribution is licensed under OSL 3.0 or the Magento Enterprise Edition (MEE) license.

[Open Software License (OSL 3.0)](https://opensource.org/licenses/osl-3.0.php).
Please see [LICENSE.txt](https://github.com/magento/magento2/blob/2.3-develop/LICENSE.txt) for the full text of the OSL 3.0 license or contact license@magentocommerce.com for a copy.

Subject to Licensee's payment of fees and compliance with the terms and conditions of the MEE License, the MEE License supersedes the OSL 3.0 license for each source file.
Please see LICENSE_EE.txt for the full text of the MEE License or visit https://magento.com/legal/terms/enterprise.
