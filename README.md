# Minor-project

# Todo List Manager

A powerful command-line application for managing multiple todo lists with ease and efficiency.

## Usage

### Viewing Lists and Items

- `todo show`: Shows all the list names.
  Example: `todo show`
  Output:
  Your Todo Lists:
  1. Work
  2. Personal
  3. Shopping

- `todo show -a`: Shows all the list names along with the items.
  Example: `todo show -a`
  Output:
  Work:
  1. [ ] Finish project proposal
  2. [x] Schedule team meeting
  
  Personal:
  1. [ ] Go for a run
  2. [ ] Call mom
  
  Shopping:
  1. [ ] Buy groceries
  2. [ ] Get new shoes

- `todo show -c`: Shows all the completed items of all lists.
  Example: `todo show -c`
  Output:
  Completed items:
  Work:
  - [x] Schedule team meeting

- `todo show -i`: Shows all the incomplete items of all lists.
  Example: `todo show -i`
  Output:
  Incomplete items:
  Work:
  - [ ] Finish project proposal
  Personal:
  - [ ] Go for a run
  - [ ] Call mom
  Shopping:
  - [ ] Buy groceries
  - [ ] Get new shoes

- `todo show <list_name> -c`: Shows all the completed items of that list.
  Example: `todo show Work -c`
  Output:
  Completed items in Work:
  - [x] Schedule team meeting

- `todo show <list_name> -i`: Shows all the incompleted items of that list.
  Example: `todo show Work -i`
  Output:
  Incomplete items in Work:
  - [ ] Finish project proposal

- `todo show <list_name>`: Shows all the items of that list.
  Example: `todo show Work`
  Output:
  Work:
  1. [ ] Finish project proposal
  2. [x] Schedule team meeting

### Completing Tasks

- `todo complete <list_name> <item_number>`: Marks that particular item of that list as completed.
  Example: `todo complete Work 1`
  Output: Item “Finish project proposal” marked as completed in Work list.

- `todo complete <list_name>`: Marks all the items of that list as completed.
  Example: `todo complete Shopping`
  Output: All items in Shopping list marked as completed.

- `todo complete`: Marks all items of all lists as completed.
  Example: `todo complete`
  Output: All items in all lists marked as completed.

### Removing Lists and Items

- `todo remove`: Removes all lists.
  Example: `todo remove`
  Output: All lists have been removed.

- `todo remove complete`: Removes all complete items from all lists.
  Example: `todo remove complete`
  Output: All completed items have been removed from all lists.

- `todo remove incomplete`: Removes all incomplete items from all lists.
  Example: `todo remove incomplete`
  Output: All incomplete items have been removed from all lists.

- `todo remove <list_name>`: Removes that particular list.
  Example: `todo remove Shopping`
  Output: Shopping list has been removed.

- `todo remove <list_name> -c`: Removes all the complete items in that particular list.
  Example: `todo remove Work -c`
  Output: All completed items have been removed from Work list.

- `todo remove <list_name> -i`: Removes all the incomplete items in that particular list.
  Example: `todo remove Work -i`
  Output: All incomplete items have been removed from Work list.

- `todo remove <list_name> <item_number>`: Removes that item from the list.
  Example: `todo remove Work 1`
  Output: Item “Finish project proposal” has been removed from Work list.

### User Authentication and Synchronization

- `todo login`: Prompts for email and password. Creates a new user if email is valid and doesn’t exist before.
  Example: `todo login`
  Output: Please enter your email: user@example.com
           Please enter your password: ********
           Login successful!

- `todo logout`: Logs out the user if any logged in.
  Example: `todo logout`
  Output: You have been logged out successfully.

- `todo push`: Syncs local changes with the cloud.
  Example: `todo push`
  Output: Your todo lists have been synced to the cloud.

- `todo pull`: Syncs changes from the cloud to local.
  Example: `todo pull`
  Output: Your todo lists have been updated from the cloud.

### Sharing and Collaboration

- `todo share <list_name> <email>`: Shares the list with the user with that email so they can contribute together.
  Example: `todo share Work colleague@example.com`
  Output: Work list has been shared with colleague@example.com.

- `todo unshare <list_name> <email>`: Unshares the list with the user with that email.
  Example: `todo unshare Work colleague@example.com`
  Output: Work list is no longer shared with colleague@example.com.

- `todo show shared`: Shows all the shared lists.
  Example: `todo show shared`
  Output:
  Shared lists:
  1. Work (shared with: colleague@example.com)
  2. Project X (shared with: team@example.com)

- `todo show shared --list <list_name>`: Shows all the users with whom the list is shared.
  Example: `todo show shared --list Work`
  Output:
  Work list is shared with:
  - colleague@example.com
  - manager@example.com

- `todo show shared --email <email>`: Shows all the items of that list shared with that user.
  Example: `todo show shared --email colleague@example.com`
  Output:
  Lists shared with colleague@example.com:
  Work:
  1. [ ] Finish project proposal
  2. [x] Schedule team meeting

### Notifications

- `todo show notifications -u`: Shows all the unread notifications of the user.
  Example: `todo show notifications -u`
  Output:
  Unread notifications:
  1. New share request: “Work” list from manager@example.com
  2. Item added to “Project X” by team@example.com

- `todo show notifications -r`: Shows all the read notifications of the user.
  Example: `todo show notifications -r`
  Output:
  Read notifications:
  1. “Shopping” list completed
  2. Reminder: Call mom

- `todo show notifications`: Shows all the notifications of the user.
  Example: `todo show notifications`
  Output:
  All notifications:
  Unread:
  1. New share request: “Work” list from manager@example.com
  2. Item added to “Project X” by team@example.com
  Read:
  3. “Shopping” list completed
  4. Reminder: Call mom

## Installation

1. Clone the repository:
   git clone https://github.com/yourusername/todo-list-manager.git
2. Navigate to the project directory:
   cd todo-list-manager
3. Install dependencies:
   npm install
4. Run the application:
   node todo.js