### example 1
```
const {ApolloServer, gql} = require("apollo-server");


const todos=[
    {task: 'wash car' , completed: false},
    {task: 'wash floor' , completed: true}
];


const typeDefs = gql`

    type Todo {
        task: String
        completed: Boolean
    }


    type Query {
    getTodos: [Todo]
  }
`;

const resolvers= {
    Query:{
        getTodos: ()=> todos
    }
}


const server = new ApolloServer({
    typeDefs,
    resolvers
});

server.listen().then(({url}) => {
    console.log(`server listening on ${url}`);
});

```

### example 2
https://www.youtube.com/watch?v=DyvsMKsEsyE&list=PLN3n1USn4xln0j_NN9k4j5hS1thsGibKi&index=1&ab_channel=BenAwad
```
const { ApolloServer, gql } = require("apollo-server");

const typeDefs = gql`
  type Query {
    hello: String!
  }
`;

const resolvers = {
  Query: {
    hello: () => "Hello World!"
  }
};

const server = new ApolloServer({ typeDefs, resolvers });

server.listen().then(({ url }) => console.log(`server started at ${url}`));
```

### example 3
https://www.youtube.com/watch?v=Y78PadVft7I&list=PLN3n1USn4xln0j_NN9k4j5hS1thsGibKi&index=2&ab_channel=BenAwad

```
const { ApolloServer, gql } = require("apollo-server");

// type checking
// query vs. mutation
// objects
// arrays
// arguments

// crud

const typeDefs = gql`
  type Query {
    hello: String
    user: User
  }
  type User {
    id: ID!
    username: String!
  }
  type Error {
    field: String!
    message: String!
  }
  type RegisterResponse {
    errors: [Error!]!
    user: User
  }
  input UserInfo {
    username: String!
    password: String!
    age: Int
  }
  type Mutation {
    register(userInfo: UserInfo!): RegisterResponse!
    login(userInfo: UserInfo!): Boolean!
  }
`;

const resolvers = {
  Query: {
    hello: () => null,
    user: () => ({
      id: 1,
      username: "bob"
    })
  },
  Mutation: {
    login: () => true,
    register: () => ({
      errors: [
        {
          field: "username",
          message: "bad"
        },
        {
          field: "username2",
          message: "bad2"
        }
      ],
      user: {
        id: 1,
        username: "bob"
      }
    })
  }
};

const server = new ApolloServer({ typeDefs, resolvers });

server.listen().then(({ url }) => console.log(`server started at ${url}`));

```
