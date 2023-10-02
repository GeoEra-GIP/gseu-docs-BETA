# Data Work flow

This file contains the source code for diagrams in mermaid syntax. The code can be transformed to images here:

[Mermaid Live Editor](https://mermaid-js.github.io/mermaid-live-editor/)

We could install the Mermaid plugin so that the code is automatically converted to diagrams.

```mermaid
graph TD
A(Decide how to deliver data<br/>Read the Delivering Data to EGDI section)
--> B(Register metadata in MIcKA <br/>Read the MIcKA cookbook)
--> C(Upload data / register service <br/> Set up Maps and Layers <br/> Read the EGDI Administration Module section)
```

```mermaid
classDiagram
Class ProjectSite
ProjectSite -- "0..*" Document
ProjectSite : +int id
ProjectSite : +geometry geom
ProjectSite : +String sitename
ProjectSite : +String sitedescription
class Document{
+int projectSiteId
+string repositoryURL
}
```

```mermaid
classDiagram
ProjectSite
ProjectSite -- "0..*"LinkTable
ProjectSite : +int Id
ProjectSite : +string description
ProjectSite : +geometry geom
LinkTable "0..*" -- Reference
LinkTable: +int projectSiteId
LinkTable: +int referenceId
Reference: +int Id
Reference: +string title
Reference: +string authors
Reference: +string doi
```

```mermaid
erDiagram
    CAR ||--o{ NAMED-DRIVER : carId
    CAR {
        int carId
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : pesonId
    PERSON {
        int personId
        string firstName
        string lastName
        int age
    }
     NAMED-DRIVER {
       int personId
       int carId
     }
```
