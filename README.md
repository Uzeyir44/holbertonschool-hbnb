##Architecture

###Package Diagram

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


###Class Diagram

```mermaid

classDiagram
    class User {
        +UUID4 id
        +string name
        +string email
        +datetime created_at
        +datetime updated_at
        +createReview(place: Place, text: string): Review
        +updateProfile(name: string, email: string)
    }

    class Place {
        +UUID4 id
        +string name
        +string description
        +string location
        +datetime created_at
        +datetime updated_at
        +addAmenity(amenity: Amenity)
        +getReviews(): List~Review~
    }

    class Review {
        +UUID4 id
        +string text
        +int rating
        +datetime created_at
        +datetime updated_at
        +updateReview(text: string, rating: int)
    }

    class Amenity {
        +UUID4 id
        +string name
        +string type
        +datetime created_at
        +datetime updated_at
    }

    %% Relationships and multiplicities
    User "1" --> "many" Review : writes
    Place "1" --> "many" Review : receives
    Place "1" --> "many" Amenity : includes
    Review "1" --> "1" Place : about
    Review "1" --> "1" User : by