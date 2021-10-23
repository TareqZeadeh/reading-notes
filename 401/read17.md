# Read: Class 18 Read: 18 - Web App Security

## [Many to many relationships](https://www.baeldung.com/hibernate-many-to-many/)

### A Typical Example

1. any given employee can be assigned to multiple projects and a project may have multiple employees working for it, leading to a many-to-many association between the two.

### Database Setup

1. create the employee and project tables along with the employee_project join table with employee_id and project_id as foreign keys

### The Model Classes

1. The model classes Employee and Project need to be created with JPA annotations
1. both the Employee class and Project classes refer to one another, which means that the association between them is bidirectional.
1. In order to map a many-to-many association, we use the `@ManyToMany`, `@JoinTable` and `@JoinColumn` annotations.
1. This association has two sides i.e. the owning side and the inverse side. In our example, the owning side is Employee so the join table is specified on the owning side by using the `@JoinTable` annotation in Employee class. The `@JoinTable` is used to define the join/link table. In this case, it is Employee_Project.

## [Security: a humorous overview](https://scholar.harvard.edu/files/mickens/files/thisworldofours.pdf/)

Stories and examples from real life about security and how dangerous can it be but at the same time it is fun.