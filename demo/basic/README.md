# Demo

```javascript
const level = require('level')
const levelize = require('../../index')
const levelize = new Levelize(level)
const dbName = 'levelize-demo-2019';
levelize.connect('levelize-demo-2019')

const UserShema = new levelize.Schema({ id: String, username: String, passpord: String });
const UserModel = levelize.model('UserShema', UserShema);

UserModel.createOne({ username: 'andy' }, (err, user) {
  if(err)return console.log(err);
  console.log(user)
})

UserModel.findOne({ username }, (err, user) {
  if(err)return console.log(err);
  console.log(user)
})
```