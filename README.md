![image](https://github.com/DaWanAnOnli/advprog-modul10-timer/assets/124868777/027845b6-f5cc-412a-a2d0-e8a93205b1da)


Explanation:
Kalimat 'hey hey' tetap muncul sebelum 'howdy!' padahal letak 'hey-hey' di source code di bawah 'howdy'. Hal ini disebabkan perintah untuk print 'howdy!' yang berada dalam thread yang asynchronous. Perlu diperhatikan, bahwa terdapat jeda waktu antara membuat thread async hingga thread tersebut dieksekusi. OS memanfaatkan jeda tersebut untuk mengeksekusi bagian program berikutnya, yang salah satunya adalah 'hey hey'. Oleh karena itu, 'hey-hey' diprint sebelum 'howdy!', karena perintah 'howdy' masih belum siap untuk diprint (masih dalam bentuk future), namun program tetap berjalan terus.
