### let me check this 


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
````
