# SMB-Log
-AMAÇ-
Sisteminizde ağınızda Balküpü (olta, tuzak) oluşturmak.
-YÖNTEM-
Bir server 2008 R2 SP1 sunucusu üzerinde ms17-10 açığı bırakıp bu açıktan içeri girildiğinde oluşan SMB logunu takip ederek kötü niyetli kişinin bu açıktan içeri girdiğini fark edip yakalamak.  
-HAZIRLIK-
Server 2008R2 SP1, 
Güvenlik duvarı kapalı olmalı,
Powershell 5 kurulu olmalı,
Wireshark kurulu ve tshark (wiresharkı konsoldan kullanmak için) ayarı yapılmalı, (Environment Variables üzerinden System Variables altında Path kısmına wireshark yüklü olduğu yol eklenir.)

