#include <iostream>
#include <vector>
#include <string>

using namespace std;

// Notice struct to hold each notice
struct Notice {
    string title;
    string body;
};

// Notice board class to hold multiple notices
class NoticeBoard {
private:
    vector<Notice> notices; // vector to store notices
    
public:
    // Add a new notice to the board
    void addNotice(string title, string body) {
        Notice notice;
        notice.title = title;
        notice.body = body;
        notices.push_back(notice);
    }
    
    // Display all notices on the board
    void displayNotices() {
        if (notices.size() == 0) {
            cout << "There are no notices on the board.\n";
        } else {
            cout << "Notices on the board:\n";
            for (int i = 0; i < notices.size(); i++) {
                cout << "Title: " << notices[i].title << endl;
                cout << "Body: " << notices[i].body << endl << endl;
            }
        }
    }
};

int main() {
    NoticeBoard board; // create a notice board object
    
    // add some notices to the board
    board.addNotice("Meeting tomorrow", "Don't forget the meeting tomorrow at 10am in the conference room.");
    board.addNotice("New employee", "Please welcome our new employee, John Smith, who will be joining us next Monday.");
    
    // display all notices on the board
    board.displayNotices();
    
    return 0;
}
