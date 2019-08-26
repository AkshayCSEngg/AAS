 # AAS

An application where student can contact to the employees of any company from any where in the world.
We'll use Android for front end, SQL for back end and Java language for business logics (Restful web services).

features: 

      1. User can connect via Internet.
      2. User can call from dashboard/home page where they get the employees data as per their interest (by default they will get highly rated employees data).
      3. User can recharge their wallet using different payment sources.
      4. User can call by filter option that includes: domain,experience, company, ratings etc. by clicking on call button.
      5. User can request to get notify when the busy or not available employees will get free or available. 

      6. Employee can set the schedule when they'll be busy and available. they can also change status when they want.
      7. Employee will get money directly to the bank account within an hour.
      8. Employee can select when they'll credited amount in the bank by setting up the threshold amount like after 100 rs or after 1 month.(future release).

# Main tasks/API's of AAS:

      1. Getting Information
      2. Storing Information
      3. Experience
      4. Ratings
      5. Suggestions(right now it's based on the user interest)
      6. Voice API Integration
      7. Availability
      8. Requesgt to call.
      9. Wallet.
      10. Payment Gateway

# Getting Information 
Information related to the Employees and Users on each page. So we need two Web services one for the Employees and another for the Users. 

Some of the methods of Employee Services are:

      public List<Employee> getEmployees();     -> List of 50 employees from different companies as well as from different profiles.
      
      public List<Employee> getEmployeesByCompanyName(String companyName);     ->List of 50 employee from same company which is companyName
      
      public List<Employee> getEmployeesByCompanyType(String companyType);(MNC/Startup/...)
      public List<Employee> getEmployeesByExperiece(float startingPoint); -> this method would return Employee list of having experience more than startingpoint.
      public Employee getEmployeeDetails(String someUniqueColumnVariable);
      
 
 method of User Services:
      
      public User getUserDetails(String someUniqueColumnVariable);
      
      
      

This application would have following functionality/modules:

      1. Login and SignUp page 
      2. Home page
      3. Wallet
      4. Logs
      5. Profile

1. Login and SignUp : User first needs to register, on registration page following information must be required as per the Users (Employee/Student):
      
      Common information
      a) Full Name
      b) DOB
      c) Email/Contact no.
      
      Student/Enquirer:
      a) Interesting Company Type(Startup/MNC/CMMI level)
      a) Interesting companies
      b) Interesting Fields(future release)
      
      Employee:
      a) Company name.
      b) Experience:
          b.1) Experience in current company. 
          b.2) Experience in Previous Company if any.
      c) Designation.
      d) Domain.
      
