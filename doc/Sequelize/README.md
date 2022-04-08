### Sequelize

<br>

#### 참고

> https://sequelize.org/


<br>
<br>

### Installation & Setup

```
npm install --save-dev sequelize-cli

npx sequelize-cli init
```

* config, contains config file, which tells CLI how to connect with database

* models, contains all models for your project
 
* migrations, contains all migration files
 
* seeders, contains all seed files


<br>
<br>

### 모델 생성

---

```
npx sequelize-cli model:generate --name User --attributes email:string
```

<br>
<br>


### migration

---

20220408022030-create-user.js (migration으로 만들어진 user.js)

```js
'use strict';
module.exports = {
  async up(queryInterface, Sequelize) {
    await queryInterface.createTable('Users', {
      id: {
        allowNull: false,
        autoIncrement: true,
        primaryKey: true,
        type: Sequelize.INTEGER
      },
      email: {
        type: Sequelize.STRING,
        allowNull: false, // 필수값, null을 허용하지 않음.
        unique: true
      },
      createdAt: {
        allowNull: false,
        type: Sequelize.DATE
      },
      updatedAt: {
        allowNull: false,
        type: Sequelize.DATE
      }
    });
  },
  async down(queryInterface, Sequelize) {
    await queryInterface.dropTable('Users');
  }
};
```

<br>

하지만 데이터 모델의 이름은 camelCase가 아닌 snake_case를 써야함.
다음과 같이 이름을 정정해야 한다.

```js
'use strict';
module.exports = {
  async up(queryInterface, Sequelize) {
    await queryInterface.createTable('Users', {
      id: {
        allowNull: false,
        autoIncrement: true,
        primaryKey: true,
        type: Sequelize.INTEGER
      },
      email: {
        type: Sequelize.STRING,
        allowNull: false, // 필수값, null을 허용하지 않음.
        unique: true
      },
      created_at: {
        allowNull: false,
        type: Sequelize.DATE
      },
      updated_at: {
        allowNull: false,
        type: Sequelize.DATE
      }
    });
  },
  async down(queryInterface, Sequelize) {
    await queryInterface.dropTable('Users');
  }
};
```
