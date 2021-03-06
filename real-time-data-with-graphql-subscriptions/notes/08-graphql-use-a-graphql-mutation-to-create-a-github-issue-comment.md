# Use a GraphQL Mutation to Create a Github Issue Comment

**[📹 Video](https://egghead.io/lessons/graphql-use-a-graphql-mutation-to-create-a-github-issue-comment)**

**[💻 Course repo](https://github.com/theianjones/egghead-graphql-subscriptions)**

## Summary

`Mutations` are like `queries` that allow us to write data. The arguments passed to the `mutation` are wrapped in an `input` object. We still declare the fields we would like to get back from the `mutation`. This is like declaring a `query` that gets run immediately after the `mutation`.

## Mutations

In GraphQL, `queries` are used to read data and `mutations` are used to write data. The way we structure a `mutation` is the same as a `query`, except that we wrap any dynamic variables we want to pass to the `mutation` in an `input` key.

```gql
mutation NewTodo($title: String!, $isCompleted: Boolean) {
  todo(input: {
    title: $title
    isCompleted: $isCompleted
  }) {
    id
    title
    isCompleted
  }
}
```

We still specify the fields we want to get back after the `mutation` is complete, kind of like a `query` to run immediately after the `mutation`. This allows us to request any fields we want to display in our application, including those that were generated by the server - in the example above `id` was generated with the creation of the todo.

In the video example we are sending an `addComment` mutation to the GitHub service. This requires a `subjectId`, to determine which issue we are commenting on, and a `body`, containing the actual comment text. The `OneGraphiQL` explorer allows us to click through the fields we want to get back after the `mutation` is complete - exactly the same as when we were building our `queries`.

## Helpful Links 🤔

[GraphQL docs on Queries and Mutations](https://graphql.org/learn/queries/#mutations)

---

📹 [Go to Previous Lesson](https://egghead.io/lessons/graphql-style-a-list-component)
📹 [Go to Next Lesson](https://egghead.io/lessons/graphql-use-urqls-usemutation-to-create-github-issues-in-a-react-app)
