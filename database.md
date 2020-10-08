# SPRING and Database    
[Home](./README.md) 

[Many to Many](https://www.baeldung.com/hibernate-many-to-many)  

How to join two models with join table in JPA
```
	@Entity
@Table(name = "Employee")
public class Employee { 
    // ...
 
    @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "Employee_Project", 
        joinColumns = { @JoinColumn(name = "employee_id") }, 
        inverseJoinColumns = { @JoinColumn(name = "project_id") }
    )
    Set<Project> projects = new HashSet<>();
   
    // standard constructor/getters/setters
}
@Entity
@Table(name = "Project")
public class Project {    
    // ...  
 
    @ManyToMany(mappedBy = "projects")
    private Set<Employee> employees = new HashSet<>();
    
    // standard constructors/getters/setters   
}
```
