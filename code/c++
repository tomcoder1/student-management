#include <iostream>
#include <vector>
using namespace std;

class Person {
public:
    string name;
    int age;

    Person(string _name, int _age) : name(_name), age(_age){}

    void getName();

    void getAge();
};

void Person::getName(){
    cout << "Name: " << name << "\n";
}
void Person::getAge(){
    cout << "Age: " << age << "\n";
}

class Course{
public:
    string courseName; 
    int courseWeight;
    Course (string _courseName, int _courseWeight) : courseName(_courseName), courseWeight(_courseWeight){}

};

class Student : public Person {
private:
    static int stemID;
public:
    vector<pair<Course, int>> grades;
    int ID;
    Student(string _name, int _age) : Person(_name, _age) {
        ID = stemID++;
    }
    void getID();
    void getGrades();
    float averageGPA();
    void getGPA();
    void getStudentInfo();

    void addCourseAndGrades(Course CName, int CGrades);
};
void Student::getID(){
    cout << "ID: " << ID << "\n";
}
void Student::getGrades(){
    if (grades.size() == 0)
        return;
    cout << "The courses that " << name << " attends, and their grades: " << "\n";
    for (auto i : grades){
        cout << i.first.courseName << ": " << i.second << "   ";
    }
    cout << "\n";
}
float Student::averageGPA(){
    float sum = 0, d = 0;
    for (auto i : grades){
        sum += i.second * i.first.courseWeight;
        d += i.first.courseWeight;
    }
    return sum / d;
}
void Student::getGPA(){
    if (grades.size() == 0)
        return;
    cout << "GPA: " << averageGPA() << "\n";
}
void Student::getStudentInfo(){
    cout << "Student's information: " << "\n";
    getName();
    getAge();
    getID();
    getGrades();
    getGPA();
    cout << "\n";
}
void Student::addCourseAndGrades(Course CName, int CGrades){
    grades.push_back(make_pair(CName, CGrades));
}
int Student::stemID = 1;

int main(){
    Student tommy ("Pham Tommy" ,18);
    Student steve ("Pham Tan Dung", 18);
    Student hm ("Tran Huu Manh" , 18);

    Course cs ("Computer", 5);
    Course math ("Math", 10);
    Course pp ("Ping Pong", 2);

    tommy.addCourseAndGrades(cs, 10);
    tommy.addCourseAndGrades(math, 8);
    tommy.getStudentInfo();

    steve.addCourseAndGrades(math, 9);
    steve.addCourseAndGrades(pp, 5);
    steve.getStudentInfo();

    hm.addCourseAndGrades(math, 10);
    hm.getStudentInfo();
}
