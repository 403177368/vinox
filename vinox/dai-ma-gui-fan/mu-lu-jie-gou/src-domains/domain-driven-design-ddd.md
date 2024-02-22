# Domain Driven Design / DDD

## What is DDD?

DDD, or Domain-Driven Design, is a software design approach that focuses on complex needs by connecting the implementation to an evolving model of the core business concepts. It prioritizes the domain and domain logic, basing the design on the domain itself rather than the technology used to implement the system. DDD involves a close collaboration between technical experts and domain experts to improve the model and make it more relevant and useful, ensuring the software is deeply aligned with the business strategy. This approach helps in tackling complex designs by dividing them into smaller, more manageable subdomains, promoting a ubiquitous language for all stakeholders, and fostering a deep understanding of the domain itself, which leads to more effective and relevant software solutions.

Domain-Driven Design is an approach to software development that emphasizes the need to base the design on an evolving model of the core business concepts. It facilitates the collaboration between technical and non-technical stakeholders to create a common language that guides the project’s development.

**DDD is a design pattern for business system.**

## What is domain?

In the context of Domain-Driven Design (DDD), a **domain** refers to the sphere of knowledge and activity around which the intent of a software application is centered. It embodies the problems and solutions relevant to the business or area of interest being addressed by the system. Understanding the domain is crucial for developing software that meets the real-world needs of its users and stakeholders.

## Business Domain

The business domain refers to the specific area of a company's operations or expertise where the software is intended to be used. It encompasses the following aspects:

* **Specific Business Problems**: The unique challenges the business aims to solve with software.
* **Business Processes**: The set of activities that are performed to accomplish business objectives.
* **Business Rules**: The constraints and operations that govern business processes.
* **Terminology and Concepts**: The language and understanding peculiar to the business domain.

In the context of Domain-Driven Design, understanding the business domain is crucial for creating software that accurately reflects and serves the business's needs.

## Posts about DDD

{% embed url="https://en.wikipedia.org/wiki/Domain-driven_design" %}

{% embed url="https://docs.github.com/en/graphql/reference/objects" %}

{% embed url="http://www.javapractices.com/topic/TopicAction.do?Id=205" %}

## **Core Concepts of DDD:**

* **Entities**: Objects that have a distinct identity that runs through time and different states.
* **Value Objects**: Objects that do not have an identity and are immutable.
* **Aggregates**: A cluster of domain objects that can be treated as a single unit.
* **Repositories**: Mechanisms for encapsulating storage, retrieval, and search behavior.
* **Domain Events**: A way of recording the occurrence of something meaningful within the domain.
* **Services**: When an operation does not conceptually belong to any object.

## **Benefits of DDD:**

1. Improved communication among team members and stakeholders.
2. A focus on the core logic of business rules and policies.
3. Ease of modifying the system as the domain evolves.
4. Better domain knowledge leading to a more robust and scalable system.
