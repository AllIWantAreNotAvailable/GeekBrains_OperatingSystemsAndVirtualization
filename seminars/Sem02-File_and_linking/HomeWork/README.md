```Bash
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.15.0-75-generic x86_64)

  

 * Documentation:  https://help.ubuntu.com

 * Management:     https://landscape.canonical.com

 * Support:        https://ubuntu.com/advantage

  

  System information as of Sat Jun 24 12:42:05 MSK 2023

  

  System load:           0.0

  Usage of /:            38.4% of 4.67GB

  Memory usage:          21%

  Swap usage:            0%

  Processes:             92

  Users logged in:       0

  IPv4 address for ens3: 192.168.64.5

  IPv6 address for ens3: fd1c:5fe9:1ec1:257f:5054:ff:feca:e22a

  

  

Expanded Security Maintenance for Applications is not enabled.

  

0 updates can be applied immediately.

  

Enable ESM Apps to receive additional future security updates.

See https://ubuntu.com/esm or run: sudo pro status

  

  

Last login: Fri Jun 23 22:16:55 2023 from 192.168.64.1

root@ubunto: mkdir students mentors                                            

root@ubunto: ls                                                                

**mentors**  **snap**  **students**

root@ubunto: touch mentors/mentors_list.txt students/students_list.txt         
root@ubunto: cd mentors                                                          
root@ubunto: ls                                                                  

mentors_list.txt

root@ubunto: cd ../students                                                      root@ubunto: ls                                                                  

students_list.txt

root@ubunto: vim students_list.txt                                               root@ubunto: less students_list.txt                                              root@ubunto: echo "Виноградова Алиса Александровна; Трофимова Вероника Егоровна; Калинин Тимофей Артёмович; Федосеева Полина Романовна; Рябова Анастасия Григорьевна; Бочаров Степан Максимович; Симонов Демид Матвеевич; Волкова Екатерина Артёмовна; Леонтьев Артур Адамович; Кузнецова Алина Максимовна" >  ../mentors/mentors_list.txt
root@ubunto: less ../mentors/mentors_list.txt                                    root@ubunto: cd ..                                                               root@ubunto: mv mentors/mentors_list.txt students                                root@ubunto: cd mentors                                                          root@ubunto: ls                                                                  

root@ubunto: cd ..                                                               root@ubunto: cd students                                                         root@ubunto: ls                                                                  

mentors_list.txt  students_list.txt

root@ubunto: rm -r ../mentors                                                    root@ubunto: cd ..                                                               root@ubunto: ls                                                                  

**snap**  **students**

root@ubunto: mv students students_and_mentors                                    
root@ubunto: ls                                                                  

**snap**  **students_and_mentors**

root@ubunto: rm -r students_and_mentors                                          root@ubunto: ls                                                                  

root@ubunto: echo "Виноградова Алиса Александровна; Трофимова Вероника Егоровна; Калинин Тимофей Артёмович; Федосеева Полина Романовна; Рябова Анастасия Григорьевна; Бочаров Степан Максимович; Симонов Демид Матвеевич; Волкова Екатерина Артёмовна; Леонтьев Артур Адамович; Кузнецова Алина Максимовна" >  ~/file1

root@ubunto: ls                                                                  

file1  **snap**

root@ubunto: ls -li                                                              

total 8

 69905 -rw-r--r-- 1 root root  521 Jun 24 21:47 file1

258076 drwx------ 3 root root 4096 Jun 23 22:11 **snap**

root@ubunto:  cat file1 > file2                                                 root@ubunto: ls                                                                  

file1  file2  **snap**
root@ubunto: less file2                                                          root@ubunto: ln -s file1 file3                                                   root@ubunto: ls                                                                  

file1  file2  **file3**  **snap**

root@ubunto: ln file1 file4                                                      root@ubunto: ls                                                                  

file1  file2  **file3**  file4  **snap**

root@ubunto: ls -i                                                               

 69905 file1   69904 file2   70856 **file3**   69905 file4  258076 **snap**

root@ubunto: ls -li                                                              

total 16

 69905 -rw-r--r-- 2 root root  521 Jun 24 21:47 file1

 69904 -rw-r--r-- 1 root root  521 Jun 24 21:52 file2

 70856 lrwxrwxrwx 1 root root    5 Jun 24 21:54 **file3** -> file1

 69905 -rw-r--r-- 2 root root  521 Jun 24 21:47 file4

258076 drwx------ 3 root root 4096 Jun 23 22:11 **snap**

root@ubunto: rm file1                                                            root@ubunto: ls                                                                  

file2  **file3**  file4  **snap**

root@ubunto: cat file1                                                           

cat: file1: No such file or directory

root@ubunto: cat file2                                                           

Виноградова Алиса Александровна; Трофимова Вероника Егоровна; Калинин Тимофей Артёмович; Федосеева Полина Романовна; Рябова Анастасия Григорьевна; Бочаров Степан Максимович; Симонов Демид Матвеевич; Волкова Екатерина Артёмовна; Леонтьев Артур Адамович; Кузнецова Алина Максимовна

root@ubunto: cat file3                                                           

cat: file3: No such file or directory

root@ubunto: cat file4                                                           

Виноградова Алиса Александровна; Трофимова Вероника Егоровна; Калинин Тимофей Артёмович; Федосеева Полина Романовна; Рябова Анастасия Григорьевна; Бочаров Степан Максимович; Симонов Демид Матвеевич; Волкова Екатерина Артёмовна; Леонтьев Артур Адамович; Кузнецова Алина Максимовна

root@ubunto: mv file2 file2.txt                                                  root@ubunto: mv file4 link4                                                      root@ubunto: mv file3 link3                                                      root@ubunto: ls                                                                  

file2.txt  **link3**  link4  **snap**

root@ubunto: mkdir links                                                       root@ubunto: mv link4 ~/links/link4                                              root@ubunto: mv link3 ~/links/link3                                              root@ubunto: ls                                                                  

file2.txt  **links**  **snap**
root@ubunto: cd links                                                            root@ubunto: ls                                                                  

**link3**  link4

root@ubunto: 
```