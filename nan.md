## Rangkuman Basic Konfigurasi pada perangkat OLT [ZTE-C300]

### Noted aja Gan
Dokumen ini berisi daftar perintah yang umum digunakan untuk mengelola dan memantau Optical Line Terminal (OLT) dan Optical Network Terminal (ONT) dalam sebuah jaringan GPON. Perintah-perintah ini dapat bervariasi tergantung pada vendor peralatan yang agan pakai.

### Perintah OLT
* **Memeriksa Status OLT**
  * `show system-group`: Menampilkan informasi tingkat sistem, termasuk uptime dan versi perangkat lunak.
  * `show card`: Menampilkan informasi tentang komponen perangkat keras OLT.
  * `show processor`: Menampilkan informasi tentang penggunaan prosesor dan memori OLT.
  * `show temperature`: Menampilkan suhu berbagai komponen di dalam OLT.
  * `show card slotno 11`: Menampilkan informasi detail tentang slot tertentu di OLT.

### Perintah ONT
* **Menemukan dan Memeriksa Status ONT**
  * `show gpon onu by sn xxxxxxxxxx`: Menemukan ONT berdasarkan nomor serialnya.
  * `show gpon onu sta gpon-olt_1/2/2`: Menampilkan status operasional ONT tertentu.
  * `show gpon onu detail-info gpon-onu_1/2/2:6`: Memberikan informasi lebih detail termasuk, uptime, log, dan informasi lainnya.
  * `show mac gpon onu gpon-onu_1/2/2:6`: Menampilkan alamat MAC fisik dari ONT.
  * `show pon power attenuation gpon-onu_1/2/2:6`: Menunjukkan seberapa besar sinyal optik melemah saat berjalan dari OLT ke ONT.
  * `show gpon remote-onu equip gpon-onu_1/2/2:6`: Menampilkan versi perangkat lunak yang berjalan pada ONT.
  * `show gpon remote-onu ip-host gpon-onu_1/2/2:6`: Menampilkan alamat IP yang dikonfigurasi pada ONT.
  * `show gpon remote-onu interface eth gpon-onu_1/2/2:6`: Menunjukkan status port Ethernet pada ONT, seperti apakah port aktif, link up, atau ada error.
  * `show run int gpon-onu_1/2/2:6`: Melihat konfigurasi dari ONT yang sebelumnya sudah di konfigurasi.
  * `show onu run con gpon-onu_1/2/2:6`: Melihat konfigurasi dari ONT yang sebelumnya sudah di konfigurasi.
 
* **Menghidupkan ulang ONT**
  * `conf t`: Masuk ke mode konfigurasi terminal.
  * `pon-onu`: Masuk ke mode konfigurasi ONT.
  * `pon-onu-mng gpon-onu_1/2/2:6`: Memilih ONT yang akan dikelola.
  * `reboot`: Merestart ONT.
  * `restore factory`: Mengembalikan ONT ke pengaturan pabrik.

* **Mereset ONT ke pengaturan ulang Pabrik**
  * `conf t`: Masuk ke mode konfigurasi terminal.
  * `pon-onu`: Masuk ke mode konfigurasi ONT.
  * `pon-onu-mng gpon-onu_1/2/2:6`: Memilih ONT yang akan dikelola.
  * `restore factory`: Mengembalikan ONT ke pengaturan pabrik.

* **Mengunci atau Mematikan Port Ethernet pada ONT**
  * `conf t`: Masuk ke mode konfigurasi terminal.
  * `pon-onu`: Masuk ke mode konfigurasi ONT.
  * `pon-onu-mng gpon-onu_1/2/2:6`: Memilih ONT yang akan dikelola.
  * `interface eth eth_0/3 state lock`: Kunci port atau mematikan port (contoh port 3 pada ONT)
 
* **Merelease dan Memperbarui Lease DHCP pada ONT**
  * `conf t`: Masuk ke mode konfigurasi terminal.
  * `pon-onu`: Masuk ke mode konfigurasi ONT.
  * `pon-onu-mng gpon-onu_1/2/2:6`: Memilih ONT yang akan dikelola.
  * `ip-host 1 dhcp-enable false ping-response false traceroute-response false`: Perintah ini digunakan untuk menghentikan proses DHCP pada ONT.
  * `ip-host 1 dhcp-enable true ping-response true traceroute-response true`: Perintah ini digunakan untuk memulai kembali proses DHCP pada ONT.
 
* **Mengecek Tingkat Penerimaan Sinyal Optik pada Uplink OLT**
  * `show int optical-module-info xgei_1/21/1`: Memeriksa dan menampilkan tingkat penerimaan sinyal optik pada port uplink OLT.
 
* **Mereset Slot OLT**
  * `reset-card slotno 12`: Mereset slot tertentu pada OLT.
 
* **Melihat Ringkasan VLAN**
  * `show vlan sum`: Melihat ringkasan semua VLAN yang dikonfigurasi pada OLT.
  * `show vlan 1234`: Melihat detail VLAN tertentu, seperti range VLAN ID, port-port yang terikat pada VLAN tersebut, dan konfigurasi lainnya.
