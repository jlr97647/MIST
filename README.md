# MIST-4610-Project-1

Team Name: BULLDAWGS

# Members:

Miles Cohall [@fromj50](https://github.com/fromj50)

Lucas Ramos [@jlr97647](https://github.com/jlr97647)

Cameron Saini [@cameronsain](https://github.com/CameronSaini)

Hitanshi Shah [@hshah56](https://github.com/hshah56)

Tyler Martin [@tjm44974](https://github.com/tjm44794)

# Scenario Description:

Our team was instructed to make a database for a construction project management firm. The central entity is contractors, as the project management firm has to keep tabs on each contractor that works for them. Contractors that work for the firm and are in charge of projects are called general contractors. These general contractors can work together on multiple projects and can also hire subcontractors for specific work such as electricity, plumbing, HVAC, etc. The general contractors must know characteristics of each project such as; the landowner tied to a project, what subcontractors are working on each project, what suppliers supplied each project, how many tasks each project has, and what permits each project has. In addition, the project management firm can also see which general contractors are tied to a specific landowner and what architecture firm supplied the building plans to that landowner. Based on these factors, we have acquired sample data to populate the database. Using this data, we can run a multitude of queries to answer mission critical questions.

# Data Model:

It is easy to understand this data model starting with a landowner. Each landowner’s attributes are listed under the owners entity. An owner can own multiple properties, hence the one-to-many relationship between owners and land_properties. 

Each owner can acquire building plans from an architecture firm, and an architecture firm can supply many owners with building plans. This is modeled by a one-to-many relationship between architecture_firms and owners. 

Each architecture firm can create many building plans, but each building plan can only be tied to one architecture firm. Also, a building plan cannot exist without an architecture firm. This is modeled by a one-to-many identifying relationship between architecture_firms and building_plans. 

Once an owner has acquired their building plans they go to the construction project management firm who will tie them to a contractor. An owner can only be tied to one contractor but a contractor can work for many owners. This is modeled by a one-to-many relationship between contractors and owners. 

Contractors that work for the construction project management firm are called general contractors. A general contractor can hire many subcontractors to work for them on specific projects. This is modeled by a one-to-many recursive relationship in the contractors entity. 

Many contractors can work on many projects and many projects can be worked on by multiple contractors. This is modeled by a many-to-many relationship between contractors and projects.

Also, each project is tied to a landowner. An owner can have multiple projects going on, but a project can only be tied to one owner. This is modeled by a one-to-many relationship between owners and projects. 

A specific project can have many tasks that need to be accomplished within them. A task can only exist under a project. This is modeled by a one-to-many identifying relationship between projects and project_tasks. 

Each specific project has to acquire many different materials. Many different projects need many different materials. Materials are supplied to a project through suppliers. This is modeled by a many-to-many relationship between projects and suppliers. 

Each specific project requires many permits. A permit can only relate to one specific project. Permits can only exist under a specific project. This is modeled by a one-to-many relationship between projects and permits. 

![data model for project](https://github.com/user-attachments/assets/cd6e76c3-b97a-4777-9038-884c4920b86a)

# Data Dictionary:
<img width="709" alt="image" src="https://github.com/user-attachments/assets/cedb2142-8efc-4d65-b042-1507c9f42d67">
<img width="707" alt="image" src="https://github.com/user-attachments/assets/798b4822-7d64-44b8-8ac8-07aaa61ff83e">
<img width="705" alt="image" src="https://github.com/user-attachments/assets/1497c517-ff33-46fe-8cc9-cc1cdafde578">
<img width="706" alt="image" src="https://github.com/user-attachments/assets/9d3117a9-99f8-49e8-98ae-020011399135">
<img width="705" alt="image" src="https://github.com/user-attachments/assets/0fe48e54-c79d-400c-a83a-26c3cddb2576">
<img width="706" alt="image" src="https://github.com/user-attachments/assets/05c1eb49-9dd1-4575-b332-af968c7f1353">
<img width="702" alt="image" src="https://github.com/user-attachments/assets/1877b204-d94b-4e4a-824b-480485e55e07">
<img width="700" alt="image" src="https://github.com/user-attachments/assets/d22c3a62-83f8-4d37-9c63-b41104263c2e">
<img width="704" alt="image" src="https://github.com/user-attachments/assets/1acf3939-8388-4d0b-ac8a-4ba45bcc1d12">
<img width="704" alt="image" src="https://github.com/user-attachments/assets/a8e6a094-52bb-4cb6-9bc7-234c072ea2c5">
<img width="707" alt="image" src="https://github.com/user-attachments/assets/1cd44fe1-608b-4db3-bc3d-f44945f1227c">





# Queries:

Query 1:

Query 1 helps us find the contractors that are working on multiple projects as well as the number of projects they’re working on. This is significant because we need to know each contractor's capacity so that our company can probably allocate resources and plan accordingly. By identifying which contractors are involved in more than one project, the company can properly ensure that they are using all their resources in the most efficient manner and avoid the cost of delays. This is also great for other aspects like viewing performance insights, risk management, contractor relationships, and providing rationale behind satisfaction surveys.
<img width="1252" alt="image" src="https://github.com/user-attachments/assets/f0e4c6c7-1320-49b8-8871-2ae206993e54">


Query 2:

Query 2 provides us with a comprehensive workload overview so that we understand each contractor's task-level accountability. This displays each employee's involvement in the firm and can highlight which contractors are able to handle larger loads of work & efficiently manage their time. Work distribution is another aspect that can be an important find within this query as it can prevent overburdening one contractor with too many tasks and so that we aren’t causing delays or missing deadlines for the overall projects. Lastly, this could be beneficial for vendor management as the contracts working on a high level of tasks could be increasingly valuable to the company, helping the company recruit from within and could be a valuable insight when discussing contracts. 
<img width="1252" alt="image" src="https://github.com/user-attachments/assets/61c7448e-6468-48d6-a7fb-ec63c9f7aa26">


Query 3:

This query allows managerial staff to get a general overview of all current and active projects assigned to subcontractors. This is vital to any firm seeking to ensure integrity and timely management and project completion. It is crucial to stay on track with deadlines, as permits only have a finite lifespan, and being past due can be costly to everyone involved. Having a general overview can alleviate stress and uncertainty, and can increase timely project completion.
<img width="1251" alt="image" src="https://github.com/user-attachments/assets/b8b42e4b-6051-4066-9cc7-08604354e2f2">


Query 4:

Query 4 helps with revealing the amount of supplies for each project which is useful for project complexity indicators, supplier dependency, and supply chain efficiency. Looking into project complexity indicators, projects with higher supplier amounts could be challenging projects & more complex. This was managers can allocate more time into these projects and focus on these coordinating efforts so that there is smooth collaboration. This is a similar concept with supplier dependency as it allows the company to know which suppliers are able to handle a multitude of tasks and if they are efficiently managing their time. This could influence managers decision making in terms of hiring and whether they should be monitoring the projects closely or not so deadlines are met. Finally, if some projects require less number of suppliers, this means they might have streamlined processes which would impact the supply chain efficiency. 
<img width="1254" alt="image" src="https://github.com/user-attachments/assets/36e59d10-9ed9-4c59-a412-0c90b3e8fb2b">


Query 5:

Query 5 is important since it highlights the landowners with the highest land value, something that could be highly useful. This could provide insight into real estate investments for this company and which owners could be repeat customers, ensuring better asset management as well as decision making for clientele. Similarity, the company is now aware of which owners to prioritize relationships with so that they can find opportunities for future transactions. Second, this supports risk management since the company would know where concentrations of land value differ and lie so they can plan strategically in case of economic shifts in the government.
<img width="1252" alt="image" src="https://github.com/user-attachments/assets/953b2522-7799-4112-879a-528838e37a44">


Query 6:

Query 6 simply ensures project managers and contractors know when to reapply for permits that are useful and necessary to their tasks and projects. This ensures that they are hitting deadlines and are not causing costly delays or damages to any relationships between themselves and their customers. This is a method of proper strategic planning and being prepared so that risk management is up-to-date and they aren’t vulnerable to legal or regulatory setbacks. 
<img width="1179" alt="image" src="https://github.com/user-attachments/assets/93a8fe08-5463-4b01-aac4-e62921730ae9">


Query 7:

Query 7 is useful because it reveals which supplier helped supply material to each project, based on a specific material in mind. If a finished project turns out to be good or bad, then this query will give the supplier name and their email to either order more materials or send complaints regarding a project that has been built.
<img width="1179" alt="image" src="https://github.com/user-attachments/assets/310aaa76-ac70-4a19-8f39-ff1335f54698">


Query 8:

Query 8 allows a general contractor  to see which tasks are tied to a specific project. This allows the general contractor to create a plan of action for the tasks in each project. The task description allows the general contractor to see what the goal of each task is, an idea of what materials are needed, and an idea of what subcontractors will be needed. The general contractor will also be able to see which tasks have been started and/or finished.
<img width="1179" alt="image" src="https://github.com/user-attachments/assets/0242a308-c824-41f0-89fc-66022477e65c">


Query 9:

This query lists all building plans assigned to a specific architecture firm. It is useful to know which architecture firms are handling which building plans and vice versa. If something were to go wrong or something specific needs to be addressed concerning building plans, the management department must be able to reach out to the respective architecture firm that drafted them.
<img width="1179" alt="image" src="https://github.com/user-attachments/assets/9b5f0cbd-bef0-4208-a73d-c7b81e34bf6b">


Query 10:

Query 10 is important because it helps management identify which suppliers are currently available to help aid a specific project, because suppliers with no current projects are more likely to deliver materials faster and have them in stock.
<img width="1181" alt="image" src="https://github.com/user-attachments/assets/2dfdc438-8fde-45e0-82db-51609ceef0aa">

<img width="405" alt="image" src="https://github.com/user-attachments/assets/54434a16-d018-4e67-ac3a-2c4992f02160">

# Database Information
Database name: cs_tjm44794

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format:CALL TP_Q1();






