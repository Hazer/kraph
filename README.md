# Kraph [![Build Status](https://travis-ci.org/taskworld/kraph.svg?branch=master)](https://travis-ci.org/taskworld/kraph)  [ ![Download](https://api.bintray.com/packages/tw/maven/kraph/images/download.svg) ](https://bintray.com/tw/maven/kraph/_latestVersion)
In short, this is a GraphQL request JSON body builder for Kotlin. It will generate the JSON string for request body that work with GraphQL Server. For example, we have the GraphQL query for list all the notes.
```
    query {
        notes {
            id
            createdDate
            content
            author {
                name
                avatarUrl(size: 100)
            }
        }
    }
```
And here is how we write it in Kotlin using Kraph.
```
    Kraph {
        query {
            fieldObject("notes") {
                field("id")
                field("createdDate")
                field("content")
                fieldObject("author") {
                    field("name")
                    field("avatarUrl", mapOf("size" to 100))
                }
            }
        }
    }
```
As you can see, we can achieve our goal with just a few tweaks from the original query.

**NOTE:** Kraph is still in an early stage. The usage may change in further development.

### Features
- DSL builder style. Make it easier to read and use.
- Support both Query and Mutation operation.

### Set up
Adding Kraph to `build.gradle`
```
    repositories {
        jcenter()
    }
    
    dependencies {
        compile "com.taskworld.kraph:kraph:x.y.z"
    }
```

### Usage
Please see the example from `sample` folder for now. We will update this part ASAP.

### Contributing to Kraph
We use Github issues for tracking bugs and requests. Any feedback and/or PRs is welcome.