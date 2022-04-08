### PostgreSQL 명령어

<br>



### Basic

---

<br>

for help

```
/?
```

<br>

list database

```
\l
```

<br>

List all tables

```
\d
```

<br>

Table infomation ( 특정 테이블 정보 조회 )

```
\d database_name
```

<br>
<br>

### TABLE

---

Create database

```
CREATE DATABASE "database_name";
```

> 이전에는 어떻게 사용했는지는 모르겠지만,
> <br>데이터 베이스를 생성하려면 "데이터베이스 이름" 을 붙여야 한다고 한다.

<br>

Connect database

```
\c database_name
```

<br>
<br>

### MODIFY

<br>

#### ADD

---

ADD Column

```
ALTER TABLE table_name ADD COLUMN name text;
```

<br>
<br>

#### DROP

---

DROP Column

```
ALTER TABLE table_name DROP COLUMN name;
```

<br>

DROP Table

```
DROP TABLE table_name;
```

<br>

DROP Database

```
DROP DATABASE database_name;
```
