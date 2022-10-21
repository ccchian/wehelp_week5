## 1.建立一個新的資料庫，取名字為 website。
create database website;

<img src="https://github.com/ccchian/wehelp_week5/blob/main/create.png"></img>

## 2.在資料庫中，建立會員資料表，取名字為 member。資料表必須包含欄位設定
mysql> CREATE TABLE member( <br>
    -> id bigint PRIMARY KEY AUTO_INCREMENT,  <br>
    -> name varchar(255) NOT NULL, <br>
    -> username varchar(255) NOT NULL,  <br>
    -> password varchar(255) NOT NULL,  <br>
    -> follower_count int unsigned NOT NULL default 0,  <br>
    -> time datetime NOT NULL DEFAULT NOW())  <br>
    -> ;
    
 <img src='https://github.com/ccchian/wehelp_week5/blob/main/create%20table%20member.jpg'></img>
    
## 3.使用 INSERT 指令新增一筆資料到 member 資料表中，這筆資料的 username 和 password 欄位必須是 test。接著繼續新增至少 4 筆隨意的資料。
mysql> INSERT INTO member <br>
    -> (name,username,password,follower_count,time)  <br>
    -> VALUES  <br>
    -> ("AA","test","test",2,NOW());  <br>
...以此類推，替換values內的值

## 4.使用 SELECT 指令取得所有在 member 資料表中的會員資料。
select * from member;

 <img src='https://github.com/ccchian/wehelp_week5/blob/main/INSERT%20INTO%20member:select*from%20member.jpg'></img>

## 5.使用 SELECT 指令取得所有在 member 資料表中的會員資料，並按照 time 欄位，由近到遠排序。
select * from member order by time DESC;

 <img src='https://github.com/ccchian/wehelp_week5/blob/main/all%20DESC.jpg'></img>

## 6.使用 SELECT 指令取得 member 資料表中第 2 ~ 4 共三筆資料，並按照 time 欄位，
由近到遠排序。( 並非編號 2、3、4 的資料，而是排序後的第 2 ~ 4 筆資料 )
mysql> select * from member  <br>
    -> WHERE 1=1  <br>
    -> order by time desc  <br>
    -> limit 1,3; <br>
    
<img src='https://github.com/ccchian/wehelp_week5/blob/main/%E5%8F%96%E7%AC%AC%E4%BA%8C%E5%88%B0%E5%9B%9B%E7%AD%86%E8%B3%87%E6%96%99.jpg'></img>    
    
## 7.使用 SELECT 指令取得欄位 username 是 test 的會員資料。
select id,username,password,follower_count,time from member where username="test";

 <img src='https://github.com/ccchian/wehelp_week5/blob/main/username%3Dtest.jpg'></img>

## 8.使用 SELECT 指令取得欄位 username 是 test、且欄位 password 也是 test 的資料。
select * from member where username="test" and password="test";

 <img src='https://github.com/ccchian/wehelp_week5/blob/main/usename:pwd%3Dtest.png'></img>

## 9.使用 UPDATE 指令更新欄位 username 是 test 的會員資料，將資料中的 name 欄位改成 test2。
UPDATE member SET name="test2" where username="test";

 <img src='https://github.com/ccchian/wehelp_week5/blob/main/test2.png'></img>

## 10.取得 member 資料表中，總共有幾筆資料 ( 幾位會員 )。
 select count( * ) as 總共有幾筆資料 from member;
 
  <img src='https://github.com/ccchian/wehelp_week5/blob/main/%E7%B8%BD%E5%85%B1%E5%B9%BE%E7%AD%86%E8%B3%87%E6%96%99.jpg'></img>
 
## 11.取得 member 資料表中，所有會員 follower_count 欄位的總和。
select sum(follower_count)  <br>
    -> from member;  <br>
    
  <img src='https://github.com/ccchian/wehelp_week5/blob/main/%E7%B8%BD%E5%92%8C.jpg'></img>
    
## 12.取得 member 資料表中，所有會員 follower_count 欄位的平均數。
select avg(follower_count) as follower_count 平均 from memer;

   <img src='https://github.com/ccchian/wehelp_week5/blob/main/%E5%B9%B3%E5%9D%87.jpg'></img>
   
