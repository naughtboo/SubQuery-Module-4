# subquery Module 4 solution

## for ex1
![mod4 ex1](https://user-images.githubusercontent.com/66467667/148680638-c343a00d-dcc3-4d89-9239-9218bf4cf743.png)
## for ex2
![mod4 ex2](https://user-images.githubusercontent.com/66467667/148680671-8f652114-9e5f-467b-a93a-7ccd4a3b5fa4.png)
## for ex3
![mod4 ex3-1](https://user-images.githubusercontent.com/66467667/148680676-1c141a3b-9e60-4f3e-bf24-f1c483c781c8.png)
![mod4 ex3-2](https://user-images.githubusercontent.com/66467667/148680678-d107fd3d-a7ae-4f3e-9b22-07807768e929.png)
## for ex4
![mod4 ex4](https://user-images.githubusercontent.com/66467667/148680684-3fe88688-23c5-4f3a-a3ed-b5b160496e7e.png)




# SubQuery - Starter Package


The Starter Package is an example that you can use as a starting point for developing your SubQuery project.
A SubQuery package defines which data The SubQuery will index from the Substrate blockchain, and how it will store it. 

## Preparation

#### Environment

- [Typescript](https://www.typescriptlang.org/) are required to compile project and define types.  

- Both SubQuery CLI and generated Project have dependencies and require [Node](https://nodejs.org/en/).
     

#### Install the SubQuery CLI

Install SubQuery CLI globally on your terminal by using NPM:

```
npm install -g @subql/cli
```

Run help to see available commands and usage provide by CLI
```
subql help
```

## Initialize the starter package

Inside the directory in which you want to create the SubQuery project, simply replace `project-name` with your project name and run the command:
```
subql init --starter project-name
```
Then you should see a folder with your project name has been created inside the directory, you can use this as the start point of your project. And the files should be identical as in the [Directory Structure](https://doc.subquery.network/directory_structure.html).

Last, under the project directory, run following command to install all the dependency.
```
yarn install
```


## Configure your project

In the starter package, we have provided a simple example of project configuration. You will be mainly working on the following files:

- The Manifest in `project.yaml`
- The GraphQL Schema in `schema.graphql`
- The Mapping functions in `src/mappings/` directory

For more information on how to write the SubQuery, 
check out our doc section on [Define the SubQuery](https://doc.subquery.network/define_a_subquery.html) 

#### Code generation

In order to index your SubQuery project, it is mandatory to build your project first.
Run this command under the project directory.

````
yarn codegen
````

## Build the project

In order to deploy your SubQuery project to our hosted service, it is mandatory to pack your configuration before upload.
Run pack command from root directory of your project will automatically generate a `your-project-name.tgz` file.

```
yarn build
```

## Indexing and Query

#### Run required systems in docker


Under the project directory run following command:

```
docker-compose pull && docker-compose up
```
#### Query the project

Open your browser and head to `http://localhost:3000`.

Finally, you should see a GraphQL playground is showing in the explorer and the schemas that ready to query.

For the `subql-starter` project, you can try to query with the following code to get a taste of how it works.

````graphql
{
  query{
    starterEntities(first:10){
      nodes{
        field1,
        field2,
        field3
      }
    }
  }
}
````
