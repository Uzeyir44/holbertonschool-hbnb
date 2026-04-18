##Architecture

```mermaid

flowchart TD
    subgraph P[Presentation Layer]
        direction TB
        Svc[Services]
        API[API Endpoints]
    end

    subgraph B[Business Logic Layer]
        direction TB
        User[User]
        Place[Place]
        Review[Review]
        Amenity[Amenity]
        Facade[Facade]
    end

    subgraph D[Persistence Layer]
        direction TB
        DAO[Database Access Objects]
        Repo[Repositories]
    end

    %% Communication pathways (Facade pattern)
    Svc --> Facade
    API --> Facade
    Facade --> User
    Facade --> Place
    Facade --> Review
    Facade --> Amenity
    User --> DAO
    Place --> Repo
    Review --> DAO
    Amenity --> Repo