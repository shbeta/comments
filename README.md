## My comment is all here

an example to model User page

### User.js page

```markdown
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
    name:{
        type: String,
        required: true,
        min: 6,
        max: 255
    },
    email:{
        type: String,
        required: true,
        min: 6,
        max: 255
    },
    password:{
        type: String,
        required: true,
        min: 6,
        max: 1024
    },
    date:{
        type: Date,
        default: Date.now
    }

});

module.exports = mongoose.model('user', userSchema);

```


### auth.js page
```markdown
const router= require('express').Router();
const User= require('../model/User');

router.post('/register', async (req,res)=>{
    const user = new User({
        name: req.body.name,
        email: req.body.email,
        password: req.body.password,  
    });
    try{
        const savedUser = await user.save();
        res.send(savedUser);
    }catch(err){
        res.status(400).send(err);
    }

});
module.exports = router;

```
### app.js page
```
const express=require('express');
const app = express();
const mongoose = require('mongoose');
const dotenv = require('dotenv');
// include routes auth
const auth= require('./routes/auth');

dotenv.config();

//connect to db
mongoose.connect(process.env.DB_CONNECT,
{ useNewUrlParser: true },() => console.log('connect to db!')
);

app.use(express.json());

//run auth middleware
app.use("/api/user/", auth);


app.listen(3000, ()=> console.log('server is now up'));
```
