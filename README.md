<h1>
  Reflection
</h1>

<h2>
  Part 1
</h2>

![image](https://github.com/DaWanAnOnli/advprog-modul10-timer/assets/124868777/027845b6-f5cc-412a-a2d0-e8a93205b1da)


Explanation:
Kalimat 'hey hey' tetap muncul sebelum 'howdy!'. Padahal letak 'hey-hey' di source code di bawah 'howdy'. Hal ini disebabkan perintah untuk print 'howdy!' yang berada dalam thread yang asynchronous. Perlu diperhatikan, bahwa terdapat jeda waktu antara membuat thread async hingga thread tersebut dieksekusi. OS memanfaatkan jeda tersebut untuk mengeksekusi bagian program berikutnya, yang salah satunya adalah 'hey hey'. Oleh karena itu, 'hey-hey' diprint sebelum 'howdy!', karena perintah 'howdy' masih belum siap untuk diprint (masih dalam bentuk future) namun program tetap berjalan terus.


<h2>
  Part 2
</h2>

![image](https://github.com/DaWanAnOnli/advprog-modul10-timer/assets/124868777/d9a83d41-72f0-4ca3-8d20-c5791c2504b5)

Penjelasan:
Execution 1: tanpa drop
Execution 2: dengan drop
Execution 3: tanpa drop lagi

Jika spawner.drop() di-comment, program tidak akan berhenti saat di-run. Hal ini dikarenakan program akan terus menunggu pesan dari spawner (karena spawner masih aktif). Jika spawner di-drop, program langsung berhenti. Hal ini dikarenakan ia tahu tidak akan ada lagi pesan yang masuk dari thread (karena sudah di-drop). Jika spawner tidak di-drop, masih mungkin ada pesan lain yang diterima oleh program, karena spawner bersifat async. Hal ini menyebabkan program tidak akan berhenti.
