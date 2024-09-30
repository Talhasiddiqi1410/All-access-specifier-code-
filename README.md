# All-access-specifier-code-
#include <iostream>

using namespace std;

class MyClass1 {
private:
    int privateMember1 = 10; // Accessible only within MyClass1

public:
    int publicMember1 = 20; // Accessible anywhere

    // Access privateMember1 using a public function
    void accessPrivate() {
        cout << "Accessing private member from MyClass1: " << privateMember1 << endl;
    }
};

class MyClass2 {
protected:
    int protectedMember1 = 30; // Accessible within MyClass2 and derived classes (if any)

public:
    int publicMember2 = 40; // Accessible anywhere

    // Access protectedMember1 using a public function
    void accessProtected() {
        cout << "Accessing protected member from MyClass2: " << protectedMember1 << endl;
    }
};

int main() {
    MyClass1 obj1;

    // Error: Trying to access private member directly
    // cout << obj1.privateMember1 << endl; // Uncomment to see the error

    cout << "Public member of MyClass1: " << obj1.publicMember1 << endl;
    obj1.accessPrivate(); // Accessing private member using a public function

    MyClass2 obj2;

    cout << "Public member of MyClass2: " << obj2.publicMember2 << endl;
    obj2.accessProtected(); // Accessing protected member using a public function

    // Error: Trying to access protected member directly outside MyClass2 (or derived classes)
    // cout << obj2.protectedMember1 << endl; // Uncomment to see the error

    return 0;
}
