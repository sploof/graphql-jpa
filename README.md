GraphQL from existing RDBMS (Futur Goal, not implemented yet)
=============================================================

This project aims to provide a fast way to direcltly bootstrap a GraphQL Api simply from your Jdbc-compatible database

The relational schema is first turned into an anemic Java Domain Model to start working with.
 
A full Java Model is Generated from the database, and can be maintained leveraging JPA / Hibernate tooling,  

This Java model is then exposed as a GraphQL Schema generated at runtime.


GraphQL for JPA
===============

The schema is derived from the JPA model first generated on server startup, see (https://github.com/jcrygier/graphql-jpa)

Schema Documentation
--------------------
Annotation-based Documentation from  [graphql-jpa](https://github.com/jcrygier/graphql-jpa) is available on Entities

If your Database follows naming conventions with non-obvious meanings, a global documentation for fields and tables 
can be generated from key-value Dictionnary to infer simple word-based descriptions

GraphiQL (https://github.com/graphql/graphiql) has been introduced for simple testing (in the test package, as I don't
want to assume your web stack).  Simply launch TestApplication as a Java Application, and navigate to http://localhost:8080/
to launch.  You will notice a 'Docs' button at the upper right, that when expanded will show you the running schema.

You can enter GraphQL queries in the left pannel, and hit the run button, and the results should come back in the right
panel.  If your query has variables, there is a minimized panel at the bottom left.  Simply click on this to expand, and
type in your variables as a JSON string (don't forget to quote the keys!).  Enjoy!

