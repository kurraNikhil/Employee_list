# emp
class Employee:
    employeelist =list()
    def __init__(self, empNo, empName, empDes, empSal):
        self.empNo, self.empName, self.empDes, self.empSal = empNo, empName, empDes, empSal
    def addNewEmployee(self):
        Employee.employeelist.append(self)  
    def getEmpList(self):
        return Employee.employeelist  
    def modifyEmpById(self, empNo, empName, empDes, empSal):
        for emp in Employee.employeelist:
            if(emp.getEmpNo() == empNo):
                emp.empNo, emp.empName, emp.empDes, emp.empSal = empNo, empName, empDes, empSal
                return True
        return False   
    def deleteEmpById(self, empNo):
         for emp in Employee.employeelist:
            if(emp.getEmpNo() == empNo):
                Employee.employeelist.remove(emp)
                return True
         return False      
    def setEmpNo(self, empNo):
        self.empNo = empNo
    def getEmpNo(self):
        return self.empNo  
    def setEmpNo(self, empName):
        self.empName = empName
    def getEmpNo(self):
        return self.empName
    def setEmpNo(self, empDes):
        self.empDes = empDes
    def getEmpNo(self):
        return self.empDes 
    def setEmpNo(self, empSal):
        self.empSal = empSal
    def getEmpNo(self):
        return self.empSal 
    def __str__(self):
        return "%d %s %s %d"%(self.empNo, self.empName, self.empDes, self.empSal)

choice = 1
employee = Employee(0, "", "", 0.0)
while choice >= 1 and choice <= 5:
    print("\n\n1. Add Record\n2. List Record\n3. Modify Records\n4. Delete Records\n5. Exit\n\n")
    choice = int(input("Enter Your Choice : "))
    if(choice == 1):
        empNo = int(input("Enter Employee No : "))
        empName = input("Enter Employee Name : ")
        empDes = input("Enter Employee Desingnation : ")
        empSal = float(input("Enter Employee Salary : "))
        emp = Employee( empNo, empName, empDes, empSal)
        emp.addNewEmployee()

    elif(choice == 2):
        print("\n")
        for emp in employee.getEmpList():
            print(emp)    

    elif(choice == 3):
        empNo = int(input("Enter Employee No : "))
        empName = input("Enter Employee Name : ")
        empDes = input("Enter Employee Desingnation : ")
        empSal = float(input("Enter Employee Salary : "))
        emp = employee.modifyEmpById( empNo, empName, empDes, empSal)  
        if(emp == False):
            print("\nSorry..! Modification Failes Employee Not Found For Id : ", empNo) 
        else:
            print("Succesfully Modify Employee For Id ", empNo)    

    elif(choice == 4):
        empNo = int(input("Enter Employee Id : "))
        emp = employee.deleteEmpById(empNo)
        if(emp == False): 
            print("\nSorry..! Delete Failes Employee Not Found For Id : ", empNo)  
        else:
             print("Succesfully Deleted Employee For Id ", empNo)         
    elif(choice == 5):
        exit(0)



