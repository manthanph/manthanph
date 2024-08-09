#include <iostream>
using namespace std;

class Student {
    int rollNo;
    string name;
    int sgpa;
    public:
           void enter(Student s[], int n);
           void display(Student s[], int n);
           void sortAscending(Student s[], int n);
};

void enter(Student s[], int n) {
    for(int i = 0; i < n; i++){
        cout << "\nEnter Roll No: ";
        cin >> s[i].rollNo;
        cout << "Enter Name: ";
        cin >> s[i].name;
        cout << "Enter SGPA: ";
        cin >> s[i].sgpa;
    }
}

void display(Student s[], int n) {
    cout << "\nStudent Records\n";
    for (int i = 0; i < n; i++) {
        cout << "Roll No: " << s[i].rollNo  << ", Name: " << s[i].name << ", SGPA: " << s[i].sgpa << endl; 
    }
}

void sortAscending(Student s[], int n) {
    for (int i = 1; i < n; i++) {
        Student key = s[i];
        int j = i - 1;
        while (j >= 0 && s[j].rollNo > key.rollNo) {
            s[j + 1] = s[j];
            j--;
        }
        s[j + 1] = key;
    }
}

int main() {
    Student s[5],x;
    int n = 5; // Allow entering 5 records
    int choice;

    do {
        cout << "\nStudent Database Menu\n";
        cout << "1. Enter Student Records\n";
        cout << "2. Display All Records\n";
        cout << "3. Sort Records by Roll No (Ascending Order)\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                x.enter(s, n);
                break;
            case 2:
                x.display(s, n);
                break;
            case 3:
                x.sortAscending(s, n);
                break;
            case 4:
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice.\n";
                break;
        }

        if (choice != 4) {
            cout << "\nDo you want to continue ";
            cin >> choice;
        }

    } while (choice == 1);

    return 0;
}
