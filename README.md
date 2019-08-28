 # AAS

An application where student can contact to the employees of any company from any where in the world.
We'll use Android for front end, SQL for back end and Java language for business logics (Restful web services).

features: 

      1. User can connect to the employee via Internet voice call.
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

      public List<Employee> getEmployees(String UserId);     -> Returns List of 30 employees from different companies as well as from different designation as per the interest of the User which would be getting by the help of UserId. If the interect section is not having anything or null then it will return the highly rated employees.
      
      public List<Employee> getEmployeesByCompanyName(String companyName);     -> Returns List of 30 employee from same company which is companyName in the parameter.
      
      public List<Employee> getEmployeesByCompanyType(String companyType);   -> Returns List of 30 employee as per the company type for Example: MNC, StartUp etc. 
      
      public List<Employee> getEmployeesByExperiece(float startingPoint); -> Returns List of 30 employee list of having experience more than startingpoint.
      
      public Employee getEmployeeDetails(String EmpId);   -> It will return all the information of Employee.
      
 
Method of User Services:
      
      public User getUserDetails(String someUniqueColumnVariable);   -> It will return all the information of User.
      
 # Storing Information

Some of the methods of Employee Services are:
  
      public void save(Employee entity); -> save the details of the employee into DB after validating it.
      
      public boolean update_Filed_Name(String EmpId, _Field_Variable_type_ fieldName); -> update the filed of the employee data and return true if success else false.
         *Note* : This method is just prototype where update_Filed_Name is the field name that should be update.
         *for exanmple* : for update the date of birth method would looks like:
                   public boolean updateDateOfBirth(String EmpId, Date newDateOfBirth);
      
Method of User Services:
      
      public void save(User entity);
      
      public boolean update_Filed_Name(String userId, _Field_Variable_type_ fieldName );
  

# Experience Calcultaion:
 
 Experience will get as per the duration from joining date in the comapny to the current date.
 it would return in the following formate:
 
 below 12 months result would be in String example if its 3 months and 15 days it will return "3.5 months"
 above 12 months result would be in String example if it's 1 year, 2 months and 12 days it will return "1.2+ years"
 and the method would be
	
	     public String getExperience(String EmpId);
	     
 Note: If we'll fetch data from the linkedIn API then we'll save that details into out DataBase and we'll perform CRUD operation.
   
# Ratings Calculation

 Retings will be calculated on average basis. All the user will seperatly rate to an employee and DB will store two things first the count associates with their ratesand second overall ratings that will show on employees profile.
 
 Example:
 	
	Satisfatory -> 5  ,	Average -> 6  ,		Poor = -> 3
	
		average = abs(Satisfatory+Average-Poor)/2
		scaling = average % 5
		
	to get in the scale of 5 = average%5 = 4%5 = 4
	
 IF the final value is more than 2.5(half of 5, the scale value) then rating is satisfactory. If it's below that than it's poor. If it's 2.5 then average.


# Suggestions(right now it's based on the user interest)
 
 We'll take the interests of the user at the time of signup (as we did while signup into any music app), based on that interest we'll show the results.

	some posible interests:
		1) Company
		2) Company Type
		3) Experience
		4) Skils and so on
		
# Voice Calling API Integration

 It's the core API which we'll use we've many APIs to choose we'll decide on the negotiation basis as we need to pay for it.
 	
	We'll go oe of the following APIs:
		 Twilio
		 Sinch
		 Tokbox and so on		 
 
# Availability Management
 This Api will manage the availability status from employee save their availability schedule to the update the status, includeing the getCurrentStatus.

# Requesgt to call.
 This Api will manage the flow of communication it will allow the notification system. If an employee is not available user can request to inform and will get the notification when the employee gets available or comes online.
 
# Wallet and Payment Gateway.
 This whould have the information about the balance a person have with the payment recharge. 
 
 	getBalance()
	rechargeWallet()
	updateBalance()
	getRecord()
	setRecord()


* This application would have following functionality/modules:

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
   
