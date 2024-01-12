# 2024_Product_Inventory_with_Export_to_Excel_XSS

+ **Exploit Title:** 2024_Product_Inventory_with_Export_to_Excel_Cross_Site_Scripting
+ **Date:** 2024-12-01
+ **Exploit Author:** Burak Sevben
+ **Vendor Homepage:** https://www.sourcecodester.com/php/17077/product-inventory-export-excel-using-php-source-code.html
+ **Software Link:** https://www.sourcecodester.com/download-code?nid=17077&title=Product+Inventory+with+Export+to+Excel+Using+PHP+and+MySQL+with+Source+Code
+ **Version:** 1.0
+ **Tested on:** Windows 11 Home + PHP 8.2.12, Apache 2.4.58
+ **CVE:** Reported, waiting for CVE number

## Description:
The `Prodocut Name` and `Product Code` sections in the 'Add Product' section of Product Inventory with Export to Excel are vulnerable to XSS attacks.
An attacker could exploit this issue to run arbitrary scripting code in an unsuspecting user's browser in the context of the affected site. This could allow an attacker to steal cookie-based authentication credentials and launch other attacks.


## Proof of Concept 1:
+ Go to `http://localhost/product-inventory-with-export-to-excel/`
+ Click on the "Add Product" button.
+ In the "Product Name" section, type the following payload : `<video/src=x onerror=alert(document.domain)>`
+ You can fill in the other sections in a random way. Then click on the "Save Changes" button.
+ XSS will be triggered and a pop-up will appear.


![Ekran görüntüsü 2024-01-13 003231](https://github.com/BurakSevben/2024_Product_Inventory_with_Export_to_Excel_XSS/assets/117217689/de422e4c-9cac-490a-a980-05bc730e621b)

![Ekran görüntüsü 2024-01-13 003301](https://github.com/BurakSevben/2024_Product_Inventory_with_Export_to_Excel_XSS/assets/117217689/8a5faee8-0223-42b5-9571-d15d947130b2)

![Ekran görüntüsü 2024-01-13 003314](https://github.com/BurakSevben/2024_Product_Inventory_with_Export_to_Excel_XSS/assets/117217689/08b26d71-ba92-4586-a00e-abaf16fd007a)

## Proof of Concept 2:
+ Go to `http://localhost/product-inventory-with-export-to-excel/`
+ Click on the "Add Product" button.
+ In the "Product Code" section, type the following payload : `<video/src=x onerror=alert(document.domain)>`
+ You can fill in the other sections in a random way. Then click on the "Save Changes" button.
+ XSS will be triggered and a pop-up will appear.


![Ekran görüntüsü 2024-01-13 003350](https://github.com/BurakSevben/2024_Product_Inventory_with_Export_to_Excel_XSS/assets/117217689/21f0b599-79d2-4398-8d23-fd21e0ea5a11)

![Ekran görüntüsü 2024-01-13 003405](https://github.com/BurakSevben/2024_Product_Inventory_with_Export_to_Excel_XSS/assets/117217689/97804151-7ba5-456d-8f20-1df62bdeb50d)

