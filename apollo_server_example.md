### example 1

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



### example 2
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
