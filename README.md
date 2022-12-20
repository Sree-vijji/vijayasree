class Collegedetails:
    def __init__(self, clgname, clgcontact, clgaddress):
        self.clgname = clgname
        self.clgcontact = clgcontact
        self.clgaddress = clgaddress
class Studentdetails(Collegedetails):
    def __init__(self, clgname,clgcontact,clgaddress,name, rollNum, age, address, phnNum,sem_marks):
        super().__init__(clgname,clgcontact,clgaddress)
        self.name = name
        self.rollNum = rollNum
        self.age = age
        self.address = address
        self.phnNum = phnNum
        self.sem_marks=sem_marks
        totalmarks = 0
        for sem in sem_marks:
            for subject in sem_marks[sem]:
                totalmarks = totalmarks + sem_marks[sem][subject]
        print(totalmarks / 40)
        if totalmarks>90:
            print("got the excellent marks")
        elif totalmarks>80 or totalmarks<60:
            print("got the very good marks")
        elif totalmarks>60 or totalmarks<50:
            print("got the good marks")
        elif totalmarks>50 or totalmarks<30:
            print("threshold marks")
        else:
            print("got the bad marks")
    def info(self):
        return "college name:{},college contact:{},college address:{},student name:{},student rollnum:{},student age:{},student address:{}, student phnNum:{},semister marks:{}".format(self.clgname,self.clgcontact,self.clgaddress,self.name,self.rollNum,self.age,self.address,self.phnNum,self.sem_marks)
sem_marks={'sem1': {"english": 83, "maths": 85, "ES": 90, "Circuits": 78, "Awp": 90},
                         'sem2': {"m1": 80, "Embedded": 90, "STld": 90, "NA": 90, "dbms": 90},
                         'sem3': {"m2": 60, "ES": 90, "emtl": 90, "DS": 90, "English": 90},
                         "sem4": {"m3": 80, "dsd": 98, "Et": 90, "cprogram": 90, "vlsi": 90},
                         "sem5": {"m4": 90, "controlsystems": 90, "powerelectronics": 89, "mefa": 90, "befa": 78},
                         "sem6": {"m5": 89, "Edrawing": 90, "Radar": 78, "edc": 90, "chemistry": 90},
                         "sem7": {"logics": 90, "design": 89, "computer": 90, "EB": 90, "physics": 90},
                         "sem8": {"solar": 90, "ED": 90, "OS": 90, "DC": 90, "AC": 90}}
Result=Studentdetails("Ravindra college of engineering",9100819982,"Near by bustop ","vijayasree",479,21,"1-56 Dhone mandal kurnool city",9876543210,sem_marks)
print(Result.info())
