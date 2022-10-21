## 1.建立一個新的資料庫，取名字為 website。
create database website;

<img src="[https://github.com/ccchian/wehelp_week5/commit/423dab1196debd4980b9eb5eb159d6906e1990ac](https://github.com/ccchian/wehelp_week5/blob/main/data.sql](https://github.com/ccchian/wehelp_week5/blob/main/usename:pwd%3Dtest.jpg)"></img>


## 2.在資料庫中，建立會員資料表，取名字為 member。資料表必須包含欄位設定
mysql> CREATE TABLE member(
    -> id bigint PRIMARY KEY AUTO_INCREMENT,
    -> name varchar(255) NOT NULL,
    -> username varchar(255) NOT NULL,
    -> password varchar(255) NOT NULL,
    -> follower_count int unsigned NOT NULL default 0,
    -> time datetime NOT NULL DEFAULT NOW())
    -> ;
4.使用 INSERT 指令新增一筆資料到 member 資料表中，這筆資料的 username 和 password 欄位必須是 test。接著繼續新增至少 4 筆隨意的資料。
mysql> INSERT INTO member
    -> (name,username,password,follower_count,time)
    -> VALUES
    -> ("AA","test","test",2,NOW());
替換values內的值
5.使用 SELECT 指令取得所有在 member 資料表中的會員資料。
select * from member;
6.使用 SELECT 指令取得所有在 member 資料表中的會員資料，並按照 time 欄位，由
近到遠排序。
select * from member order by time DESC;
7.使用 SELECT 指令取得 member 資料表中第 2 ~ 4 共三筆資料，並按照 time 欄位，
由近到遠排序。( 並非編號 2、3、4 的資料，而是排序後的第 2 ~ 4 筆資料 )
mysql> select * from member
    -> WHERE 1=1
    -> order by time desc
    -> limit 1,3;
8.使用 SELECT 指令取得欄位 username 是 test 的會員資料。
select id,username,password,follower_count,time from member where username="test";
9.使用 SELECT 指令取得欄位 username 是 test、且欄位 password 也是 test 的資料。
select * from member where username="test" and password="test";
10.使用 UPDATE 指令更新欄位 username 是 test 的會員資料，將資料中的 name 欄位改
成 test2。
UPDATE member SET name="test2" where username="test";
要求四：
11.取得 member 資料表中，總共有幾筆資料 ( 幾位會員 )。
 select count( * ) as 總共有幾筆資料 from member;
12.取得 member 資料表中，所有會員 follower_count 欄位的總和。
select sum(follower_count)
    -> from member;
13.取得 member 資料表中，所有會員 follower_count 欄位的平均數。
select avg(follower_count) as follower_count 平均 from memer;
