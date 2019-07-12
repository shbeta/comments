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

module.exports = mongoose.model('ahmad', userSchema);

```

