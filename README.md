# Втора лабораториска вежба по Софтверско инженерство

## Дона Штерјова, бр. на индекс 206034


###  Control Flow Graph

![ControlFlow drawio](https://github.com/shterjovad/SI_2023_lab2_206034/assets/56770645/a6745d72-9fa0-49e0-bfec-dd4035998a00)
![Nodes Distribution] (https://github.com/shterjovad/SI_2023_lab2_206034/blob/master/Screen%20Shot%202023-05-31%20at%202.13.48%20AM.png)



### Цикломатска комплексност![Uploading ControlFlow.drawio.png…]()


Цикломатската комплексност на овој код е 1, истата ја добив преку броење на региони формирани од темињата и ребрата на сликата, во овој случај 10+1(надворешен)=11, и исто така преку формулата 32(ребра)-23(темиња)+2=11


### Тест случаи според критериумот  Every statement 

....

1. shterjovad, no pass, shterjovad@gmail.com
2. no username, Finki. , shterjovad@gmail.com, no existing email, nor username,
3. shterjovad, Finki123. , shterjovad@gmail.com, existing mail and username
4. shterjovad, F inki123., shterjovadgmail.com


### Тест случаи според критериумот Every Branch

1. shterjovad, no pass, shterjovad@gmail.com
2. no username, Finki. , shterjovad@gmail.com, no existing email, nor username,
3. shterjovad, Finki123. , shterjovad@gmail.com, existing mail and username
4. shterjovad, F inki123., shterjovadgmail.com
5. shterjovad, Finki123, shterjovadgmail.com

Секој од овие крајни тест случаи терминира со exception (пример 1) или со return statement (2,3,4,5).
2 тест пример терминира во return false во линија 63, а притоа ги скока if statements за да се утврди дали веќе постои акаунт со исти мејл и корисничко име и не влегува во нив.
3 тест пример терминира во return same == 0 во линија 69, и за разлика од тест случајот 2 влегува и во двете if услови, т.е веќе постои корисник со исто кор. име и е-адреса во базата. Додатно влегува и во if условот каде што потврдуваме дека нема празно поле во парвордот и во следиот услов каде што потврдуваме дека содржи специјален карактер.
4 тест пример терминита во последиот return false во 74та линија и главна цел му е да го опфати случајот каде што пасвордот содржи празно поле, па автоматски не е кредибилен да биде валиден пасворд за креирање на профил.
5 тест пример главна цел му е да го опфати граничниот случај кај што во пасвордот не се содржи специјален карактер, па 
по изминување на истиот преминува во return false во 74та линија.
.... 

### Тест случаи според критериумот Multiple Condition

1. user == null 
2. user.getPassword() == null
3. user.getEmail() == null
4. user!=null && user.getPassword()!=null && user.getEmail()!=null, па не влегуваме во if условот.

1,2,3 тест случаи бидејќи се одвоени со знакот или, би влегле во if условот кога било кое од нив би било исполнето и би ни фрлило исклучок со порака "Mandatory information missing!".
Конкретно во случај 1, не би било исполнето барањето доколку ја имаме следната иницијализација.
User user = null;
List<User> allUsers = new ArrayList<>();

if (user == null || user.getPassword() == null || user.getEmail() == null) {
    throw new RuntimeException("Mandatory information missing!");
}

Во тест случајот 2:
User user = new User();
user.setEmail("example@example.com");
user.setPassword(null);

List<User> allUsers = new ArrayList<>();

if (user == null || user.getPassword() == null || user.getEmail() == null) {
    throw new RuntimeException("Mandatory information missing!");
}
  
Или адекватно за тест случај 3 кога би го поставиле null како вредност во setEmail методот на објектот user.


### Објаснување на напишаните unit tests

...
...
